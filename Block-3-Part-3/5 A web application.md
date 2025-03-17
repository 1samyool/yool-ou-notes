- Components that make up a standard web application
	- User requests from clients are sent across the internet to arrive at the web server
	- There can be of course be other infrastructure, such as networks and routers, but these don't change the basic operation of the HTTP request-response protocol
	- User requests arrive at the srver having been routed by DNS servers, etc. to the correct IP address.
	- The server has a single static IP address on the internet
	- ![dafsafdasd.JPG](../../_resources/dafsafdasd.JPG)
- All requests to ther server come via the single IP address, and as the number of requests rises the server will start to slow in its response time.
	- Adding more resources to the architecture to help serve the increasing volume of requests is problematic.
	- Adding memory or a CPU to the server would normally mean shutting it down for a time.
	- Adding anohter machine to share the load is problematic because all requests go directly to the existing server
	- One solution is to introduce a load balancer (LB) to the intial architecture
- ![dafdssafas.JPG](../../_resources/dafdssafas.JPG)
- To create a load balanced infrastructure in OpenStack we can use the 'load balancer as a service' approach available in OpenStack
	- ![dafdadfafa.JPG](../../_resources/dafdadfafa.JPG)
- The load balancer has a floating IP address to which it repsonds just as you saw earlier when using a single VM
	- Behind this set of listeners handle specific requests using different protocols or ports
	- In figure 3 there are two listeneers for HTTP and HTTPS shown
	- The listeners route requests to and from a pool of VMs that can respond to the requests
	- A pool component groups a set of one or more member VMs together
	- The pool of VMs is also monitored by a health monitor which ensure that requests are not sent to VMs which are not responding
- In OpenStack we can add a load balancer to the infrastructure, and that will allow us to add VMs dynamically when the load increases.
	- To do this automatically, OpenStack allows us to set up the LBaaS infrasturcture which is described later
- The load balancer is an additional component extending the architecture so that it takes the place of the server in receiving incoming requests from the web
	- It listens for requests on the IP address which is externally visible to users and then handles incoming requests by sending them to one of the multiple servers to which it is connected.
	- There are a few considerations that the balancer has to account for in order to improve the applications performance and reliabilty
- The first consideration is that sessions are maintained.
	- So when a request comes in, the LB will route it to one of the servers
	- At some point in time it will expect to receive a response from the server and iwll then pass the response back to the originating client
	- If the LB receives any other requests from the same client it has to pass them to the same server which may have retained some inforamtion for a session
	- So if the client has sent login credentials then the server that checked these will have retained that information and will be ready to allow the client access to protected resources
	- The other servers, where the user might have logged in but hasn't, will not have the login credentials and will thus not be prepared to allow any access
- Another consideration is server failure
	- In OpenStack, an instance can be monitored by a 'health monitor'
	- In fact, an OpenStack monitor willl monitor all VMs if these are grouped together into what is called a 'pool'
	- In this way, when a new VM is started it is added to the pool and then the monitor will automatically monitor the new VM in addition to existing instances
- If a health monitor finds out that an instance is not running it will remove it
	- A health monitor is specificed as having a 'type', which is the protocol to use in talking to an instance (HTTP, TCP, etc.)
	- Several monitors can be set up to monitor a single pool
	- It also has specified a time between messages to a VM, the number of tries to attempt to connect to a VM before declaring failure, and how long to wait before timing out trying to connect
- A simple declaration for a monitor is given below
	- This monitor uses TCP to connect to a VM and will do so every 5 seconds, allowing 4 seconds to establish a connection and up to three attempts if it fails to connect. This resource type is documented in the resources list under the 'Orchestration' tab in your OpenStack project
	- The pool represents the collection of VMs that run on the local network
	- All member of the pool then have their health monitored, including new VMs when added as needed
	- ![dafadfaf.JPG](../../_resources/dafadfaf.JPG)
- Another consideration is how the LB chooses which server to pass requests on to
	- With one server there is only one possibility, but with two or more servers the LB needs to decide which server it should pass the next incoming request on to
	- A simple way to do this would be to pick each server in turn
	- So if there are 3 servers, A B and C, the LB would pass the first request to A, the next to B, and the third to C, then back to A for the fourth and so on
	- This approach is known as a **round-robin** approach or algorithm
	- The problem with this approach is that one request may take considerably longer to respond to than another, especially if the server has to do a lot of work
	- For example, getting data from a database and then sorting and formatting the data for presentation takes longer and more resources than simply serving up a static HTML page
	- So another common approach is to sample the load on each server and select the server that is least loaded
	- This requires a more sophisticated LB, and incurs an overhead in assessing the load on servers
	- In OpenStack a number of different algorithms are available
- An example of a HEAT load balancer is given below
	- The blancer is associated a subnet where the pool of VMs will be run and to which it will allocate a Virtual IP (VIP) address for the load balancer to be contact on (rather than users contacting a specific VM directly)
	- ![dfafdsafdafd.JPG](../../_resources/dfafdsafdafd.JPG)
- The load balancer is also given a floating IP address that will be used to receive requests to the pool
- The IP address is on the external network so it can operate there, and the port is declared to be the load balancers VIP address
- ![fasfad.JPG](../../_resources/fasfad.JPG)
- In OpenStack  the actual laod balancer algorithm is specified in the pool specificaton as shown below where ROUND_ROBIN is named
- Other options are LEAST_CONNECTIONS and SOURCE_IP
- This last option generates a VM selecton based on the client's IP, which means that it will always talk to the same VM even outside a normal session
- ![dfasfdsafa.JPG](../../_resources/dfasfdsafa.JPG)
- Whilst OpenStack itself collects data about the VM's loads in order to facilitate aspects such as billing for resources and autoscaling, for autoscaling it is necessary to specify two more items: alarms and scaling policy
	- An alarm is simply a device which regularly asseses the monitoring data from OpenStack against a set of criteria
	- When the criteria are met, the alarm is triggered and a scaling policy is applied to alter the autoscaling group pool by adding or removing resources as specified in the policy
	- An example of a scaling policy is shown below
	- This is a policy which will add one instance to the autoscaling group
	- The cooldown period is the time that must pass before the alarm can fire again
	- This prevents multiple signals form the same alarm form prompting several instances to be launched
	- When the first alram fires it may take some time to launch the new instance and for it to start sharing the load
	- so the cooldown period shoould be longer thatn the time for a new instance to come online
	- ![dasfafdadfafd.JPG](../../_resources/dasfafdadfafd.JPG)
- An example alarm is illustrated below
	- This alarm is set on the CPU 'cpu_util' of instances in the pool and will fire when the CPU reaches 50%
	- The granularity property specifies how long the CPU has to be above 50% for the alarm to run
	- This means that the system will check the CPU usage has remained greater than 50% for one minute
	- There is however a time scale which OpenStack uses to sample data and the granularity has to be a factor which respects or conforms to this
	- Here it is quite a long time but that will ensure the alarm works with the current OpenStack setting
	- The collection of data is currently at a low elvel, which means every 5 minutes over a period f 30 days
	- So when the alarm condiitons are met we mayhave to wait several minutes for the state of the alarm to actually change
	- The alarm action is a URL which points to the declaration of the scale-up policy also declared in the stack
	- The query is a string which is matched against information OpenStack records
	- In this case the query is given the name 'server_group' and a value which is actually the ID of the stack when it is run
	- This will be a unique ID so the data used to trigger alarms can be restricted to contain this stack's ID
	- Whenever you see a template and params as part of a property such as alarm_actions, it will generallyt be the case that the template is a sring which has values put in which are taken from the params previously listed
- ![fdsfasdaf.JPG](../../_resources/fdsfasdaf.JPG)
- The most significant part of the autoscaling resources to examine is the important autoscaling group
	- An example is given below
	- This is quite complicated because it includes a reference to anohter YAML file using a URL
	- That file specifies the resources to be load balanced, but those are actually just a VM server instance
	- Parameters are passed down to that file relating to running the instancee and enclosing stack ID
	- The key parts of the specification are that it defines the item to be scaled (the resource) and the minimum and maximum size of the pool
	- ![sdfasfdasfa.JPG](../../_resources/sdfasfdasfa.JPG)














 




