# ⚙️  arp-scan

Tags: #⚙️
Related to: [[arp]], [[nmap]]
See also:
Previous:

## Description

arp-scan is **a command-line tool that uses the ARP protocol to discover and fingerprint IP hosts on the local network**.

## Usage

```
┌──(root㉿Trix)-[/home/xron]
└─# arp-scan -I eth0 -g 192.168.0.0/24
```
```text
Interface: eth0, type: EN10MB, MAC: 00:0c:29:84:b2:f5, IPv4: 192.168.11.129
Starting arp-scan 1.10.0 with 256 hosts (https://github.com/royhills/arp-scan)

0 packets received by filter, 0 packets dropped by kernel
Ending arp-scan 1.10.0: 256 hosts scanned in 2.209 seconds (115.89 hosts/sec). 0 responded
```

 - -I for Network Interface
 - -g for IP Subnets