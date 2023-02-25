# 💢 nikto
Tags: #💢
Related to: 
See also: 
Previous: [[Vulnerability Analysis]], [[Web Vulnerability Scanners]]

---
## Description


## Usage Examples

```
┌──(xron㉿Trix)-[~]
└─$ nikto -h google.com 
```

```text
- Nikto v2.1.6
---------------------------------------------------------------------------
+ Target IP:          142.250.192.78
+ Target Hostname:    google.com
+ Target Port:        80
+ Start Time:         2023-02-26 01:35:28 (GMT5.5)
---------------------------------------------------------------------------
+ Server: gws
+ X-XSS-Protection header has been set to disable XSS Protection. There is unlikely to be a good reason for this.
+ The X-Content-Type-Options header is not set. This could allow the user agent to render the content of the site in a different fashion to the MIME type
+ Root page / redirects to: http://www.google.com/
+ No CGI Directories found (use '-C all' to force check all possible dirs)
+ Server banner has changed from 'gws' to 'sffe' which may suggest a WAF, load balancer or proxy is in place
+ Uncommon header 'cross-origin-resource-policy' found, with contents: cross-origin
+ Cookie 1P_JAR created without the httponly flag
+ Allowed HTTP Methods: GET, HEAD
```
 - -h option to specify host or domain
---
## References
- [[]]