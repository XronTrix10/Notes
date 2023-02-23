# Information Gathering

## IP Address or Host Name Gathering
```
1. ping - To Gain IP Address

2. nslookup - To gain more information || “ nslookup -querytype=ANY <Domain Name> ” - To get more information || “ nslookup -querytype=NS <Domain Name> ” - For getting nameserver details

3. whois - More Information

4. google Ip checker (ipinfo.info) - Gain details about IP Address or a certain Domain

5. whatweb - default scan level is 1 

6. nikto - get information about a live website - type “nikto -h <IP Address || web address>”  ( -h for host )

7. host - type ‘’ host <Domain Name> ‘’ to get IP addresses , Name server and lot more  

8. use netcraft to get more information

9. firece tool is usefull for subdomain enumeration || “ fierce --domain <domain name> ” || Type “ fierce -h ” for more info

10. Some github Tools - 
	i. dnsrecon
	ii. dnsenum
	iii. subbrute
	iv. fierce
	v. dnsenum
	vi. knock
	vii. recon-ng 
```

## Email Gathering
```
1. theHarvester - A tool to gather information about emails

2. Hunter.io - This website also helps
```

# Scanning
```
1. sudo arp --help
2. sudo arp -av

3. sudo netdiscover - Most powerful Tool to discover all IP addresses

4. netstat -nr => To check the IP address of the router or the gateway.

5. nmap <IP Address>

6. nmap -sS <IP Address>

7. sudo nmap -sT <IP Address>

8. nmap -sU <IP Address>

9. nmap -O <IP Address> - To get Operating System details

10. gobuster dir -e -u <domain name> -w <path to wordlist> 
```

# Vulnerability Analysis

## Scanning with nmap
```
1. nmap --script <group of script> -sS <IP Address>
```
Visit https://nmap.org/book/nse-usage.html to know about all kind of script groups

	EX: sudo nmap --script malware -sS -F 192.169.0.101 ( -F for only 100 ports for faster scanning )
  
```
2. nmap --script-help <script name> (know about a specific script) ( All scripts are present at /usr/share/nmap/scripts )
	
3. nmap --script <script name> <IP Address> (Run a specific script against a target)
```

## Google Dorking
```
1. Run "sudo nmap -sV <IP Address>" to get the version info of running services and google it
```
**Search Pattern example:** vsftpd 2.3.4 exploit

## Searchsploit

-searchsploit <Serivice name> ( Know about the service if it is exploitable )
Example:

    searchsploit vhstp
	
## Scanning with Nessus

- Start Nessus by - 
```
/bin/systemctl start nessusd.service
```
### Then visit http://localhost:8834
