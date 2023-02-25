# 🗃 EH Zero to Mastery

Tags: #🗃 
Related to: [[eJPT v2]], [[eJPT]]
See also: [[eJPT v2]]

## Information Gathering

### IP Address or Host Name Gathering


1. ping - To Gain IP Address
	 - See [[ping]]

3. nslookup 
	 - See [[nslookup]]

5. whois - for more Information

	 - See [[whois]]

7. Visit [ipinfo](https://ipinfo.info) - Gain details about IP Address or a certain Domain

9. whatweb 
	- See: [[whatweb]] 

11. nikto

	- See [[nikto]]

13. host 
	- See [[host]]

15. use [Netcraft](https://netcraft.com) to get more information

16. firece tool is usefull for subdomain enumeration
	  - See: [[fierce]]

18. Some github Tools - 

	i. dnsrecon - [[dnsrecon]]
	ii. dnsenum - [[dnsenum]]
	iii. subbrute - [[subbrute]]
	iv. fierce - [[fierce]]
	v. dnsenum - [[dnsenum]]
	vi. knock - [[knock]]
	vii. recon-ng - [[recon-ng]]



### Email Gathering

1. theHarvester - A tool to gather information about emails
	 - See: [[theharvester]]

3. [Hunter.io](https://hunter.io) - This website also helps


### Scanning
```
1. sudo arp --help
2. 
3. sudo arp -av
4. 
5. sudo netdiscover - Most powerful Tool to discover all IP addresses

6. netstat -nr => To check the IP address of the router or the gateway.

7. nmap <IP Address>

8. nmap -sS <IP Address>

9. sudo nmap -sT <IP Address>

10. nmap -sU <IP Address>

11. nmap -O <IP Address> - To get Operating System details

12. gobuster dir -e -u <domain name> -w <path to wordlist> 
```

## Vulnerability Analysis

### Scanning with nmap
```
1. nmap --script <group of script> -sS <IP Address>
```
Visit https://nmap.org/book/nse-usage.html to know about all kind of script groups

	EX: sudo nmap --script malware -sS -F 192.169.0.101 ( -F for only 100 ports for faster scanning )
  
```
2. nmap --script-help <script name> (know about a specific script) ( All scripts are present at /usr/share/nmap/scripts )
	
3. nmap --script <script name> <IP Address> (Run a specific script against a target)
```

### Google Dorking
```
1. Run "sudo nmap -sV <IP Address>" to get the version info of running services and google it
```
**Search Pattern example:** vsftpd 2.3.4 exploit

### Searchsploit

 - See [[searchsploit]]
```
┌──(xron㉿Trix)-[~]
└─$ searchsploit vsftpd
```
```text
---------------------------------------------- ---------------------------------
 Exploit Title                                |  Path
---------------------------------------------- ---------------------------------
vsftpd 2.0.5 - 'CWD' (Authenticated) Remote M | linux/dos/5814.pl
vsftpd 2.0.5 - 'deny_file' Option Remote Deni | windows/dos/31818.sh
vsftpd 2.0.5 - 'deny_file' Option Remote Deni | windows/dos/31819.pl
vsftpd 2.3.2 - Denial of Service              | linux/dos/16270.c
vsftpd 2.3.4 - Backdoor Command Execution     | unix/remote/49757.py
vsftpd 2.3.4 - Backdoor Command Execution (Me | unix/remote/17491.rb
vsftpd 3.0.3 - Remote Denial of Service       | multiple/remote/49719.py
---------------------------------------------- ---------------------------------
Shellcodes: No Results

```
### Scanning with Nessus

- Start Nessus by - 

`sudo /bin/systemctl start nessusd.service`
`firefox http://localhost:8834`

### Try Different

- If you don't get any specific version of the running service then try to run version detection by running scanners of Metasploit Framework

 - If you don't get any result from ‘Searchsploit Tool’ , then try to google it

## Exploitation

### Metasploit

See: [[metasploit framework]] and [[Using the Metasploit-Framework]]

## Post Exploitation

**UAC** - user account control

 - after successfully gaining access to the target machine, we need to get the administrator or root priviledge

 - To do that, wee need to bypass uac.

 - For that, background the current session with _bg_ and search for scripts in metasploit framework -

	`search bypassuac`

```text
msf6 > search bypassuac

Matching Modules
================

   #   Name                                                   Disclosure Date  Rank       Check  Description
   -   ----                                                   ---------------  ----       -----  -----------
   0   exploit/windows/local/bypassuac_windows_store_filesys  2019-08-22       manual     Yes    Windows 10 UAC Protection Bypass Via Windows Store (WSReset.exe)
   1   exploit/windows/local/bypassuac_windows_store_reg      2019-02-19       manual     Yes    Windows 10 UAC Protection Bypass Via Windows Store (WSReset.exe) and Registry
   2   exploit/windows/local/bypassuac                        2010-12-31       excellent  No     Windows Escalate UAC Protection Bypass
   3   exploit/windows/local/bypassuac_injection              2010-12-31       excellent  No     Windows Escalate UAC Protection Bypass (In Memory Injection)
   4   exploit/windows/local/bypassuac_injection_winsxs       2017-04-06       excellent  No     Windows Escalate UAC Protection Bypass (In Memory Injection) abusing WinSXS
   5   exploit/windows/local/bypassuac_vbs                    2015-08-22       excellent  No     Windows Escalate UAC Protection Bypass (ScriptHost Vulnerability)
   6   exploit/windows/local/bypassuac_comhijack              1900-01-01       excellent  Yes    Windows Escalate UAC Protection Bypass (Via COM Handler Hijack)
   7   exploit/windows/local/bypassuac_eventvwr               2016-08-15       excellent  Yes    Windows Escalate UAC Protection Bypass (Via Eventvwr Registry Key)
   8   exploit/windows/local/bypassuac_sdclt                  2017-03-17       excellent  Yes    Windows Escalate UAC Protection Bypass (Via Shell Open Registry Key)
   9   exploit/windows/local/bypassuac_silentcleanup          2019-02-24       excellent  No     Windows Escalate UAC Protection Bypass (Via SilentCleanup)
   10  exploit/windows/local/bypassuac_dotnet_profiler        2017-03-17       excellent  Yes    Windows Escalate UAC Protection Bypass (Via dot net profiler)
   11  exploit/windows/local/bypassuac_fodhelper              2017-05-12       excellent  Yes    Windows UAC Protection Bypass (Via FodHelper Registry Key)
   12  exploit/windows/local/bypassuac_sluihijack             2018-01-15       excellent  Yes    Windows UAC Protection Bypass (Via Slui File Handler Hijack)
```

 - In current case, no. 2 exploit/windows/local/bypassuac worked for windows 7

 - Just type - _use 2_

 - set options as required,, **and most importantly** change the port if it is using the same as session 1

**NEXT MODULE IS PERSISTENCE**

 - persistense is to maintain our access to the target machine

 - That means we will not lose access even if the machine shuts down or reboots.

 - To do that we need to execute our payload on boot time
