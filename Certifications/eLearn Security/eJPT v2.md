# This is the Cheatsheet of eJPT v2 Course material by INE

Tags: #⚙️
Related to: [[eJPT]]
See also: 
Previous: 

## <u>Section: Information Gathering</u>

### Passive information Gathering:

 **Website Recon and footprinting**

1. host  
	  - See [[host]] 
```
$ host google.com
```

2. Crawl the website
	
	i.  Check for robots.txt
	EX: `https://google.com/robots.txt`
	ii. Check for sitemap.xml orsitemaps.xml 
	EX: `https://google.com/sitemap.xml`

    
3. Get some browser extensions

    i.  BuiltWith
    ii. Wappalyzer

    
4. Whatweb Command

        $ whatweb google.com         
        $ whatweb <IP Address> 
        
    
5. Download the entire website to analyze structure and source code

    - Visit [HTTRack](https://www.httrack.com/)

    or
    ```
    $ sudo apt install webhttrack 
    $ httrack
    ```

**Whois Enumeration**

1. whois 

	- See: [[whois]]

	- Or goto [whois](http://who.is) to enumerate

2. host command to get IP of a domain. See [[host]]
```
┌──(xron㉿Trix)-[~]
└─$ host google.com
```
```text
google.com has address 142.250.192.46
google.com has IPv6 address 2404:6800:4009:828::200e
google.com mail is handled by 10 smtp.google.com.
```

**Netcraft Enumeration**

 - Visit [Netcraft](https://www.netcraft.com/) and go to site report section, then put the domain of the websit to get a lot more information about the site. Like: DNS information, IP Address...etc

**DNS Enumeration**

1. [dnsdumpster](https://dnsdumpster.com/)
2. [kali-repo](https://www.kali.org/tools/dnsrecon/)
3.  dnsrecon

	Usage Example: See [[dnsrecon]]

**wafw00f**

- See [[wafw00f]]

**Sublist3r**

 - See [[sublist3r]]

**theHarvester**

- See: [[theharvester]]

### Active Information Gathering

**DNS Zone Transfer**

1. dnsenum
	- See [[dnsenum]]
1. dig
	- See [[dig]]
1. fierce
	 - See [[fierce]]

**Host Discovery**

Related: [[nmap]], [[netdiscover]], [[ip]]

1. ip    // Get IP informetion in different interface

```
┌──(xron㉿Trix)-[~]
└─$ ip a s
```
```text
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host 
       valid_lft forever preferred_lft forever
2: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP group default qlen 1000
    link/ether 00:0c:29:84:b2:f5 brd ff:ff:ff:ff:ff:ff
    inet 192.168.11.129/24 brd 192.168.11.255 scope global dynamic noprefixroute eth0
       valid_lft 1405sec preferred_lft 1405sec
    inet6 fe80::20c:29ff:fe84:b2f5/64 scope link noprefixroute 
       valid_lft forever preferred_lft forever
```

2. nmap

```
┌──(xron㉿Trix)-[~]
└─$ sudo nmap -sn 192.168.0.0/24
```
 - -sn option disables port scan
```text
Starting Nmap 7.93 ( https://nmap.org ) at 2023-02-25 14:57 IST
Nmap scan report for 192.168.0.0
Host is up (0.0035s latency).
Nmap scan report for 192.168.0.1
Host is up (0.00067s latency).
Nmap scan report for 192.168.0.2
Host is up (0.0034s latency).
```

3. netdiscover

	- See [[netdiscover]] 