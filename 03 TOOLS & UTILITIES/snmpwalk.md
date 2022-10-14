# 💢 snmpwalk

Tags: 
Related to: 
See also: 
Previous: [[SNMP Analysis]]

## Description

snmpwalk is an SNMP application that uses SNMP GETNEXT requests to query a network entity for a tree of information.

## Usage Examples

```shell-session
snmpwalk -v 2c -c public 10.129.42.253 1.3.6.1.2.1.1.5.0

iso.3.6.1.2.1.1.5.0 = STRING: "gs-svcscan"
```

```shell-session
snmpwalk -v 2c -c private  10.129.42.253 

Timeout: No Response from 10.129.42.253
```

# References