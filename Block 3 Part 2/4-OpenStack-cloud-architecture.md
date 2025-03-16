- Two main differences between OpenStack and AWS are:
	- OpenStack is an open-source project so you have access to the source code, whereas AWS is a proprietary solution which you can use but not download or change
	- AWS is an outsourcing solution, so AWS runs on machines owned and maintained by AWS. In contrast, OpenStack can be downloaded and run on your own machines. However, there are also outsourcing providers that run OpenStack for you and other companies that provide support if you do want to run your own OpenStack. The OpenStack platform at the OU is a supported RedHat variant, for example.
- Both cloud options provide for autoscaling of VM instances based on rules defined by the tenant
- The rules can be based on the amount of network traffic received or on a timed schedule
- OpenStack is an open source IaaS project
  

![fdasfasdfa.JPG](../../_resources/fdasfasdfa.JPG)

- Most equipment in top half of diagram performs exactly same as traditional network
- Firewall requires some changes, must open up extra ports that will handle traffic for the cloud
- Local DNS server will be responsible for handling new websites as they are created dynamically in the cloud
- No NAT function in the architecture, NAT is used in the clouds
- Bottom half of diagram contains elements that make up the cloud
- Five key blocks:
	- Controller
	- Network
	- Compute
	- Images
	- Storage
- First 3 represent computer hardware, last 2 represent disk storage to support the cloud function
- Hardware is interconnected by three separate networks
	- One handles management traffic and data between computers
	- One handles network traffic to and from the website
	- One carries the internet traffic exhanged with the cloud


**4.1 Controller node**
- Controller node is responsible for managing the cloud
- It schedules new VMs to start and stop
- It manages the images used to create VMs
- It handles authentication for cloud admins and tenants
- It gathers detailed info about cloud usage
- All this is achieved by running services (programs launched at startup and continue to run in the background)
- Controller node decides where a VM will be created based on the flavor chosen and the resources (proccessor, memory) available on the compute nodes

**4.2 Network node**
- The network node is responsible for managing the network elements that are used by VMs to communicate with the internet
- Includes assinging IP addresses to VMs, routing traffic amongst the VMs and between the VMs and internet
- The solution is based on the use of services running on the network node that mimic the internetwork layer and the data link layer of the OSI protocol stack
- Recall that Hoff's model included a breakdown of these networking elements
- Once a VM has been launched by the controller node, a message is sent to the netowrk node to create the various networks required by the VM
- The network node uses the info about the VMs network interfaces to assign IP addresses, and set up routes for data flows
- First IP address assigned is for a private network linking the VM to the network node, and allows various cloud nodes to communicate with the VM
![uytdyut.JPG](../../_resources/uytdyut.JPG)
- The network node also creates the equivalent of a firewall to protect the VM
- Creates a security group that contains details of the accessible ports on the VM and the user accounts which are permitted access to the services running on those ports
- If the VM needs to communicate with the internet it must be assinged a proper IP address that will be used solely for internet traffic
- OpenStack refers to this as a 'floating IP address'
- The network node software also creates the necessary routes for the VM's internet traffic
- OpenStack network node has optional services that can provide the functionality of load balancing and firewall protection


**4.3 Compute node**
- Host computer for the guest VMs
- When a new VM is to be launched, the controller nodes posts a message to the selected compute node and the compute node loads the image from the image storage device
- Compute node also runs a network service that configures the various interfaces and bridges that the VM will use to communicate internally and externally
- Recall that all VM network traffic must use the host computers network interfaces, so the compute node needs to know how to connect to the various services on the network node
- In place of hardware router aeach VM uses a software defined route table that dfinest he addresses to be used for exchanging data, both between collaborating VMs and an internet gateway
- By default, VMs are allocated ephemeral storage, sufficient to allow the VM to go through its bootup process and store temporary data
- When the VM shuts down, all temp data is discarded
- If persistent storage is required, perhaps for logging data, it must be created in the form of a virtual disk drive, or volume, and linked to the VM at launch time
- The compute node also gathers info about the VMs activities so that tenants can b echarged for the resources that they use
- The data is passed to a message queue so that it can be collected by the appropriate service running on the controller node

**4.4 Images**
- The images block represents the disk storage used for VM images and it is managed by one of the services running on the controller node
- New images can be loaded or removed by tenants, shared between tenants, or marked as private for use by a single tenant

**4.5 Storage**
- Storage block represents disk storage used for persistent data required by the VMs
- It too is controlled by a service running on the controller node
- The storage takes form of a virtual disk drive that can be attached to an individual VM running on a compute node
- It could be used to store static web pages and images, dynamic pages and web server logs

**4.6 Management**
- OpenStack cloud has two modes of control, a web-based interface and a set of application programming interfaces (APIs) for use with RESTful web services
- Using these tools, a tenant can launch new instances, create and edit flavors, load and unload images, create storage voumes and monitor usage

**4.7 A website**
- The website for an application can be created entirely through the OpenStack management interface using a combination of the services running on the controller, network and compute nodes
- No further hardware is required: everything is achieved through software
- Initially a single web server image and a database server image would be created and saved to the images node
- From here they can be used as the basis for as many VMs as required
- The database would be allocated persistent storage by means of a volume saved to the storage node
- The database will be shared between as many web servers as required, so some careful planning of the database design will be necessary
- When launched, the web server VM would be connected to the internet and a private network established between the web and database servers
- The website VM will be monitored by the controller node and, if necessary, another instance will be launched to help with the workload
- A load balancer service would be launched to distribute the requests between the available servers

**4.8 Further options**
- There are too many single points of failure for this to be a viable commerical cloud offering
- To make the cloud more resilient, we can turn to traditional clustering models such as active/active or active/passive
- We could also introduce multiple controller an dnetwork nodes and load balance them in the traditional way
- 

