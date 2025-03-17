NIST document defines a set of five essential characteristics
	- On demand self service
	- Broad network access
	- Resource posing
	- Rapid elasticity
	- Measured service

Provision - creating the infrastructure to host an application

On-Demand Self-Service
- A consumer can unilaterally provision computing capabilities, such as server time and network storage, as needed automatically without requiring human interaction with each service provider
  	- Consumer refers to owner of hosted application
  	- For example:
  		- A company providing Office 365 to its employees
	- Not the end user of application
	- IP addresses and DNS entries for hosts must be assigned dynamically


Broad Network Access
- Capabilities are available over the network and accessed through standard mechanisms that promote use by heterogenous thin or thick client platforms (mobile phones, tablets, laptops, and workstations)
	- Standard mechanisms = TCP/IP, HTTP, CSS, HTML
	- Less obvious = standards for routing, domain name service, video and audio file formats


Resource Pooling
- The provider's computing resources are pooled to serve mutlitple consumers using a multi-tenant model
- Different physical and virtual resources dynaimically assinged and reassigned according to consumer demand
- Sense of location independence becuase the customer generally has no control or knowledge over the exact location of the provided resources but may be able to specify location at a higher level of abstraction (country, state, datacenter)
- Examples:
	- Storage
	- Processing
	- Memory
	- Network Bandwidth
- Similarities with conventional shared web hosting in that each customer is one of multiple tenants sharing a single web server (the resource) and the customer has little control as to where the shared server is located
- Key difference:
	- In the cloud: Dynamically as and when required
		- So the customer can add more processors, memory, and disk storage to their server
	 

Rapid Elasticity
- Capabilities can be elastically provisioned and released, in some cases automatically, to scale rapidly outward and inward commensurate with demand
- To the consumer, the capabilities available for provisioning often appear to be unlimited and can be appropriated in any quantity at any time
- Most distincitive characteristic of the cloud
- Abilitiy to increase resources as demand rises and dispose of resources as demand falls
- Traditional web hosting model = expensive
- Cloud solution permits scaling on demand


Measured Serviice
- Cloud systems automatically control and optimize resource use by leveraging a metering capability at some level of abstraction appropriate to the type of service (storage, processing, bandwidth, and acive user accounts)
- Resource usage can be monitored, controlled, and reported, providing transparency for both the provider and consumer of the utilized service
- Measuring and monitoring are not unique to cloud computing
- Traditional web hosting typically includes charges for data storage and transmisiion across the network and monitoring tools to assess performance
- Management tools are more powerful, allowing full conrol of a cloud thorugh an application programming interface (API)

