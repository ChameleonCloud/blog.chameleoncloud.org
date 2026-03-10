---
abstract: "<p>Learn about all of the ways you can store your experiment data on Chameleon,\
  \ including a fantastic new\_feature: The Shared Filesystem!</p>"
authors:
- Zhuo Zhen
categories:
- Tips and Tricks
date: '2022-10-26 22:09:36+00:00'
featured: false
hide_image: true
image: http://chameleoncloud.org/media/filer_public/99/11/99118e34-aceb-469b-bb55-586edce34d05/chameleon-storage.png
slug: data-storage-management-and-sharing-on-chameleon
subtitle: ''
title: Data Storage, Management, and Sharing on Chameleon
---

<p style="text-align: center;"><b id="docs-internal-guid-c167fd00-7fff-4652-e70f-78513dfc48dd"><img src="https://chameleoncloud.org/media/filer_public/99/11/99118e34-aceb-469b-bb55-586edce34d05/chameleon-storage.png" style="width: 512px; height: 360px;"></b></p>

<p>Chameleon offers multiple ways to store and share your data, so it is important to understand the differences among types of storage and your needs to help you choose the best storage solution for your experiment. Chameleon storage capabilities are provided via an enhanced version of mainstream <a href="https://www.openstack.org/">OpenStack</a>, including both ephemeral storage and persistent storage (Object Storage, Block Storage, and File-based storage). In this blog, we will discuss all storage types provided by Chameleon and their use cases. Don’t forget to check out our Jupyter Notebook tutorials, Youtube video, and various learning materials mentioned at the end of the blog!<br>
 </p>

<h1>Ephemeral Storage </h1>

<p>You can save your data to your instance’s primary block device. Chameleon has various types of storage nodes, such as nodes with NVME SSDs and storage hierarchy nodes. You can also deploy your standalone NFS server and clients via our <a href="https://chameleoncloud.org/appliances/25/">NFS Share appliance</a>. However, the data written to your instance is not persisted, i.e. it disappears when your instance is terminated. Chameleon offers the <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/images.html#the-cc-snapshot-utility">cc-snapshot</a> tool for bare metal instances, which allows you to snapshot your disk image. If you use the KVM@TACC site, you can also choose to base your disk image on top of a mountable block device (<a href="https://docs.openstack.org/cinder/latest/">OpenStack Cinder</a>). You need to be cautious when persisting and sharing your data this way, as we expect bootable images to contain the minimum amount of configuration to start your experiment quickly. Dependencies/software are encouraged to be saved this way. However, saving large datasets with your snapshotted disk image is not recommended, as large images take longer time or fail to launch. For large or important datasets, you should consider using persistent storage.</p>

<h1>Object Storage</h1>

<p><a href="https://chameleoncloud.readthedocs.io/en/latest/technical/swift.html">Object Storage</a> stores data as binary blobs, and allows you to access and manage your binary objects via a REST API. This is the only storage type that allows you to access your data anywhere without an instance, as all other storage types require you to have an active instance. An “object” is not a “file”, but multiple chucks of data. Object storage is suitable for storing large objects at scale and provides an easy way to share your data with others. Objects also contain metadata. Fixed-key metadata includes checksum, security levels, and ACLs. You can also set custom metadata to help you search, process, and use your objects. Chameleon provides the <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/swift.html#mounting-object-store-as-a-file-system">cc-cloudfuse</a> tool to help you mount your Object Store to your instance file system, but there are limitations as you are not dealing with the real files and the real file system. You can read our <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/swift.html#mounting-object-store-as-a-file-system">user documentation</a> for a list of limitations on mounting and accessing your Object Store via cc-cloudfuse tool. Object storage isn’t suitable for transactional data, as objects are immutable and updated in their entirety, i.e. you can not modify a single portion of an object. Therefore, it has a slower performance compared to other cloud storage types. Commercial cloud equivalents of object storage include <a href="https://aws.amazon.com/s3/">AWS S3</a>, <a href="https://cloud.google.com/storage">GCP Cloud Storage</a>, <a href="https://azure.microsoft.com/en-us/services/storage/blobs/">Azure Blob Storage</a>. </p>

<h1>Block Storage</h1>

<p>To fill the gap between KVM and bare metal setups on mountable storage capability, we released the <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/shares.html#">shared file system</a> through <a href="https://docs.openstack.org/manila/latest/">OpenStack Manila</a> interface for <a href="https://chameleoncloud.org/blog/2022/08/01/chameleon-changelog-for-july-2022/">CHI@UC and CHI@TACC in July, 2022</a>. A “share” is a pre-allocated, remote, and mountable file system backed by our Ceph clusters. The shared file system is persistent and allows you to detach from one instance and attach to another without data loss like OpenStack Cinder volumes. But even better than block storage service, you can mount a share to any number of instances and access the share by several users at a time, thanks to locking capability. Acting exactly the same as your instance’s local file system, all the data is saved together as a file with a file extension, and the files are organized in folders and subfolders. Your share is protected by <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/shares.html#storage-networks">reservable storage networks</a> and <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/shares.html#accessibility">access rules</a>, so that only permitted IPs (instances) can access the share. You can easily mount your share to your local file system via NFS protocol.</p>

<p>Not only your datasets, but you can also save dependencies/software in your share too! This would help you slim your disk image so that your instance can be launched faster. The shared file system also provides an efficient way to collaborate with your project members on files, but please be careful and prevent overwriting each other’s changes with the help of versioning software. Commercial cloud equivalents of file-based storage include <a href="https://aws.amazon.com/efs/">AWS EFS</a>, <a href="https://cloud.google.com/filestore">GCP Filestore</a>, <a href="https://azure.microsoft.com/en-us/services/storage/files/">Azure Files</a>.</p>

<h1>Learning Materials</h1>

<p>Our <a href="https://python-chi.readthedocs.io/en/latest/">python-chi</a> library helps you interact with all Chameleon storage types listed above. We also have a <a href="https://github.com/ChameleonCloud/notebooks/blob/master/tutorials/getting-started/DataManagement.ipynb">Jupyter Notebook tutorial for Data Management</a>, which walks you through various ways to store, manage, and share your data. In the tutorial, you can learn about cc-snapshot and cc-cloudfuse tools and how to interact with Chameleon Object Store. In addition, we created a separate <a href="https://chameleoncloud.org/experiment/share/81af3cca-76cd-4a2e-83e1-3deb1fc7cf14">Jupyter Notebook for our shared file system</a>. The tutorial explores how to create a share and access the share with a reserved storage network using the python-chi library. Don’t forget to check out the recording of our <a href="https://www.youtube.com/watch?v=NJWLfiWyOEo&amp;list=PLE8dVtsVJCUH7xZhrYTGYREqsppUi5Cf9&amp;index=2&amp;t=13s">Science, Storage, and Sanity Webinar</a> (Summer with Chameleon 2022) on <a href="https://www.youtube.com/channel/UCVP_TxAjuCiMoQRxC68Pt_A">Chameleon YouTube channel</a>. Other learning resources are listed below:</p>

<ul>
	<li><a href="https://chameleoncloud.readthedocs.io/en/latest/technical/swift.html#">Chameleon Object Store User Documentation</a></li>
	<li><a href="https://chameleoncloud.readthedocs.io/en/latest/technical/shares.html">Chameleon Shares User Documentation</a></li>
	<li><a href="https://chameleoncloud.readthedocs.io/en/latest/technical/kvm.html">Chameleon KVM User Documentation</a></li>
	<li><a href="https://chameleoncloud.org/blog/2022/07/19/experimenting-with-virtual-machines-on-chameleon/">Experimenting With Virtual Machines on Chameleon</a></li>
	<li><a href="https://docs.openstack.org/arch-design/design-storage/design-storage-concepts.html">OpenStack Storage Concepts</a><br>
	 </li>
</ul>