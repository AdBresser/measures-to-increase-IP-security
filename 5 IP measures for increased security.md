## 5. IP measures for increased security

### Port filtering

One of the most basic measures to increase the security is to perform filtering based on the TCP/UDP ports. 
This can be used to protect servers from being accessed on ports without any public service, but also in access networks to protect customers against attacks on ports that were not intended for global purposes. 
In access networks there is sometimes also a port 25 block to prevent spam by infected end-user devices. 
In these cases, the customer email is to be sent over ISP SMTP servers. 
This prevents the ISP from being blacklisted and thus completely loosing email connectivity.

### Quarantine IP addresses

An IP address (typically associated with an user) can (temporally) be blocked from access to the majority of the Internet. 
This can be useful when the IP address is used for unwanted behaviour, like being a (potential) source of a DDOS. 
This can be the case when the control of a PC or server is taken over by an infection. 
Once this infection is removed, the IP address can be granted full access again. 
Such measures have proved to be very successful in not only reducing the unwanted behaviour, but also in the distribution of malware. 
The identification the relevant IP addresses, is of course crucial. 
In a case of an access network, this was done by forcing all email over an SMTP server (port 25 block) and profiling. 
In an access network were this was implemented, the zombie rate was significant lower.
Similar concepts also work in hosting environments to prevent / mitigate undesired traffic. 
It is not uncommon that a hosting customer that triggers abuse messages (e.g. by sending spam), receives a port 25 block until the issue is resolved.
In residential environments, typically only one IP address is issued per physical connection. 
More devices can use the connection by implementing concepts like NAT. 
When such a IP address is placed in quarantine, this means that all devices loose connectivity, when only one device is infected. 
This increases the awareness of the end-user (TV video streaming stops, when the adolescent laptop is infected), but can have unwanted side effects without being noticed (IoT device stops). 
 
### Shared DDOS scrubbing center

To mitigate the impact of DDOS attacks there are DDOS scrubbing solutions. 
They can be on-site or outsourced, but they can also be shared. 
The Dutch national anti-DDOS scrubbing center [NaWas], is a solution build on top of IXPs to make it accessible for all participants. 
It can be activated within seconds by BGP controlled rerouting the DDOS traffic to the scrubbing center and receiving the cleaned traffic.
