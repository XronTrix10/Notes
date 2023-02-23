## Scanning with nmap

```
┌──(xron㉿Trix)-[~]
└─$ nmap -A -T4 -p- -v 192.168.11.131
Starting Nmap 7.93 ( https://nmap.org ) at 2023-02-23 19:56 IST
NSE: Loaded 155 scripts for scanning.
NSE: Script Pre-scanning.
Initiating NSE at 19:57
Completed NSE at 19:57, 0.00s elapsed
Initiating NSE at 19:57
Completed NSE at 19:57, 0.00s elapsed
Initiating NSE at 19:57
Completed NSE at 19:57, 0.00s elapsed
Initiating Ping Scan at 19:57
Scanning 192.168.11.131 [2 ports]
Completed Ping Scan at 19:57, 0.00s elapsed (1 total hosts)
Initiating Parallel DNS resolution of 1 host. at 19:57
Completed Parallel DNS resolution of 1 host. at 19:57, 6.00s elapsed
Initiating Connect Scan at 19:57
Scanning 192.168.11.131 [65535 ports]
Discovered open port 22/tcp on 192.168.11.131
Discovered open port 8080/tcp on 192.168.11.131
Discovered open port 111/tcp on 192.168.11.131
Discovered open port 80/tcp on 192.168.11.131
Discovered open port 49727/tcp on 192.168.11.131
Discovered open port 40859/tcp on 192.168.11.131
Discovered open port 55147/tcp on 192.168.11.131
Discovered open port 43829/tcp on 192.168.11.131
Discovered open port 2049/tcp on 192.168.11.131
Completed Connect Scan at 19:57, 2.40s elapsed (65535 total ports)
Initiating Service scan at 19:57
Scanning 9 services on 192.168.11.131
Completed Service scan at 19:57, 6.21s elapsed (9 services on 1 host)
NSE: Script scanning 192.168.11.131.
Initiating NSE at 19:57
Completed NSE at 19:57, 1.01s elapsed
Initiating NSE at 19:57
Completed NSE at 19:57, 0.03s elapsed
Initiating NSE at 19:57
Completed NSE at 19:57, 0.00s elapsed
Nmap scan report for 192.168.11.131
Host is up (0.0015s latency).
Not shown: 65526 closed tcp ports (conn-refused)
PORT      STATE SERVICE  VERSION
22/tcp    open  ssh      OpenSSH 7.9p1 Debian 10+deb10u2 (protocol 2.0)
| ssh-hostkey: 
|   2048 bd96ec082fb1ea06cafc468a7e8ae355 (RSA)
|   256 56323b9f482de07e1bdf20f80360565e (ECDSA)
|_  256 95dd20ee6f01b6e1432e3cf438035b36 (ED25519)
80/tcp    open  http     Apache httpd 2.4.38 ((Debian))
|_http-server-header: Apache/2.4.38 (Debian)
| http-methods: 
|_  Supported Methods: GET HEAD POST OPTIONS
|_http-title: Bolt - Installation error
111/tcp   open  rpcbind  2-4 (RPC #100000)
| rpcinfo: 
|   program version    port/proto  service
|   100000  2,3,4        111/tcp   rpcbind
|   100000  2,3,4        111/udp   rpcbind
|   100000  3,4          111/tcp6  rpcbind
|   100000  3,4          111/udp6  rpcbind
|   100003  3           2049/udp   nfs
|   100003  3           2049/udp6  nfs
|   100003  3,4         2049/tcp   nfs
|   100003  3,4         2049/tcp6  nfs
|   100005  1,2,3      45181/udp   mountd
|   100005  1,2,3      49389/udp6  mountd
|   100005  1,2,3      54139/tcp6  mountd
|   100005  1,2,3      55147/tcp   mountd
|   100021  1,3,4      32889/tcp6  nlockmgr
|   100021  1,3,4      43829/tcp   nlockmgr
|   100021  1,3,4      51018/udp   nlockmgr
|   100021  1,3,4      59184/udp6  nlockmgr
|   100227  3           2049/tcp   nfs_acl
|   100227  3           2049/tcp6  nfs_acl
|   100227  3           2049/udp   nfs_acl
|_  100227  3           2049/udp6  nfs_acl
2049/tcp  open  nfs_acl  3 (RPC #100227)
8080/tcp  open  http     Apache httpd 2.4.38 ((Debian))
| http-methods: 
|_  Supported Methods: GET HEAD POST OPTIONS
|_http-server-header: Apache/2.4.38 (Debian)
| http-open-proxy: Potentially OPEN proxy.
|_Methods supported:CONNECTION
|_http-title: PHP 7.3.27-1~deb10u1 - phpinfo()
40859/tcp open  mountd   1-3 (RPC #100005)
43829/tcp open  nlockmgr 1-4 (RPC #100021)
49727/tcp open  mountd   1-3 (RPC #100005)
55147/tcp open  mountd   1-3 (RPC #100005)
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel

NSE: Script Post-scanning.
Initiating NSE at 19:57
Completed NSE at 19:57, 0.00s elapsed
Initiating NSE at 19:57
Completed NSE at 19:57, 0.00s elapsed
Initiating NSE at 19:57
Completed NSE at 19:57, 0.00s elapsed
Read data files from: /usr/bin/../share/nmap
Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 16.28 seconds

```

