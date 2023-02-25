# 💢 dnsrecon
Tags: #💢
Related to: 
See also: 
Previous: [[DNS Analysis]]

---
## Description


## Usage Examples

```
┌──(xron㉿Trix)-[~]
└─$ dnsrecon -d hackersploit.org     
[*] std: Performing General Enumeration against: hackersploit.org...
[*] DNSSEC is configured for hackersploit.org
[*] DNSKEYs:
[*] 	NSEC KSk ECDSAP256SHA256 99db2cc14cabdc33d6d77da63a2f15f7 1112584f234e8d1dc428e39e8a4a97e1 aa271a555dc90701e17e2a4c4b6f120b 7c32d44f4ac02bd894cf2d4be7778a19
[*] 	NSEC ZSK ECDSAP256SHA256 a09311112cf9138818cd2feae970ebbd 4d6a30f6088c25b325a39abbc5cd1197 aa098283e5aaf421177c2aa5d714992a 9957d1bcc18f98cd71f1f1806b65e148
[*] 	 SOA dee.ns.cloudflare.com 172.64.32.93
[*] 	 SOA dee.ns.cloudflare.com 173.245.58.93
[*] 	 SOA dee.ns.cloudflare.com 108.162.192.93
[*] 	 SOA dee.ns.cloudflare.com 2a06:98c1:50::ac40:205d
[*] 	 SOA dee.ns.cloudflare.com 2803:f800:50::6ca2:c05d
[*] 	 SOA dee.ns.cloudflare.com 2606:4700:50::adf5:3a5d
[*] 	 NS dee.ns.cloudflare.com 108.162.192.93
[*] 	 Bind Version for 108.162.192.93 "2023.2.8"
[*] 	 NS dee.ns.cloudflare.com 173.245.58.93
[*] 	 Bind Version for 173.245.58.93 "2023.2.8"
[*] 	 NS dee.ns.cloudflare.com 172.64.32.93
[*] 	 Bind Version for 172.64.32.93 "2023.2.8"
[*] 	 NS dee.ns.cloudflare.com 2a06:98c1:50::ac40:205d
[*] 	 NS dee.ns.cloudflare.com 2803:f800:50::6ca2:c05d
[*] 	 NS dee.ns.cloudflare.com 2606:4700:50::adf5:3a5d
[*] 	 NS jim.ns.cloudflare.com 172.64.33.125
[*] 	 Bind Version for 172.64.33.125 "2023.2.8"
[*] 	 NS jim.ns.cloudflare.com 173.245.59.125
[*] 	 Bind Version for 173.245.59.125 "2023.2.8"
[*] 	 NS jim.ns.cloudflare.com 108.162.193.125
[*] 	 Bind Version for 108.162.193.125 "2023.2.8"
[*] 	 NS jim.ns.cloudflare.com 2a06:98c1:50::ac40:217d
[*] 	 NS jim.ns.cloudflare.com 2803:f800:50::6ca2:c17d
[*] 	 NS jim.ns.cloudflare.com 2606:4700:58::adf5:3b7d
[*] 	 MX _dc-mx.2c2a3526b376.hackersploit.org 198.54.120.212
[*] 	 A hackersploit.org 104.21.44.180
[*] 	 A hackersploit.org 172.67.202.99
[*] 	 AAAA hackersploit.org 2606:4700:3031::6815:2cb4
[*] 	 AAAA hackersploit.org 2606:4700:3036::ac43:ca63
[*] 	 TXT hackersploit.org google-site-verification=TW0pQsFZ0xx3w4b7kysBV0UrcMq7fJFB-5Rz9h6GwkU
[*] 	 TXT hackersploit.org v=spf1 a:my.hackersploit.org ~all
[*] Enumerating SRV Records
[+] 0 Records Found

```
---
## References
- [[]]