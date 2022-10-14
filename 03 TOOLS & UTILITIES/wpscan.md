# 💢 wpscan
Tags: #💢
Related to: 
See also: 
Previous: [[Web Application Analysis]], [[Web Vulnerability Scanners]]

---
## Description

WordPress Security Scanner.

## Usage Examples

### Enumerate vulnerable plugins

	wpscan --url http://10.10.110.100:65000/wordpress --enumerate vp -o wpscan.txt

### Check WordPress Vulnerability Database [^1]

### Enumerate users

	wpscan --url http://10.10.110.100:65000/wordpress --enumerate u

### Bruteforce WordPress login

	wpscan --url http://10.10.110.100:65000/wordpress --usernames names.txt --passwords cewl.out
 
---
## References

[^1]: https://wpvulndb.com/wordpresses/541