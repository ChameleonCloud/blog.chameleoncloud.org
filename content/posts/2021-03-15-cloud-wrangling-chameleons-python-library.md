---
abstract: "<p>Chances are, if you're using Chameleon today, you're probably utilizing\
  \ either the <a href=\"https://chameleoncloud.readthedocs.io/en/latest/technical/gui.html\"\
  >GUI</a> or the <a href=\"https://chameleoncloud.readthedocs.io/en/latest/technical/cli.html\"\
  >CLI</a> (or a mixture of both.) Did you know there's a Python library that makes\
  \ it easy to script your Chameleon experiments? In January <a href=\"https://www.chameleoncloud.org/blog/2021/02/02/chameleon-changelog-january-2021/\"\
  >we announced</a> the public release of <a href=\"https://python-chi.readthedocs.io/en/latest/\"\
  >python-chi</a>, the official Python library for CHI (Chameleon Infrastructure),\
  \ which is exactly that. Read on to learn all about python-chi and how to easily\
  \ use it\_to experiment on Chameleon.</p>"
authors:
- Jason Anderson
categories:
- Tips and Tricks
date: '2021-03-15 23:47:00+00:00'
featured: false
hide_image: true
image: http://chameleoncloud.org/media/filer_public/e7/b0/e7b01ed1-ae8b-4f57-8cd4-5678d6c9ead6/carbon.png
related_posts: []
slug: cloud-wrangling-chameleons-python-library
subtitle: ''
title: Cloud-Wrangling with Chameleon's Python Library
---

<p dir="ltr">Chances are, if you're using Chameleon today, you're probably utilizing either the <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/gui.html">GUI</a> or the <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/cli.html">CLI</a> (or a mixture of both.) Did you know there's a Python library that makes it easy to script your Chameleon experiments? In January <a href="https://www.chameleoncloud.org/blog/2021/02/02/chameleon-changelog-january-2021/">we announced</a> the public release of <a href="https://python-chi.readthedocs.io/en/latest/">python-chi</a>, the official Python library for CHI (Chameleon Infrastructure), which is exactly that.</p>

<p> </p>

<p dir="ltr">Why a separate library? Chameleon's cloud technology is built on <a href="https://www.openstack.org/">OpenStack</a>, and so Chameleon users (and operators!) benefit from a lot of work already invested by the open source community into the various service APIs and client libraries. Yet, the general-purpose nature of these APIs can make it excessively challenging to express what is really a simple use case on Chameleon. For example, here's how one might create a lease and launch a node via just the OpenStack Python libraries:</p>

<p dir="ltr"> </p>

<p dir="ltr"><code><tt>lease_name = "my-lease"</tt></code></p>

<p dir="ltr"><code><tt>node_type = "compute_haswell"</tt></code></p>

<p dir="ltr"><code><tt>node_count = 2</tt></code></p>

<p dir="ltr"><code><tt>image_name = "my-image"</tt></code></p>

<p> </p>

<p dir="ltr"><code><tt>from datetime import datetime, timedelta</tt></code></p>

<p dir="ltr"><code><tt>import json</tt></code></p>

<p dir="ltr"><code><tt>from dateutil import tz</tt></code></p>

<p dir="ltr"><code><tt>from time import sleep</tt></code></p>

<p dir="ltr"><code><tt>from blazarclient.client import Client as BlazarClient</tt></code></p>

<p dir="ltr"><code><tt>from glanceclient.client import Client as GlanceClient</tt></code></p>

<p dir="ltr"><code><tt>from keystoneauth1.session import Session</tt></code></p>

<p dir="ltr"><code><tt>from keystoneauth1.identity.v3 import ApplicationCredential</tt></code></p>

<p dir="ltr"><code><tt>from novaclient.client import Client as NovaClient</tt></code></p>

<p> </p>

<p dir="ltr"><code><tt># Create authentication context</tt></code></p>

<p dir="ltr"><code><tt>credential_name = os.getenv('OS_APPLICATION_CREDENTIAL_NAME')</tt></code></p>

<p dir="ltr"><code><tt>credential_secret = os.getenv('OS_APPLICATION_CREDENTIAL_SECRET')</tt></code></p>

<p dir="ltr"><code><tt>auth = ApplicationCredential(auth_url="https://chi.uc.chameleoncloud.org:5000/v3", application_credential_name=credential_name, application_credential_secret=credential_secret, username="", user_domain_name="chameleon")</tt></code></p>

<p dir="ltr"><code><tt>session = Session(auth=auth)</tt></code></p>

<p> </p>

<p dir="ltr"><code><tt># Request a lease for nodes for 1 hour</tt></code></p>

<p dir="ltr"><code><tt>start_date = datetime.now(tz=tz.tzutc()) + timedelta(seconds=70)</tt></code></p>

<p dir="ltr"><code><tt>end_date = start_date + timedelta(hours=1)</tt></code></p>

<p dir="ltr"><code><tt>blazar = BlazarClient('1', service_type='reservation', session=session)</tt></code></p>

<p dir="ltr"><code><tt>lease = blazar.lease.create(</tt></code></p>

<p dir="ltr"><code><tt><b id="docs-internal-guid-430cce45-7fff-c240-84fc-40b54f42fe4a">    </b>name=lease_name, start=start_date, end=end_date,</tt></code></p>

<p dir="ltr"><code><tt><b id="docs-internal-guid-430cce45-7fff-c240-84fc-40b54f42fe4a">    </b>reservations=[{'resource_type': 'physical:host', 'resource_properties': json.dumps(['=', '$node_type', node_type]), 'hypervisor_properties': '', 'min': str(node_count), 'max': str(node_count)}], events=[])</tt></code></p>

<p> </p>

<p dir="ltr"><code><tt># Wait for lease to start</tt></code></p>

<p dir="ltr"><code><tt># TODO: wait for lease to become ACTIVE before proceeding instead of sleeping!</tt></code></p>

<p dir="ltr"><code><tt>sleep(120)</tt></code></p>

<p> </p>

<p dir="ltr"><code><tt># Launch bare metal instances against the lease</tt></code></p>

<p dir="ltr"><code><tt>nova = NovaClient('2.10', session=session)</tt></code></p>

<p dir="ltr"><code><tt>glance = GlanceClient('2', session=session)</tt></code></p>

<p dir="ltr"><code><tt>reservation_id = json.loads(lease.get('reservations')).get('id')</tt></code></p>

<p dir="ltr"><code><tt>image_id = next((img for img in glance.images.list() if img.name == image_name)).id</tt></code></p>

<p dir="ltr"><code><tt>flavor_id = next((f for f in nova.flavors.list() if f.name == 'baremetal')).id</tt></code></p>

<p dir="ltr"><code><tt>server = nova.servers.create(name="my-server", image=image_id, flavor=flavor_id, </tt></code></p>

<p dir="ltr"><code><tt>scheduler_hints={'reservation': reservation_id},</tt></code></p>

<p dir="ltr"><code><tt><b id="docs-internal-guid-430cce45-7fff-c240-84fc-40b54f42fe4a">     </b>key_name='my-keypair',</tt></code></p>

<p dir="ltr"><code><tt><b id="docs-internal-guid-430cce45-7fff-c240-84fc-40b54f42fe4a">     </b>nics=[{'net-id': network_id, 'v4-fixed-ip': ''}],</tt></code></p>

<p dir="ltr"><code><tt><b id="docs-internal-guid-430cce45-7fff-c240-84fc-40b54f42fe4a">     </b>min_count=node_count,</tt></code></p>

<p dir="ltr"><code><tt><b id="docs-internal-guid-430cce45-7fff-c240-84fc-40b54f42fe4a">     </b>max_count=node_count)</tt></code></p>

<p><br>
 </p>

<p dir="ltr">And here's the same using python-chi:</p>

<p> </p>

<p dir="ltr"><code>lease_name = "my-lease"</code></p>

<p dir="ltr"><code>node_type = "compute_haswell"</code></p>

<p dir="ltr"><code>node_count = 2</code></p>

<p dir="ltr"><code>image_name = "my-image"</code></p>

<p> </p>

<p dir="ltr"><code>import chi</code></p>

<p dir="ltr"> </p>

<p dir="ltr"><code># Create authentication context (most info automatically sourced from env)</code></p>

<p dir="ltr"><code>chi.use_site('CHI@UC')</code></p>

<p> </p>

<p dir="ltr"><code># Request a lease for nodes for 1 hour</code></p>

<p dir="ltr"><code>reservations = []</code></p>

<p dir="ltr"><code>chi.lease.add_node_reservation(reservations, count=node_count, </code></p>

<p dir="ltr"><code>node_type=node_type)</code></p>

<p dir="ltr"><code>start_date, end_date = chi.lease.lease_duration(hours=1)</code></p>

<p dir="ltr"><code>lease = chi.lease.create_lease(lease_name, reservations, start_date=start_date,</code></p>

<p dir="ltr"><code><b id="docs-internal-guid-430cce45-7fff-c240-84fc-40b54f42fe4a">                     </b>end_date=end_date)</code></p>

<p> </p>

<p dir="ltr"><code># Wait for lease to start</code></p>

<p dir="ltr"><code>chi.lease.wait_for_active(lease.id)</code></p>

<p dir="ltr"> </p>

<p dir="ltr"><code># Launch bare metal instances against the lease</code></p>

<p dir="ltr"><code>reservation_id = get_node_reservation(lease.id)</code></p>

<p dir="ltr"><code>server = create_server(server_name, reservation_id=reservation_id,</code></p>

<p dir="ltr"><code>image_name=image_name, count=node_count)</code></p>

<p> </p>

<p dir="ltr">The Python library is designed to leverage the <a href="https://en.wikipedia.org/wiki/Pareto_principle#In_computing">Pareto principle</a>: by focusing on the most-commonly-used 20% of features of OpenStack, we can ideally handle 80% of individual use cases on Chameleon, namely:</p>

<ul>
	<li dir="ltr">
	<p dir="ltr">Making leases for bare metal nodes, networks, or IPs</p>
	</li>
	<li dir="ltr">
	<p dir="ltr">Launching bare metal instances against a lease</p>
	</li>
	<li dir="ltr">
	<p dir="ltr">Assigning floating IPs to instances</p>
	</li>
	<li dir="ltr">
	<p dir="ltr">Creating isolated networks that can NAT to the internet</p>
	</li>
</ul>

<p dir="ltr"> </p>

<p dir="ltr">You can build a lot of interesting things with these blocks. For example, you could set up a daily script that checks in the morning if there are available nodes, makes a reservation for a node starting at 9:00AM and launches your <a href="https://chameleoncloud.readthedocs.io/en/latest/technical/images.html#the-cc-snapshot-utility">bare metal snapshot</a> and emails you when the server is up and running, with a link to login. Or, you could script a complicated network setup as part of a Jupyter Notebook, where you need to create multiple networks and connect them together in various ways. In fact, just to give you a peek behind the curtain, we at Chameleon use this library to implement automated health checks of each cloud site, and even have some custom bots we call "<a href="https://github.com/chameleoncloud/hammers">hammers</a>" that run around fixing simple problems for us.</p>

<p> </p>

<p dir="ltr">If you're using the Jupyter interface, python-chi is already pre-installed on your Jupyter server, allowing you to script your Chameleon experiments easily within a Jupyter Notebook. You can also download the library to your workstation by following the <a href="https://python-chi.readthedocs.io/en/latest/#installation">installation instructions here</a>. If you want to just play around a bit more, check out a few of our interactive tutorials on the <a href="https://python-chi.readthedocs.io/en/latest/notebooks/reservations.html">documentation</a>, where you can learn about the basics.</p>

<p> </p>

<p dir="ltr">Have fun, and <a href="https://www.chameleoncloud.org/user/help/ticket/new/">let us know</a> how you use this library in your research and experimentation!</p>