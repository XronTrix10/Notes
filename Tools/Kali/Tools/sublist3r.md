# ⚙️ sublist3r

Tags: #⚙️
Related to: 
See also: [[dnsrecon]]
Previous:

## Description

Sublist3r is **a python tool designed to enumerate subdomains of websites using OSINT**. It helps penetration testers and bug hunters collect and gather subdomains for the domain they are targeting.

## Installation

	sudo apt install sublist3r -y

## Usage

1. sublist3r -d {domain name} -e google,yahoo

2. sublist3r -d {domain name} // omit -e option to search from all search engine

 - set -t or --thread option for bruteforcing and see documentation page for more details
```
┌──(xron㉿Trix)-[~]
└─$ sublist3r -d hackersploit.org

                 ____        _     _ _     _   _____
                / ___| _   _| |__ | (_)___| |_|___ / _ __
                \___ \| | | | '_ \| | / __| __| |_ \| '__|
                 ___) | |_| | |_) | | \__ \ |_ ___) | |
                |____/ \__,_|_.__/|_|_|___/\__|____/|_|

                # Coded By Ahmed Aboul-Ela - @aboul3la
    
[-] Enumerating subdomains now for hackersploit.org
[-] Searching now in Baidu..
[-] Searching now in Yahoo..
[-] Searching now in Google..
[-] Searching now in Bing..
[-] Searching now in Ask..
[-] Searching now in Netcraft..
[-] Searching now in DNSdumpster..
[-] Searching now in Virustotal..
[-] Searching now in ThreatCrowd..
[-] Searching now in SSL Certificates..
[-] Searching now in PassiveDNS..
[!] Error: Virustotal probably now is blocking our requests

```