---
abstract: <p>Since KVM@TACC now requires bounded reservations, VM instances and their
  data are deleted when reservations end. While snapshots can preserve entire instances,
  persistent volumes offer a more flexible solution for storing experiment scripts
  and data that persists independently of your VM lifecycle. This guide walks through
  creating volumes via the GUI, partitioning and mounting storage, and extending volumes
  as your storage needs grow.</p>
authors:
- Mark Powers
categories:
- Tips and Tricks
- Featured
date: '2026-02-17 21:43:41+00:00'
featured: false
hide_image: true
image: http://chameleoncloud.org/media/filer_public/7a/81/7a81f256-1aa3-421a-a293-ca93608bfc80/figure1.png
slug: managing-persistent-storage-with-volumes-at-kvmtacc
subtitle: A guide to creating, attaching, and managing persistent volumes for VMs
title: Managing Persistent Storage with Volumes at KVM@TACC
---

<p>KVM@TACC is Chameleon's virtualized site, where instead of bare metal instances, you can deploy VMs. Last year, we started requiring bounded and advanced reservations at KVM@TACC, and as a result, your VM instances will be terminated when your reservation ends, and all of your data deleted. One option to preserve your instance is <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/kvm/kvm_gui.html#creating-a-instance-snapshot">via a snapshot</a>, which will create a bootable image based on your running VM that can be used to restore the state, similar to <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/images/cc_snapshot.html">cc-snapshot</a> for baremetal instances.</p>

<p>A snapshot will take the instance's entire filesystem and restore it. If you just want to persist a portion of your VM's files though, such as your experiment scripts or data, it may be easier to use a <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/kvm/kvm_volumes.html">persistent volume</a>. A volume is a block device that is not tied to a lease, and so you can set one up and keep it around, regardless of if it is tied to your instance.</p>

<h2>Creating a Volume Using the GUI</h2>

<p>To get started with volumes, make sure you have a <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/kvm/kvm_gui.html">running VM</a> and can SSH to it.</p>

<p><img align="center" border="1" src="https://chameleoncloud.org/media/filer_public/7a/81/7a81f256-1aa3-421a-a293-ca93608bfc80/figure1.png" width="800"></p>

<p><em>The create volume dialog</em></p>

<p>First, navigate to the Volume overview from the KVM GUI by selecting "Volumes &gt; Volumes" on the sidebar. Select "Create Volume", which will bring up a dialog like the one in the above image. Enter a name for your volume, and the size in GiB. Additionally, you can also select the type of volume you want to set up. Currently, we have 2 backend types: ceph-ssd and ceph-hdd. The ceph-ssd type is the same storage type as your VM boot disk. The ceph-ssd type is on older storage backed by spinning disks, which may be slower for random access, though we have more of this storage available. Typically, you can leave the volume source as "No source", but you could also create your volume as a copy of another volume or snapshot under the "volume source" option which might be useful if your instance has issues booting or freezes—you can create a volume from that instance's snapshot and manually recover any data. Once all of your options are configured as desired, click the "Create Volume" to confirm.</p>

<p><img align="center" border="1" src="https://chameleoncloud.org/media/filer_public/a4/d7/a4d763cb-4c5f-4b45-90bd-e887c7eccba7/figure2.png" width="800"></p>

<p><em>The "Volumes Attached" section of the instance overview</em></p>

<p>Now, you need to attach the volume to your instance. Navigate back to the instance overview via "Computes &gt; Instances" on the sidebar. Find your instance in the list, and under the "Actions" column select "Attach Volume". A popup will appear. Select your volume from the dropdown, and confirm with "Attach Volume". Now, if you select your instance, you'll be taken to the instance overview screen. At the bottom of this page, you should see a "Volumes Attached" section with information about the volume. Here, I see that my volume now is mounted as the block device <code>/dev/vdb</code> inside my instance. If I ssh into my VM instance, I now see that block device appears.</p>

<pre><code>cc@mark-volume-test-1:~$ lsblk
NAME    MAJ:MIN RM  SIZE RO TYPE MOUNTPOINTS
vda     253:0    0   40G  0 disk
├─vda1  253:1    0  550M  0 part /boot/efi
├─vda2  253:2    0    8M  0 part
└─vda3  253:3    0 39.5G  0 part /
vdb     253:16   0   10G  0 disk</code></pre>

<h2>Using the Volume</h2>

<p>If you want to store files in the new, empty volume, we'll need to partition the device, format it, and mount it. If you are not starting from an empty volume, skip the partition and formatting steps.</p>

<p>Here is one way to do this tested on Ubuntu 24.04, though the specifics may depend on your needs and your operating system. Additionally, this assumes your device is also attached to <code>/dev/vdb</code>.</p>

<p>Creation the partition:</p>

<pre><code>sudo parted -s /dev/vdb \
  mklabel gpt \
  mkpart primary ext4 0% 100%</code></pre>

<p>Format it</p>

<pre><code>sudo mkfs.ext4 /dev/vdb1</code></pre>

<p>Mount it to <code>/mnt/data</code></p>

<pre><code>sudo mkdir -p /mnt/data
sudo mount /dev/vdb1 /mnt/data</code></pre>

<p>Here is the output from my instance</p>

<pre><code>cc@mark-volume-test-1:~$ sudo parted -s /dev/vdb \
  mklabel gpt \
  mkpart primary ext4 0% 100%
cc@mark-volume-test-1:~$ sudo mkfs.ext4 /dev/vdb1
mke2fs 1.47.0 (5-Feb-2023)
Discarding device blocks: done
Creating filesystem with 2620928 4k blocks and 655360 inodes
Filesystem UUID: 4e628394-53a2-4867-a806-6889f22ebf07
Superblock backups stored on blocks:
        32768, 98304, 163840, 229376, 294912, 819200, 884736, 1605632

Allocating group tables: done
Writing inode tables: done
Creating journal (16384 blocks): done
Writing superblocks and filesystem accounting information: done

cc@mark-volume-test-1:~$ sudo mkdir -p /mnt/data
sudo mount /dev/vdb1 /mnt/data</code></pre>

<p>And now, we can see this reflected in <code>lsblk</code>.</p>

<pre><code>cc@mark-volume-test-1:~$ lsblk
NAME    MAJ:MIN RM  SIZE RO TYPE MOUNTPOINTS
vda     253:0    0   40G  0 disk
├─vda1  253:1    0  550M  0 part /boot/efi
├─vda2  253:2    0    8M  0 part
└─vda3  253:3    0 39.5G  0 part /
vdb     253:16   0   10G  0 disk
└─vdb1  253:17   0   10G  0 part /mnt/data</code></pre>

<p>Now, I can write up to 10GB of data to the <code>/mnt/data</code> directory, and it will be stored in my volume, rather than the instance's boot disk.</p>

<h2>Extending the Volume</h2>

<p>Please keep in mind when creating volumes that Chameleon has a shared pool of storage for all users, so only use as much space as you actually need. However, if you find that you need more storage than you initially set up, it is easy to extend an existing volume.</p>

<p><img align="center" border="1" src="https://chameleoncloud.org/media/filer_public/9b/82/9b82f513-ee42-4b47-bde4-bc59fc66d26f/image3.png" width="800"></p>

<p>Navigate back to the volume overview by selecting "Volumes &gt; Volumes". Under the "Actions" column for your volume, select "Extend Volume" which will bring up the above window. Enter the new volume size as desired.</p>

<pre><code>cc@mark-volume-test-1:~$ lsblk
NAME    MAJ:MIN RM  SIZE RO TYPE MOUNTPOINTS
vda     253:0    0   40G  0 disk
├─vda1  253:1    0  550M  0 part /boot/efi
├─vda2  253:2    0    8M  0 part
└─vda3  253:3    0 39.5G  0 part /
vdb     253:16   0   20G  0 disk
└─vdb1  253:17   0   10G  0 part /mnt/data</code></pre>

<p>My instance automatically picked up the disk change, and <code>/dev/vdb</code> appears as 20G. In order to use this space, we need to update the partition, and update the filesystem:</p>

<pre><code>sudo growpart /dev/vdb 1
sudo resize2fs /dev/vdb1</code></pre>

<p>Here is the output from my instance after running these commands. Now <code>lsblk</code> shows that my partition is the full 20GiB.</p>

<pre><code>cc@mark-volume-test-1:~$ sudo growpart /dev/vdb 1
sudo resize2fs /dev/vdb1
CHANGED: partition=1 start=2048 old: size=20967424 end=20969471 new: size=41940959 end=41943006
resize2fs 1.47.0 (5-Feb-2023)
Filesystem at /dev/vdb1 is mounted on /mnt/data; on-line resizing required
old_desc_blocks = 2, new_desc_blocks = 3
The filesystem on /dev/vdb1 is now 5242619 (4k) blocks long.

cc@mark-volume-test-1:~$ lsblk
NAME    MAJ:MIN RM  SIZE RO TYPE MOUNTPOINTS
vda     253:0    0   40G  0 disk
├─vda1  253:1    0  550M  0 part /boot/efi
├─vda2  253:2    0    8M  0 part
└─vda3  253:3    0 39.5G  0 part /
vdb     253:16   0   20G  0 disk
└─vdb1  253:17   0   20G  0 part /mnt/data</code></pre>

<h2>Further Usage</h2>

<p>If you prefer to use the CLI for managing volumes, see the <a href="https://docs.openstack.org/cinder/latest/cli/cli-manage-volumes.html">OpenStack Cinder documentation</a>. Python-chi has <a href="https://python-chi.readthedocs.io/en/latest/modules/storage.html#chi.storage.Volume">Volume support</a> (see <a href="https://trovi.chameleoncloud.org/dashboard/artifacts/48c7e345-e27e-4717-9459-d0e19743622c/">this Trovi artifact</a> for a notebook example).</p>

<p>The steps above for mounting your device assume that it is always located at <code>/dev/vdb</code>. If you have multiple volumes attached to your instance, you can't assume the block device name. Additionally, if your instance reboots, you'll need to remount the volume. One solution to this is to use <a href="https://aws.amazon.com/blogs/compute/how-to-mount-linux-volume-and-keep-mount-point-consistency/">fstab to automatically mount your device by</a> UUID.</p>

<p>As mentioned before, you create a volume from an instance snapshot, which can be used in case your instance has problems to recover its data. You could use this feature to export data from a <a href="https://chameleoncloud.readthedocs.io/en/v1.0/technical/images.html#downloading-an-image">cc-snapshot image</a>, by downloading it from the baremetal site and uploading the image to KVM@TACC before creating a volume.</p>