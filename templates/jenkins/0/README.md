# Rancher Rebalancer

### Info
This template contains a single alpine based image that performs simple balancing of a services across hosts in a Rancher cattle environment.

In some instances if there are host failures or maintenance you may end up with a host that can be running all, or the majority of containers, associated with a service.

What this rebalancer does is attempt to redistribute them more evenly across hosts in an environment to prevent service downtime.

The service is opt in, or opt out. If opt in is chosen then only services with a label of ```rebalance``` set to ```true``` will be balanced. If opt out is chosen then all services will be balanced apart from ones with the label ```rebalance``` set to ```false```

The service will by default attempt to balance across hosts, but if hosts are all equally loaded it may be that services will be recrated where they were removed from. This is the default setting of the Rancher scheduler. If you want ot override this then set the mode to ```AGGRESSIVE``` and this will force the scheduler to put the container on a different host by temporarily deactivating the current host.

Currently this excludes any services that use affinity rules

The source code is available at [https://www.github.com/chrisurwin/rancher-rebalancer](https://www.github.com/chrisurwin/rancher-rebalancer)

