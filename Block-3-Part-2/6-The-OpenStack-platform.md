**6.1 OpenStack architecture**
- Consists of an extensive set of independent services
- OpenStack dashboard is a webpage called Horizon
![fdaafaa.JPG](../../_resources/fdaafaa.JPG)
- Networking service, called Neutron, is concerned with providing connectivity for VM instances so that they can interact with the outside world, usually on company intranet or internet
- Compute service, called Nova, is concerned with managing VM instances
	- It can manage very large pools of VMs, scaling horizontally, and is very flexible in working with wide range of virtualisation technologies, such as Docker, which provide containers
	- Containers are seen as important development, and container support has been integrated into OpenStack by the Magnum project
- Image service, called Glance, manges the storage of VM images and isk images ina range of different back-ends
- There are two types of storage in basic architecture:
	- block storage provided by a service called Cinder
	- object storage provided by a service called Swift
- Swift is the older project of the two and is used to store large objects as single items
- Glance stores images in Swift, for example Swift is distributed and produces redundant copies of objects across a network to ensure robustness and speed
- Cinder's block stoage provides storage volumes for compute
- The identity service, called Keystone, ensures that users have provided appropriate credentials, and should be allowed access to the services being requested

**6.2 Accessing OpenStack**
- In general, there is 4 approaches to access
	- 1) Horizon Dashboard
		 - Simplest method
	 - 2) CLI
		 - Each service has a CLI
		 - Commands can be issues from a shell or console
	 - 3) Python APIs
		 - Provides similar access as CLI, but programatically
	 - 4) YAML
		 - Declarative scripting approach
		 - In OpenStack terminology, a YAML description, which can create any number of resources and actions, is called a "Stack"

**6.3 OpenStack at the OU**
- This version of OpenStack we use is called Xena
![fasdafda.JPG](../../_resources/fasdafda.JPG)
  





 