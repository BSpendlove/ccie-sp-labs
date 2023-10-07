# Base Config 2

This base configuration is based on the CCIE SP v5 Practice lab topology which can be found here:
https://learningnetwork.cisco.com/s/article/ccie-service-provider-practice-labs

There are 3 topology files, 1 which contains the full lab and the other 2 are each service provider network in the event of you wanting to only focus on intra domain routing with Segment Routing (ISP X) or LDP+RSVP-TE (ISP Y).

The scenario provided (from the Cisco article) in this base configuration for future labs mention ISP X is a next-generation ISP using Segment Routing and newer features like EVPN, SR-TE with PCE-PCEP, SR-ODN, Flex-Algo etc... and
are merging with a older service provider (ISP Y) which are running LDP and RSVP-TE, already providing services to their customers and we have to think about integration and optimization between the various protocols.


## Loopbacks

Name		v4 Loopback	v6 Loopback
SP-X-ASBR1	10.111.111.1	2001:db8:111::1
SP-X-ASBR2	10.111.111.2	2001:db8:111::2
SP-X-CE1	10.111.111.3	2001:db8:111::3
SP-X-CE2	10.111.111.4	2001:db8:111::4
SP-X-CE3	10.111.111.5	2001:db8:111::5
SP-X-CE4	10.111.111.6	2001:db8:111::6
SP-X-CE5	10.111.111.7	2001:db8:111::7
SP-X-CE6	10.111.111.8	2001:db8:111::8
SP-X-P1		10.111.111.9	2001:db8:111::9
SP-X-P2		10.111.111.10	2001:db8:111::10
SP-X-P3		10.111.111.11	2001:db8:111::11
SP-X-P4		10.111.111.12	2001:db8:111::12
SP-X-PCE1-RR1	10.111.111.13	2001:db8:111::13
SP-X-PCE2-RR2	10.111.111.14	2001:db8:111::14
SP-X-PE1	10.111.111.15	2001:db8:111::15
SP-X-PE2	10.111.111.16	2001:db8:111::16
SP-X-PE3	10.111.111.17	2001:db8:111::17
SP-X-PE4	10.111.111.18	2001:db8:111::18
SP-Y-ASBR1	10.222.222.1	2001:db8:222::1
SP-Y-ASBR2	10.222.222.2	2001:db8:222::2
SP-Y-CE1	10.222.222.3	2001:db8:222::3
SP-Y-CE2	10.222.222.4	2001:db8:222::4
SP-Y-CE3	10.222.222.5	2001:db8:222::5
SP-Y-CE4	10.222.222.6	2001:db8:222::6
SP-Y-P1		10.222.222.7	2001:db8:222::7
SP-Y-PE1	10.222.222.8	2001:db8:222::8
SP-Y-PE2	10.222.222.9	2001:db8:222::9
SP-Y-RR		10.222.222.10	2001:db8:222::10

## Other infrastructure addressing

All v4 and v6 addressing can be found on the article, along with high level diagrams for IGP design and BGP/MPLS/L3VPN/L2VPN design.
