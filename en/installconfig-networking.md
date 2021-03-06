Title: Networking
TODO:  Bug check: https://goo.gl/mPKBRl
       Not sure about the purpose of "deleting" a subnet. Won't it reappear eventually?


# Networking

This page shows where to view and edit the main networking elements in MAAS.
See [Concepts and terms][concepts] for the definitions of networking objects.


## Main view

To access the main networking view visit the 'Subnets' page:

![subnets page][img__2.2_subnets]

In the above example the following networking elements can be seen: *fabrics*,
*VLANs*, *subnets*, and *spaces*. Due to the nature of the particular network
topology being represented here, some elements are used multiple times. To be
clear, in this example there are 3 fabrics, 1 VLAN, and 3 subnets, and 1
(undefined) space. All such elements should be detected automatically by MAAS
but if they're not each can be added manually using the 'Add' button. 

This main view can also be filtered either by fabrics or by spaces through the
use of the 'Group by' dropdown.

Although each of the elements can be clicked upon to open up its own window,
fabrics, VLANs, and spaces do not have much in the way of configuration; their
names and descriptions can be altered. A VLAN, however, can additionally have
its MTU changed and also has an action available for
[enabling DHCP][enabling-dhcp] (see 'Take action' button).

A subnet, on the other hand, can be configured considerably and its window also
shows information pertinent to the day-to-day operation of MAAS. For these
reasons, a subnet will now be examined in more detail.

### Subnet window

Clicking a subnet (here `192.168.1.0/24`) will display its window. We'll look
at this example window by sections.

The **Subnet summary** section:

![networking subnets page summary][img__2.2_subnets-summary]

!!! Warning: 
    The fields in this section are immediately editable and changes
    are applied instantly.

Here, values for 'Gateway IP' and 'DNS' (nameserver), and optionally
'Description', are entered. Gateway and DNS values are passed to nodes for
commissioning and, if DHCP is MAAS-managed, for deploying too. There is also
the option of changing the subnet's fabric and VLAN. Spaces are managed at the
VLAN level.

'Managed allocation' refers to the ability of MAAS to completely manage a
subnet. See [Subnet management][subnet-management].

When 'Active mapping' is enabled, MAAS will scan the subnet every 3 hours to
discover hosts that have not been discovered passively. 

The **Static Routes** section:

This section can be used to define a static route between two subnets, allowing
administrators to configure reachability to a subnet from a source subnet. A
route is defined on a per-subnet basis to use a particular gateway, using a
configured destination and metric.

To create a static route, click the 'Add static route' button to reveal the
edit pane. Enter a Gateway IP address, select a destination subnet from the
'Destination' drop-down list, and edit the routing metric value if needed.
Clicking 'Add' will activate the route. Routes can be edited and removed using
the icons to the right of each entry. 

![networking static routes configuration][img__2.2_subnets-routes]

The **Utilisation** section:

![networking subnets utilisation][img__2.2_subnets-utilisation]

'Subnet addresses' shows the total number of addresses associated
with the subnet, here 254. 'Availability' shows how many of those addresses
are unused, and therefore "available", here 189, which corresponds to a
percentage of roughly 74% of the total. Finally, 'Used' shows the percentage
that *is* used, here roughly 26%.

The **Reserved** section:

![networking subnets reserved][img__2.2_subnets-reserved]

This shows the *reserved IP ranges*. This is an important subject and is
treated separately in [IP ranges][ipranges].

The **Used** section:

![networking subnets used][img__2.2_subnets-used]

This section displays hosts (including controllers) associated with the used
addresses along with related bits of host information.


<!-- LINKS -->

[concepts]: intro-concepts.md
[enabling-dhcp]: installconfig-network-dhcp.md#enabling-dhcp
[ipranges]: installconfig-network-ipranges.md
[subnet-management]: installconfig-network-subnet-management.md

[img__2.2_subnets]: ../media/installconfig-networking__2.2_subnets.png
[img__2.2_subnets-summary]: ../media/installconfig-networking__2.2_subnets-summary.png
[img__2.2_subnets-routes]: ../media/installconfig-networking__2.2_subnets-routes.png
[img__2.2_subnets-utilisation]: ../media/installconfig-networking__2.2_subnets-utilisation.png
[img__2.2_subnets-reserved]: ../media/installconfig-networking__2.2_subnets-reserved.png
[img__2.2_subnets-used]: ../media/installconfig-networking__2.2_subnets-used.png
