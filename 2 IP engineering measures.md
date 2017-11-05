## 2. IP engineering measures

One of the major weaknesses of the IP protocol, is the possibility to spoof the IP source address of an IP packet. 
According to [CAIDA-Spoof] in around a third of the announced address space, prefixes and autonomous systems the source address is spoofable.

### Source IP address assurance

By setting up routers in networks properly, DDoS attacks based on spoofed IP source addresses, can be prevented. 
This way, spoofed packets are easily stopped. 
These packets are the source of many different forms of attacks. 
Unfortunately, filtering this is only effective if almost all networks set it up [CSAN2016].

The nearer the filters are applied to the origination of the spoofed traffic, the better the effects on the security and reliability of the hosts and the network will be. 
According to some measurements, up to 60% of the IP addresses used in attacks are bogon.

### Ingress filtering - Customers

On the edge of a network, every source IP address from every incoming IP packet can be validated. 
If the IP source address is not the expected IP address or doesn't belong to the known prefix, the packet should be dropped. 
This is clearly described in [BCP38]. 
This can be applied in access networks, transit networks and server networks. 
The amount of deployments is unknown. 
The benefits are mainly for the Internet community as a whole. 
More specific description on how to prevent nodes attached to the same IP link from spoofing each other's IP addresses, can be found in [SAVI].

### Ingress filtering - Transit & Peering

The IP source addresses of IP packets received from connectivity providers, can be validated. 
If the IP address is from your own prefixes, or from a private address range, the packet should be dropped. 
When the source IP address in the packet belongs to a customer, it can also be dropped, unless it is the IP address of a multi-homed customer. 
The amount of deployments in unknown. 
This filter is beneficial for your own infrastructure and your customers.

### Egress filtering - Transit & Peering

Source IP addresses of IP packets send to connectivity providers, can be validated. 
They should only contain IP addresses from prefixes you or your customers own. 
Although this seems redundant compared to the Ingress filtering - Customers, it prevents the leakage of IP packets with source addresses with from a private range, which is sometimes used for internal purposes. 
Moreover, it prevents IP packets with incorrect source IP addresses from wrongly configured or hacked servers you have in your network.
The amount of deployments is unknown. 
This filter is beneficial for the Internet community and maintaining a profile of a credible network provider.

### Egress filtering - Customers

The IP source addresses of IP packets send to customers can be validated. 
Those IP source addresses should not be from a private address range. 
It is an option to check for the IP range from the customer, but special care should be taken, because it could be valid traffic from multihomed customers or test traffic. 
The amount of implementation is unknown, but not a lot of implementations are expected. 
Benefit is for the customer, see also [BCP46].

### Advanced cases and solutions

[BCP84] is an update of [BCP38] and gives some advanced options for implementing source address assurance, including the handling of multihomed situations.

In [RIPE431] examples are given on how to configure routers for filtering.
The filtering options described can best be applied on the external interface, but in some cases it is more logical to perform the filtering on a other interface. 
This is especially the case for egress filtering.

### IPv6 considerations

IPv6 makes it somewhat easier to implement end2end security, because it supports end-to-end encryption.

As IPv6 is not yet widely deployed, it is likely that there are more (compared to IPv4) security weaknesses in implementations.

The available IPv6 address space will create opportunities to optimize security. 
E.g. in quarantine networks, were only the affected system can be blocked based on the IP address, instead of the blocking all systems that are behind one IPv4 address.

IPv6 will remove the need for IPv4 address space driven NAT solutions. 
NAT rewrites the source address of normal traffic to ensures reachability and is thus a natural source address assurance mechanism (which makes spoofing more complicated). 
IPv6 removes the need for NAT and could increase the spoofing opportunities, when [SAVI] is not implemented.

Although security by obscurity is never a sustainable security mechanism, the amount of IP addresses creates possibilities for this.
This is only mentioned here for completeness and not advised as a security mechanism.
