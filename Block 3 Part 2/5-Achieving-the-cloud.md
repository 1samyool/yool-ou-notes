**On-demand self-service**
- OpenStack certainly fulfils the goals of on-demand and self-service
- It offers a web-based interface and a set of APIs to manage all the stages of creating, managing and monitoring a cloud application
- The server, network, firewall and router only exist as software: all the traditional hardware elements have been replaced by software counterparts.

- Disk storage is also managed through software, drawing on large-scale storage services such as OpenStack’s Swift
- Hardware configurations such as RAID are no longer required because of the way that the storage services are configured for high availability.

**Broad network access**
- The NIST paper describes network access from an end-user’s perspective, the ability to access deployed applications – but there is also the issue of network access from a tenant’s perspective.
- A tenant needs network access to create, manage and monitor their application.

**Resource pooling**
- In the OpenStack example, pooling is evident in the way that all the nodes are shared by multiple tenants.
- The tenant won’t know, and doesn’t need to know, which node is performing which task.

**Rapid elasticity**
- Rapid elasticity is all about scaling up and down in proportion with demand.
- Although I haven’t gone into the details, OpenStack provides the tools to monitor the workload of an application and change the resources deployed as necessary.

**Measured service**
- OpenStack provides a rich variety of tools with which to monitor a tenant’s application and to measure the resources used.
- The information gathered can be viewed with the web interface or through calls to the API.