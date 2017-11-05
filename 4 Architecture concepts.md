## 4. Architecture concepts

There are several architecture concepts that can increase the security and reliability of the routing system.

### Split destinations

It is possible to increase the security (e.g. mitigating DDOS attacks) by creating multiple instances of a destination for IP packets and manipulating the flow of IP traffic coming from the Internet. 
Such a solution can include separated servers, dual ASNs and separated peering policies. 
With the latter, peerings with trusted networks can be separated from worldwide connectivity. 
The advantage of this solution is that it is completely independent from other cooperation initiatives.

### Transit & Peering

The continuity of Internet connectivity can be increased by using multiple Transit providers, connecting to multiple IXPs and implementing that on multiple locations.
With respect to the peering policy: a more open policy increases the robustness, but a full open policy creates the risk of connecting with unknown parties.

### Selective peering

It is possible to selectively peer with networks that match a certain quality / security profile. 
Profiles can be based on region, black- and whitelist, [MANRS], information from RIPE DB and Peering DB. This typically is enabled / eased on route servers of IXP's.

### Trusted networks

It is possible to build a solution consisting of a network (VLAN) of trusted networks, that can be activated by each participating network in case of an emergency situation. 
This will result in a temporary disconnect from the global internet, while ensuring connectivity to trusted networks. 
This can be completely separated from regular peering policies.
In the Netherlands the Trusted Network Initiative [TNI] was launched to counter the adverse effects of DDoS attacks [CSAN2016]. 
 
### Direct connections

One of the most trustworthy solutions is of course the direct connection between networks.
