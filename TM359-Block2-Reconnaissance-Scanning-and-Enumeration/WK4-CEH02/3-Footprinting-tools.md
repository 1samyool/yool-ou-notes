- Common tools
	- Maltego
		- can be used to determine the relationships and real world links between people, groups of people, organizations, websites, internet infrastructure, etc.
		  
	- Recon-ng
		- A web reconnaissance framework with independent modules and database interaction, which provides an environment in which open source, web-based reconnaissance can be conducted
		  
	- FOCA
		- Tool used mainly to find metadata and hidden info in the documents it scans
	- OSR framework
		- inlcudes applications related to username checking, DNS lookups, information leaks research, deep web search, regular expressions extraction, etc.
		  
	- Recon-dog
	- BillCipher
	- Spyse
	- OSINT framework
 
	- Web Spider
		- Web spiders, such as Web Data Extractor and ParseHub
		- Perform automated searches on the target website
		- Collect specificed info, such as employee names and email addresses
		- Attackers use the collected info to perform footprinting and social engineering attacks
		- User-Directed Spidering
			- Attackers use standard web browswers to walk through the target website functionalites
			- The incoming and outgoing traffic of the target website is monitored and anlayzed by tools that include features of both a web spider and an intercepting proxy
			- Atttackers use tools such as Burp Suite and WebScarab to perform user-directed spidering
	  
- Additional tools
	- theHarvester
		- Attackers use this tool to perform enumeration on LinkedIn and find employees of the target company along with their job titles
		- Attackers can use this information to gather more info, such as current location and educational qualifications, and perform social engineering or other kinds of attacks
		  
	- Shodan
		- Search engine that lets you find connected devices (routers, servers, IoT, etc.) using a variety of filters
		  
	- Google hacking
		- GHDB is an authoritative source for querying the ever-widening reach of the Google search engine
		- Attackers use Google dorks in Google advanced search operators to extract sensitive information about their target, such as vulnerable servers, error messages, sensitive files, login pages, and websites
		  
	- Netcraft
	- Sublist3r
	- Sherlock
	- BurpSuite
	- HTTrack
	- Archive.org
	- Photon
	- CEWL
	- ExifTool
	- Infoga
 
	- Whois
		- Whois databases are maintained by Regional Internet Registries and contain personal information of domain owners
		- Whois query returns:
			- Domain name details
			- Contact details of domain owners
			- Domain name servers
			- NetRange
			- When a domain was created
			- Expiry records
			- Last updated record
		- Info obtained from Whois database assists an attacker to:
			- Gather personal info that assists in social engineering
			- Create a map of the target org's network
			- Obtain internal details of the target network
		- Regional Internet Registries (RIRs)
			- ARIN
			- AFRINIC
			- RIPE NCC
			- LACNIC
			- APNIC
		
	- DNSRecon
 
	- Traceroute
		- Series of outbound requests with incrementing TTL values
		- Traceroute programs work on the concept of ICMP protocol and use the TTL field in the header of the ICMP packets to discover the routers on the path to a target host
		- Attackers execute traceroute to find the IP addresses of intermediate devices such as routers and firewalls present between a source and its destination
		- By compiling this info, attackers can identify the intermediate devices or hosts in the path to the target network