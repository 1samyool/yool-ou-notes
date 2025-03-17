NIST authors recognised the basic definition they offer was ill-suited as the basis for comparison of cloud services and deployment strategies.
- These service models more closely align to available offerings
- These service models still form the basis for much of the discussion about the cloud, even though it was published in 2011

The three service models defined by NIST are:
	- SaaS (Software as a Service)
	- PaaS (Platform as a Service)
	- IaaS (Infrastructure as a Service)


**Software as a Service (SaaS)**
- The capability provided to the consumer is to use the provider's applications running on a cloud infrastructure
- The applications are accessible from varioous client devices through either a thin client interface, such as a web browser (Ex: Gmail) or a program interface
- The consumer does not manage or control the underlying cloud infrastructure including:
	- Network
	- Servers
	- Operating systems
	- Storage
	- Individual application capabilities, with the possible exception of limited user-specific application confiugration settings
- In the SaaS model, the entire applicaton and hosting infrastructure is the responsibilitiy of the service provider
- All the tenant has to choose is the type of application

![dsafafadfa.JPG](../../_resources/dsafafadfa.JPG)

- The application block represents a single service (Ex: file storage) that is shared by multiple tenants
- Working from top to bottom, the tenants share the application, middleware, operating system, and hardware, but have thier own protected application data

- Examples of SaaS in the real world:
	- Netflix
	- Dropbox

- Organisations can also use SaaS mdoel to provide email, word processing, and other 'office' tools for their employees

- A popular trend is for application developers, for example Adobe, to convert from stand-alone applications to a web-based SaaS delivery model
- The SaaS model gives the developer greater control since they deploy to a known environment in the cloud rather than distributing thousands of copies to individual users.


**Platform as a Service (PaaS)**

- The capability provided to the consumer is to deploy onto the cloud infrastructure consumer-created or acquired applications created using programming languages, libraries, services, and tools supported by the provider.
- The consumer does not manage or control the underlying cloud infrastructure including netowrk, servers, operating systems, or storage, but has control over the deployed applications and possibly configuration settings for the application-hosting environment

- In this model, the tenant creates the application that is to be hosted by the PaaS provider.
- For example, the tenant might contract for a web server with scripting engine plus a database server, but have limited choice over the operating system or the database engine

- Tenant's options cover both the application and its data, but the middleware, operating system, and hardware remain under the control of the service provider

![dsfafdafa.JPG](../../_resources/dsfafdafa.JPG)

- Although similar to conventional web hosting, most PaaS providers add value by way of pluggable services such as authentication and authorisation, email, user interface components, and an API to monitor and manage the application.

- PaaS examples:

	- AWS
	- Google App Engine
	- Microsoft Azure
	- Oracle Cloud


**Infrastructure as a Service (IaaS)**
- The capability provided to the consumer is to provision processing, storage, networks, and other fundamental computing resources where the consumer is able to deploy and run arbitrary software, which can include operating systems and applications
- The consumer does not manage or control the underlying cloud infrastructure but has control over operating systems, storage, and deployed applcations
- Possibly limited contorl of select networking components (Ex: firewalls)

-In this model, the tenant takes on responsibility for most of the applciation, but not the computer or networking infrastructure
- In traditional computing terms, IaaS is comparable to renting a dedicated host to run a web server or database server

- The tenants options now include the middleware, but the hardware and operating system remain under the control of the service provider

- Inclusion of the operating system reflects the fact that the article was based on specific IBM commercial offerings

- The majority of IaaS providers offer tenants a choice of operating system, albeit one taken from a restricted set of 'flavors'

![fasdfafda.JPG](../../_resources/fasdfafda.JPG)

Examples of IaaS providers:
	- AWS Elastic Compute Cloud (EC2)
	- Rackspace
	- Microsoft Azure
	- Google Compute Engine

IaaS cloud based on OpenStack

SaaS, PaaS, IaaS are the key to understanding how the cloud has evolved




  



