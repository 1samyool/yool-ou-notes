In the first part, you learned about basic cloud definitions and models. The NIST (National Institute of Standards and Technology) cloud definition, even though it was written in 2011, is still widely used. It describes the main features and ways to use and set up the cloud, but it doesn’t give every detail you might need to make decisions. Other models (like those from USBC+IBM and Hoff) give a clearer picture of how the cloud really works and how offering services has changed things.

In the second part, we looked at virtualization and scaling, two key ideas behind the cloud.

Virtual Machines (VMs):

	A VM is like having a whole separate computer running on top of another computer’s operating system (the “host”).
	The host has something called a “hypervisor” that keeps different VMs apart and manages their memory and devices.
	

Containers:

	A container only has the application and the files it needs, and it shares the host’s operating system directly (so it doesn’t need its own OS).
	Containers are therefore smaller and start up much faster (in seconds rather than minutes).
	Scaling-out means adding more computers or servers to handle extra work. This usually involves load balancing, which spreads tasks across these servers. Cloud providers often use a few “template” VM setups (called flavors) to keep things simple.

Finally, creating a new VM or container is only part of running things in the cloud. You also need:

	Load balancing for scaling,
	Networking so everything can talk to each other and to the internet,
	Security to control who can access what.
	
All these extra services must be set up automatically whenever you add a new VM to the cloud.