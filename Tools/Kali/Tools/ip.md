# ⚙️ ip

Tags: #⚙️
Related to:
See also: [[ifconfig]]
Previous:

## Description

Show / manipulate routing, network devices, interfaces and tunnels.

## Usage Examples

### Show addresses assigned to all network interfaces

	ip a
	ip addr

### Check that you're connected to VPN

	ip -4 a show tun0

```text
6: tun0: <POINTOPOINT,MULTICAST,NOARP,UP,LOWER_UP> mtu 1500 qdisc pfifo_fast state UNKNOWN group default qlen 500
    inet 10.10.10.1/23 scope global tun0
       valid_lft forever preferred_lft forever
```

As long we get our IP back, then we should be connected to the VPN network.

### Get IP informetion in different interface

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

# References
