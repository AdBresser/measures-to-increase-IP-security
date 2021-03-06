## 7. Assurance

### Operational Security Requirements

In [RFC3871] a list of operational security requirements for the infrastructure of large Internet Service Provider (ISP) IP networks (routers and switches) is specified. 
It provides network operators a clear, concise way of communicating their security requirements to vendors. 
It covers functional requirements, documentation requirements and assurance requirements.
Functional Requirements:
*	Device Management Requirements 
*	In-Band Management Requirements 
*	Out-of-Band (OoB) Management Requirements 
*	Configuration and Management Interface Requirements 
*	IP Stack Requirements 
*	Rate Limiting Requirements 
*	Basic Filtering Capabilities 
*	Packet Filtering Criteria 
*	Packet Filtering Counter Requirements 
*	Other Packet Filtering Requirements 
*	Event Logging Requirements 
*	Authentication, Authorization, and Accounting (AAA) Requirements 
*	Layer 2 Devices Must Meet Higher Layer Requirements 
*	Security Features Must Not Cause Operational Problems 
*	Security Features Should Have Minimal Performance Impact
Documentation Requirements:
*	Identify Services That May Be Listening 
*	Document Service Defaults 
*	Document Service Activation Process 
*	Document Command Line Interface 
*	'Console' Default Communication Profile Documented
Assurance Requirements:
*	Identify Origin of IP Stack 
*	Identify Origin of Operating System
For detailed recommendation on how to protect the router's control plane, see [RFC6192].

### Security audit

It is a good practice to conduct technical and procedural security audits. 
Those audits can be held with fixed time intervals, after a (major) change and after an incident.

### Security certification

[ISO27000] is the standard that helps organizations keep information assets secure. 
Although this standard is not specific enough for networking equipment, implementation and certification eases audits (at least the procedural part of it).

### Contingency planning

Because of the packet switching nature of IP, it has natural robustness. 
Still it can be very useful to regularly perform a contingency audit. 
An approach for such an analysis, is exploring several "what if" situations to identify areas of improvement. 
This is especially useful when the networks grows incremental.

### CERT / CSIRT

A computer emergency response team (CERT) is an expert group that handles computer security incidents. 
Alternative names for such groups include computer emergency readiness team and computer security incident response team (CSIRT).
The CERTs are organized in [FIRST] (global Forum of Incident Response and Security Teams)

### Security Operations Center

A Security Operations Center (SOC) is responsible for the detection and investigation of vulnerabilities in the operational infrastructure, the interpretation of cyber threats and the advising of countermeasures to remove existing risks. 
During disasters, the SOC acts as the Computer Emergency Response Team (CERT) [CSAN2016].

### bgp.he.net

The Hurricane Electric BGP Toolkit [BGPHE], gives insight in, amongst others, actual routing, prefix and relations between networks.
This can support quality and consistency checking.

### National contingency boards

Internet service providers in the Netherlands have established the Dutch Continuity Board (DCB), which works on measures to minimise the impact of DDoS attacks on Dutch critical infrastructure and to make services that have been disrupted available again as soon as possible [CSAN2016].

### National Detection Network

In The Netherlands investments have been made in the National Detection Network [NDN]. 
This is a partnership of the NCSC and other parties in the exchange of information on detected threats [CSAN2016].
