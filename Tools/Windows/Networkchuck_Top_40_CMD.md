1. Network information
                    
        ipconfig

2. all network information

        ipconfig /all

3. filter the desired output
- findstr is same as grep in linux

        ipconfig /all | findstr DNS

4. Release the current IP Address

        ipconfig /release

5. Specify Interface

        ipconfig /release "Wifi"

6. Get New IP Address from DHCP

        ipconfig /renew

7. Display DNS records

        ipconfig /displaydns

8. copy to clipboard all stdout

        ipconfig /displaydns | clip

9. Flush the DNS

        ipconfig /flushdns

10. Network Troubleshoot

        nslookup google.com

11. Specify DNS

        nslookup google.com 8.8.8.8

12. Specify Record Type

        nslookup -type=mx google.com

        nslookup -type=txt google.com

        nslookup -type=ptr google.com  

13. Clear the screen 

        cls

14. Get MAC Address

        getmac /v

15. Check energy or powerissue

        powercfg /energy

16. Check Battery Health

        powercfg /batteryreport

17. Default programs for filetypes

        assoc

18. Change the default program

        assoc .mp4=VLC.vlc

19. Check Disk health

        chkdsk /f

20. Check physical sectors

        chkdsk /r

21. System file checker

        sfc /scannow

22. Deployment Image Servicing and Management

        DISM /Online /Cleanup-Image /CheckHealth

23. Go deeper with longer scan

        DISM / Online /Cleanup-Image /ScanHealth

24. Restore Health

        DISM / Online /Cleanup-Image /RestoreHealth

25. List Processes

        tasklist

26. Find Specific task

        tasklist | findstr script

27. Kill task with PID

        taskkill /f /pid <pid>

    - example : 

            taskkill /f /pid 270127

28. Get wireless report

        netsh wlan show wlanreport

29. Show all interfaces

        netsh interface show interface
    
30. Get IP using netsh

        netsh interface ip show address | findstr "IP Address"

31. Get DNS Servers

        netsh interface ip show dnsservers

32. Turn off Windows defender firewall

        netsh firewall set allprofiles state off

32. Turn on Windows defender firewall

        netsh firewall set allprofiles state on

33. ping any host

        ping google.com

    - Add -t option to keep going
    
            ping -t google.com

34. Trace Route

        tracert google.com
    
    - Don't Resolve domain names

            tracert -d google.com

35. Netstat

        netstat

36. See opened Ports

        netstat -af

37. Process ID for all connections

        netstat -o

38. Sent and Received Stats every 5 mins

        netstat -e -t 5

39. route to certain networks or routing table

        route print

40. Add routes in your pc 

        route add <IP> mask <Subnet mask> <Gateway>

    - Example :

          route add 192.168.40.0 mask 255.255.255.0 10.7.1.44

41. Delete a route 

        route delete <IP>

42. Shutdown your pc

        shutdown

43. Restart to BIOS or UEFI

        shutdown /r /fw /f /t 0