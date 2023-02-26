# 🔥 Windows Meterpreter

Tags: #🔥 
Related to: [[_shells]], [[Windows Fundamentals]]
See Also:

---
## Core Commands

| **Commands** | **Description** |
| ------ | ------------- |
|`?`  | Help Menu |
|	`background` | Backgrounds the current session |
|	`bg` | Alias for `background` |
|	`bgkill` | kills a background meterpreter script |
|	`bglist` | Lists running background scripts |
|	`bgrun` | Executes a meterpreter script as a background thread |
|	`channel` | Displays information or control active channels |
|	`close` | Closes a channel |
|	`detach` | Detach the meterpreter session (for http/https) |
|	`disable_unicode_encoding` | Disables encoding of unicode strings |
|	`enable_unicode_encoding` | Enables encoding of unicode strings |
|	`exit` | Terminate the meterpreter sessions |
|	`get_timeouts` | Get the current session timeout values |
|	`guid` | Get the session guid |
|	`help` | Help menu |
|	`info` | Displays information about a post module |
|	`irb` | Open an interactive ruby shell on the current shell |
|	`load` | Load one or more meterpreter extensions |
|	`machine_id` | Get the MSF ID machine attached to the session |
|	`migrate` | Migrate the server to another process |
|	`pivot` | Manage pivot listeners |
|	`pry` | Open the pry debugger on the current session |
|	`quit` | Terminate the meterpreter session |
|	`read` | Reads data from the channel |
|	`resource` | Run the commands stored in a file |
|	`run` | Executes a meterpreter script or post module |
|	`secure` | (Re)Negotiate TLV packet encryption on the session |
|	`sessions` | Quickly switch to another session |
|	`set_timeouts` | Set the current session timeout values |
|	`sleep` | Force meterpreter to go quiet, then re|establish connection |
|	`ssl_verify` | Modify the SSL certificate verification settings |
|	`transport` | Manage the transport mechanisms |
|	`use` | Depricated alias for `load` |
|	`uuid` | Get the UUID for the current session |
|	`write` | Write data to a channel |

---
## File System Commands

| **Commands** | **Description** |
| ------ | ------------- |
| `cat` | Read the contents of a file to screen |
| `cd` | Change directory |
| `checksum` | Retrieve the checksum of a file |
| `cp` | Copy source to Destination |
| `del` | Delete specified file |
| `dir` | List files ( alias for `ls` ) |
| `download` | Download a file or directory |
| `edit` | Edit a file |
| `getlwd` | Print local working directory |
| `getpwd` | Print working directory |
| `lcat` | Read the contents of a local file to screen |
| `lcd` | Change local working directory |
| `lls` | local list files |
| `lpwd` | Print local working directory |
| `ls` | List files |
| `mkdir` | Make Directory |
| `mv` |  Move Source to Destination |
| `pwd` | Print working directory |
| `rm` |  Delete specified file |
| `rmdir` | Delete directory |
| `search` | Search for files |
| `show_mount` |  List all mount points/logical drives |
| `upload` |  Upload a file or directory |

---

## System Commands


| **Commands** | **Description** |
| ------ | ------------- |
| `clearev` | Clear the event log  |
| `drop_tokenn` |  Relinquishes any active impersonation token |
| `execute` |  Execute a command |
| `getenv` |  Get one or more environment variable values |
| `getpid` | Get the current process identifier |
| `getprivs` | Attempt to enable sll privileges availableto the current process |
| `getsid` | Get the SID of the user that the server is running as |
| `getuid` | Get the user that the server is running as |
| `kill` | Terminate a process |
| `localtime` | Displays the target system local date and time |
| `pgrep` | Filter process by name |
| `pkill` | Terminate a process by name |
| `ps` |  List running processes |
| `reboot` | Reboots the remote computer |
| `reg` | Modify and interact with the remote registry |
| `rev2self` | Calls Revert2Self() on the remote machine |
| `shell` | Drop into a system command shell |
| `shutdown` | Shuts down the remote computer |
| `steal_token` | Attempts to steal an impersonation token from the target process  |
| `suspend` | Suspends or resumes a list of processes |
| `sysinfo` | Gets information about the remote system such as OS |

---

## Audio Output Command

`play` - play a waveform audiofile ( .wav ) on the target system

## Priviledge: Elevate Command

`getsystem` - Attempts to elevate your priviledge to that local system

## Priviledge: Password Database Command 

`hashdump` - Dumps the contents of the SAM database

## Priviledge: Timestomp Command

`timestomp` - Manipulate file MACE attributes

---

## Networking Commands

| **Commands** | **Description** |
| ------ | ------------- |
| `arp` | Display the host ARP cache |
| `getproxy` |  Display the current proxy configuration |
| `ifconfig` | Display interfaces |
| `ipconfig` | Display interfaces |
| `netstat` |  Displays the network connections |
| `portfwd` |  Forward a local port to a remote service |
| `resolve` |  Resolve a set of hostnames on the target |
| `route` | View and modify the route table |

---

## User Interface Commands

| **Commands** | **Description** |
| ------ | ------------- |
| `enumdesktops` | List all accessible desktops and window stations |
| `getdesktop` |  Get the current meterpreter desktop |
| `idletime` |  Returns the number of seconds the remote user has been idle |
| `keyboard_send` |  Send keystroke |
| `keyevent` | Send key events |
| `keyscan_dump` | Dump the keystroke buffer |
| `keyscan_start` | Start capturing keystroke |
| `keyscan_stop` |  Stop capturing keystroke |
| `mouse` | Send mouse events |
| `screenshare` | Watch the remote user desktop in real time |
| `screenshot` | Grab a screenshot of the interactive desktop |
| `setdesktop` | Change the meterpreters current desktop |
| `uictl` | Control some of the user interface components |

---

## Webcam Commands

| **Commands** | **Description** |
| ------ | ------------- |
| `record_mic` | Record audio from the default microphone for X seconds |
| `webcam_chat` | Start a video chat |
| `webcam_list` | List webcams |
| `webcam_snap` | Take a snapshot from the specified webcam |
| `webcam_stream` | Play a video stream from the specified webcam |