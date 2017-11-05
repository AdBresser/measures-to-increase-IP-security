## 3. BGP engineering measures

The Border Gateway Protocol (BGP) is the protocol almost exclusively used in the Internet to exchange routing information between network domains.  
Due to this central nature, it is important to understand the security measures that can and should be deployed to prevent accidental or intentional routing disturbances.
Good risk analysis of BGP vulnerabilities can be found in [CSRIC3BGP] and [NIST800-54]. 

### General BGP Operations and Security

General BGP Operations and Security is described in [BCP194]. It covers the following topics:
*	Protection of the BGP Speaker 
*	Protection of BGP Sessions on TCP level and by TTL Security (GTSM)
*	BGP Route Flap Dampening
*	Maximum Prefixes on a Peering
*	AS Path Filtering
*	Next-Hop Filtering
*	BGP Community Scrubbing
*	Prefix Filtering:
    *	Special-Purpose Prefixes
    *	Unallocated Prefixes, based on IANA and RIR-Allocated Prefix Filters
    *	Filters Created from Internet Routing Registries (IRRs)
    *	Filters based on SIDR
    *	Secure Inter-Domain Routing principles (BGP Prefix Origin Validation and BGPsec)
    *	Prefixes That Are Too Specific
    *	Filtering Prefixes Belonging to the Local AS and Downstreams
    *	IXP LAN Prefixes for Network Security, PMTUD and the Loose uRPF Problem
    *	The Default Route
    *	In Full Routing Networks with Internet Peers, Customers and Upstream Providers
    *	Prefix Filtering for Leaf Networks

### Advanced BGP management

In [BGPJob] there are some BGP measures mentioned that are especially relevant for the more specialized network operators (there is some overlap with [BCP194]):
*	Peer Locking aka "bignetworks filter" 
*	Dropping Bogon ASNs
Ingress:
*	Dynamic maximum prefix settings 
*	Reject Bogon prefixes (RFC1918, etc) 
*	Reject Bogon ASNs (AS0 / AS23456 etc) 
*	Reject IXP prefixes (Some IXP subnets) 
*	Reject leakage with the Peerlock filter 
*	Match against IRR whitelist (only customers) 
*	Mark as customer route (or as peer route) 
*	Scrub internally significant BGP communities 
*	Apply Features – (blackholing, traffic engineering, etc, only for customers)
Egress:
*	Reject Bogon prefixes 
*	Remove-private-AS 
*	Reject “bad” routes 
*	Accept peer routes (on customer session) 
*	Accept customer routes (on every session) 
*	Do prepending (if requested & applicable) 
*	Scrub internal communities 
*	Set next-hop-self 
*	Normalize Med

### BGP origin validation

There is a form of attack against the routing information provided by BGP4. 
This is done through injection of misleading routing information into the routing system. 
The measures to protect against misleading routing information consists of several Resource Public Key Infrastructure (RPKI) based components (next to the already mentioned). 
The operation best practices are described in [BCP185].
