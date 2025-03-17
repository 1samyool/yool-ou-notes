- Footprinting through search engines
	- Attackers use search engines to extract info about a target
		- Such as:
			- Tech platforms
			- Employee details
			- Login pages
			- Intranet portals
	- Can help the attacker to perform social engineering and other types of advanced system attacks
	- Major search engines used:
		- Google
		- Bing
		- Yahoo
		- Ask.com
		- Aol
		- Baidu
		- DuckDuckGo
		  
- Footprinting through web services
	- Search for the target company's external URL in a search engine, such as Google or bing
	- Sub-domains provide an insight into different departments and business units in an organization
	- You may find a company's sub-domains by trail and error method or using a service such as [Netcraft](https://www.netcraft.com)
	- You can use the Sublist3r python script, which enumerates subdomains across mulitple sources at once
	  
- Footprinting through social networking sites
	- Facebook, Twitter, LinkedIn, provide useful info about the individual that helps the attacker in performing social engineering and other attacks
	- The people search can provide critical info about a person or an org, including location, emails, websites, blogs, contacts, important dates, etc.
	- People search online services such as Spokeo, Intelius, pipl, BeenVerified, Whitepages, and PeekYou, provide people's names addresses, contact details, date of birth, photographs, etc.
	  
- Website footprinting
	- Refers to the monitoring and analysis of the target organization's website for info
	- Browsing the target website may provide the following info:
		- Software used and its version
		- OS used and its scripting platform
		- Sub-directories and parameters
		- Filename, path, database field name, or query
		- Technologies used
		- Contact and CMS details
	- Attackers use BurpSuite, Zaproxy, Wappalyzer, CentralOps, Website Informer, etc. to view headers that provide the following info:
		- Connection status and content-type
		- Accept-Ranges and Last-Modified
		- X-Powered-By Information
		- Web server in use and its version
		- Examining the HTML source code may provide:
			- Comments present in the source code
			- Contact details of the web developer or admin
			- File system structure and script type
		- Examining cookies may provide
			- Software in use and its behavior
			- Scripting platforms used
- Whois footprinting
- Footprinting through social engineering
	- Attackers use social engineering tricks to gather sensitive info from social networking websites
	- Attackers create a fake profile and then use the false identity to lure employees into revealing their sensitive information
	- Attackers collect information about the employee's interests and tricks them into revealing more information
- Network footprinting
	- Network range info assists attackers in creating a map of the target network
	- One can find the range of IP addresses using ARIN whois database search tool
	- One can also find the range of IP addresses and the subnet mask used by the target org from RIRs
- Email footprinting
	- Gathering email addresses related to the target org acts as an important attack vector during the later phases of hacking
	- Attackers use automated tools such as theHarvester and Email Spider to collect publicly available email addresses of the target organization that helps them perform social engineering and brute-force attacks
	  
- DNS footprinting
	- DNS records provide important info about the location and types of servers
	- Attackers can gather DNS info to determine key hosts in the network and can perform social engineering attacks
	- Attackers query DNS servers using DNS interrogation tools, such as SecurityTrails, NSLOOKUP, and DNS Records, to retrieve the record structure that contains info about the target DNS
	- Reverse DNS Lookup
		- Attackers perform a reverse DNS lookup on IP ranges in an attempt to locate a DNS PTR record for those IP addresses
		- Attackers use various tools, such as DNSRecon and Reverse Lookup to perform the reverse DNS lookup on the target host
		  
- Footprinting through job sites
	- A company's infrastructure details can be gathered from job postings
	- They look for:
		- Job requirements
		- Employee's profiles
		- Hardware information
		- Software information
	- Attackers use the technical info obtained through job sites, such as Dice, LinkedIn, or Simply Hired, to detect underlying vulnerabilities in the target IT infrastructure

- Deep and Dark Web Footprinting
	- Deep Web
		- It consists of web pages and contents that are hidden and unindexed and cannot be located using traditional web browsers and search engines
		- It can be accessed by search engines like Tor Browser and The WWW Virtual Library
		  
	- Dark Web or Darknet
		- It is the subset of the deep web that enables anyone to navigate anonymously without being traced
		- It can be accessed by browsers, such as TOR browser, Freenet, GNUnet, I2P, and Retroshare
	- Attackers use deep and dark web searching tools, such as Tor Browser and ExoneraTor, to gather confidential info about the target, including credit card details, passport info, identification card details, medical records, social media accounts, SSNs, etc.
 
	- TOR Browser
		- It is used to access the deep and dark web where it acts as a default VPN for the user and bounces the network IP address through several servers before interacting with the web
	 
- Finding IP Geolocation Information
	- IP geolocation helps to identify info such as country, region/state, city, ZIP/postal code, time zone, connection speed, ISP (hosting company), domain name, IDD country code, area code, mobile carrier, and elevation
	- IP geolocation lookup tools, such as IP2Location and IP Location Finder, help to collect IP geolocation info about the target, which in turn helps attackers in launching social engineering attacks, such as spamming and phishing


	 
