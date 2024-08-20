### private cloud-computing model

- Segments networks
- Restricts access to instances through firewalls
- Creates static routes to forward traffic
- Can have subnets

## Auto mode

- Default network
- One subnet per region
- Regional IP allocation
- Fixed /20 subnetwork per region
- Expendable to /16
- Suitable for isolated use
## Custom Mode

- No default subnets
- Full control of IP ranges
- Regional IP allocation
- Expendable to IP ranges
- Suitable to production environments


It has a routing table, so you don't have to provision or manage a router. It forwards traffic from one instance to another.

They don't need a firewall because you can limit traffic with tags.


