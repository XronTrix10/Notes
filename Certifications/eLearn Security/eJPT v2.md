# This is the Cheatsheet of eJPT v2 Course material by INE

## <u>Section: Information Gathering</u>

### Passive information Gathering:

- **Website Recon and footprinting**

1. host command - a DNS Lookup utility. Example usage: 
```
$ host google.com
```


2. crawl the website

    i.  Check for robots.txt
`https://google.com/robots.txt`
    
    ii. Check for sitemap.xml/sitemaps.xml 
`https://google.com/sitemap.xml`

    
3. Get some browser extensions

    i.  BuiltWith

    ii. Wappalyzer

    
4. Whatweb Command

        $ whatweb google.com         
        $ whatweb <IP Address> 
        
    
5. Download the entire website to analyze structure and source code

    - Visit [HTTRack](https://www.httrack.com/)

    or
    ```
    $ sudo apt install webhttrack 
    $ httrack
    ```