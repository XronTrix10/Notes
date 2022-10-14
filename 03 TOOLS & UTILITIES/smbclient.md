# ⚙️ smbclient

Tags: #⚙️ 
Related to: 
See also: 
Previous: [[SNMP Analysis]]

## Description

FTP-like client to access SMB/CIFS resources on servers

## Usage Examples

### List Samba services

	proxychains smbclient -L \\172.16.1.10	// list services; root:<blankpassword>

```
Enter WORKGROUP\root's password: 

        Sharename       Type      Comment
        ---------       ----      -------
        print$          Disk      Printer Drivers
        SlackMigration  Disk      
        IPC$            IPC       IPC Service (DANTE-NIX02 server (Samba, Ubuntu))
SMB1 disabled -- no workgroup available
```

### Connect to share

	proxychains smbclient \\\\172.16.1.10\\SlackMigration	// root:<blankpassword>

```
smb: \> ls
  .                                   D        0  Mon Apr 12 10:39:41 2021
  ..                                  D        0  Mon Apr 12 10:39:41 2021
  admintasks.txt                      N      279  Mon May 18 11:24:22 2020

smb: \> get admintasks.txt
```

### List Samba services and suppress password prompt

	smbclient -N -L \\\\10.129.42.253

```
Sharename       Type      Comment
---------       ----      -------
print$          Disk      Printer Drivers
users           Disk      
IPC$            IPC       IPC Service (gs-svcscan server (Samba, Ubuntu))
SMB1 disabled -- no workgroup available
```

The login with root username and empty password is successful, which means that SMB NULL
sessions are permitted.

### Attempt to connect as guest user

	smbclient \\\\10.129.42.253\\users

```
Enter WORKGROUP\users's password: 
Try "help" to get a list of possible commands.

smb: \> ls
NT_STATUS_ACCESS_DENIED listing \*

smb: \> exit
```

### Attempt to connect as user

	smbclient -U bob \\\\10.129.42.253\\users

```
Enter WORKGROUP\bob's password: 
Try "help" to get a list of possible commands.

smb: \> ls
  .                                   D        0  Thu Feb 25 16:42:23 2021
  ..                                  D        0  Thu Feb 25 15:05:31 2021
  bob                                 D        0  Thu Feb 25 16:42:23 2021

		4062912 blocks of size 1024. 1332480 blocks available
		
smb: \> cd bob

smb: \bob\> ls
  .                                   D        0  Thu Feb 25 16:42:23 2021
  ..                                  D        0  Thu Feb 25 16:42:23 2021
  passwords.txt                       N      156  Thu Feb 25 16:42:23 2021

		4062912 blocks of size 1024. 1332480 blocks available
		
smb: \bob\> get passwords.txt 
getting file \bob\passwords.txt of size 156 as passwords.txt (0.3 KiloBytes/sec) (average 0.3 KiloBytes/sec)
```

# References