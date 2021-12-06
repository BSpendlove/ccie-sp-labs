# ISIS Segment Routing Basics (Configuration based on almost best practices)

### NET ID
Typically you should encode the loopback address in the system ID field of the NET address and pad with 0s like:

Loopback0 = 192.0.2.1
NET = 49.0001.[1920.0000.2001].00

however I have simply used the router #, for example:
xrv1 = 49.0001.[0000.0000.0001].00

### LSP Key Chain Authentication
There are 2 methods of authentication

1) LSP (neighbors can still come up in this case) however LSPs with wrong authentication will not be installed in the LSDB
2) Domain Authentication (based on the interface level and will not form adjacency)

Key Chain is used in the lab but you can utilize key chains to automate start/end dates and key rotations every x amount of hours/days/months depending on how confident you feel about that... Sometimes simple is good, you can easily change it if it has been exposed...

### Metric Style Wide

Bigger metrics to play with for more general costing design

### Default metric

Default metric is 10, however on Cisco you can set a default metric for interfaces that have no metric defined... This should be considered in all cases to prevent a random link being used that an engineer/automation tool has not correctly configured...

### MPLS related commands

MPLS traffic engineering commands have only been enabled for the relevant level and using the loopback as the router-id to uniquely identify the node within the MPLS TE database/topology

### Segment Routing

Segment Routing enabled for MPLS and prefix-sid has been assigned to the loopback address

### SPF Intervals

These have been tweaked as per Ciscos recommended values for optimal convergence without enabling TI-LFA

### IPv6

Single topology allows SPF to perform a single calculation for both address families based on a single SPF tree. As long as both v4 and v6 are deployed on the same interfaces then you will not run into an issue and this is the preferred way to run ISIS unless you have other demands for a different topology for IPv6

### Loopbacks

Always put into passive (incase they are used as unnumbered)

### P2Ps

Circuit type is always set as per the topology diagram (mainly level 2 only unless it's a level 1/2 router connecting to a level 2 router)
Hello padding is disabled, this can be set to sometimes but we will not require this
AFI v4 and v6 are enabled on all relevant interfaces
point-to-point network type to avoid needing to perform DIS election when there are always 2 routers on a link, no broadcast network type is needed in our topology

### Prefix suppression

Can be enabled to only advertise loopback addresses throughout the network but this is an 'almost' best practice config based on Cisco and other vendor documentation

### Log adjacency changes

Logging these changes are useful for troubleshooting/log purposes...

### LSP Generation Interval

When possible, generation interval should be set to the lowest possible value. Router will wait this amount of seconds between creating new versions of a given LSP, with CPUs these days it doesn't take much resources to perform this action with hundreds of routers in a single L2 domain + area

### LSP Refresh Interval

Set to max because ideally refresh shouldn't be required because a topology change will cause the router to send out an update which in effect will technically refresh the LSP, so minimal LSP refresh is required...
