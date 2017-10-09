---
category: Building software
expires: 2018-03-29
---
# Managing interactions between services

Services need to interact with one another over APIs. They need to be
able to find one another, authenticate clients, be fault-tolerant,
scale appropriately in line with demand, and more.

## Principles

Services should be built on the assumption that [whatever network they
reside in is
insecure](https://en.wikipedia.org/wiki/Fallacies_of_distributed_computing).
It should be possible to deploy a new instance of a service to a new
environment (with appropriate configuration) and have it present an
appropriately-secured interface to the network.

A failure (including high latency) in a downstream service should not
inherently mean a failure in a consuming service, but it is not possible
for a third party service to accurately decide the appropriate response
in the case of a failure. Only the provider or consumer of the API can
have enough knowledge of failure states to handle them.

Handling increased load is best done at the level of the service.
Inserting a caching proxy, rate limiting layer, or other middleware, in
front of a suite of services assumes that all of those services have
similar usage and caching characteristics, and that they will need to
scale in the same fashion. If any one of them diverges from this, the
middleware will then have to scale in two (probably competing)
directions.

## Conclusion

As APIs grow their user-base, any management/middleware layer outside
the boundaries of the service itself becomes a bottleneck and a source
of errors and failures outweighing the benefits it offers.

Instead, management should be approached using something like the
[service
mesh](http://philcalcado.com/2017/08/03/pattern_service_mesh.html)
pattern: each service has its own dedicated layer responsible for the
service's reliability and security, monitored (and ultimately
orchestrated) by a sibling “control plane” service.
