# 🤖 python programs
Tags: #🤖
Related to: 
See also: 
Previous: [[python]]

## Description

A collection of Python programs made using ChatGPT.

## Usage Examples

### Get subdomains from SSL certificates

```python
import requests

# Certificate Search Website
url = "https://crt.sh/?q=hackthebox.eu&output=json"

# Get json data
response = requests.get(url)
data = response.json()

# Avoid duplicate subdomains
subdomains = set()

# Get subdomains
for item in data:
    subdomains.add(item['common_name'])

# Print them
for subdomain in sorted(subdomains):
    print(subdomain)
```

```text
*.enterprise-dev.hackthebox.eu
*.hackthebox.eu
aaamidatlantic-status.polaris.synopsys.com
analytics.hackthebox.eu
api.ctf.hackthebox.eu
api.hackthebox.eu
beta-status.astronomer.io
certificates-dev.hackthebox.eu
<...snip...>
```

#### curl alternative

	curl -s https://crt.sh/\?q\=hackthebox.eu\&output\=json | jq . | grep name | cut -d":" -f2 | grep -v "CN=" | cut -d'"' -f2 | awk '{gsub(/\\n/,"\n");}1;' | sort -u

# References

https://chat.openai.com/chat/