- Orchestration in cloud terms is a means to create a set of cloud components (networks, VMs, storage, etc.) automatically in one simple action
- Instead of creating a network, then a VM, and the allocating a floating IP address, you can write a specification of what components are required and then invoke the specification to create all the components as one automated sequence
- The main OpenStack orchestration project is called HEAT and this has developed a standard way of orchestrating resources using descriptions called 'templates'. HEAT Orchestration Templates (HOTs) have a fixed structure and are written with YAML language
- Lines that start with # are comments
- The HEAT template version tells the system what version and thus what functions can be found in the template
	-  There is a range of different standards, each associated with a different date when the version was made current
	- The description is self explanatory (a human readable description of what the template does) and optional, but it is good practice to complete the description as it is intended to build up a repository of templates
	- The parameter_grpups section allows parameters to be grouped and ordered. This means that, for example, a login username and password can be grouped, and it is then obvious that they are associated. This allows client interface displaying the template to group them in the disloay in a logical fashion. Otherwise all parameters can only be listed in an arbitrary fashion.
	- The parameters section is for specifying inputs to the template, which can be provided when invoking or running the template. These are very much like the paramters passed into a function or procedure in a typical programming language. They can have default values which are used if no value is provided when the template is invoked
	- The resources section specifies what OpenStack resources should be created, such as instances, networks, routers, etc.
	- The outputs section allows the specification of parameters to be returned by the template after it has been created. These are optional
- Some of the sections are related to presenting the temlate in a client, perhaps as a form in a web page where the parameters can be listed with fields for values pre-filled with default values. When the template is running it can return information to be displayed, such as the IP address of a VM
-  Note that the named items (image, flavor and network) have to exist in the OpenStack installation for the template to have a chance of running successfully
-  Normally templates are more generally applicable and these elements would be passed as parameters to the template. The template above can be recast to use parameters with default values
- ![dfasfasda.JPG](../../_resources/dfasfasda.JPG)
- The parameters section here describes and gives default values for image, flavor, and network, and in the actual resource a template function get_param is used to get the specific value of the parameter to be used. Now when the template is called, an image name and flavor can be specfied; if these are not specified then the default values will be used
- The HEAT specification allows for 'environment' files that can be used in conjunction wiht a template to specify a range of elements including parameter values. So for example, the template above can have the parameter values removed to:
- ![fdsafasfda.JPG](../../_resources/fdsafasfda.JPG)
-  This template can then be used in conjunction with an environment file that specfies the parameter values:
	-  ![fddfsafs.JPG](../../_resources/fddfsafs.JPG)
-  The new template can then be used with any image, flavor, or network. To change any of these values only the environment has to be changed. It is important when you are editing YAML not to introduce non-printing characters. For example, problems with tabs have been senn, so avoid using them. Use a simple text editor such as Notepad to edit the YAML environment files
-  HEAT is very complicated, however the basic concepts and techniques remain much the same




