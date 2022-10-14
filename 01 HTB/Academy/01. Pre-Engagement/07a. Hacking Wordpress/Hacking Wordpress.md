# Hacking Wordpress

Tags: #🧑‍🎓 
Related to: 
See also: 
Previous: [[ ]]

![[logo_hacking_wordpress.png]]

WordPress is an open-source Content Management System (CMS) that can be used for multiple purposes.

### Cheatsheets

| **Command** | **Description** |
| --------------|-------------------|
|`tree -L 1`|  Lists contents of current directory |
|`curl -s -X GET <url>`| Makes a GET request to a webserver and receives HTML source code of requested web page |
|`curl -I -X GET <url>`| Prints the response header of the GET request from the requested web page |
|`curl -X POST -d <data> <url>`| Sends a POST request with data to specific webserver |
|`wpscan --url <url> -e ap`| Scans specific WordPress application to enumerate plugins |
|`wpscan --url <url> -e u`| Scans specific WordPress application to enumerate users |
|`msfconsole`| Starts Metasploit Framework |
|`html2text`|  Converts redirected HTML output or files to easily readable output |
|`grep <pattern>`| Filters specific pattern in files or redirected output |
|`jq`| Transforms JSON input and streams of JSON entities |
|`man <tool>`| Man provides you with the manpage of the specific tool |

### Module Summary

As an information security professional, it is important to understand networking, operating systems, databases, web applications, scripting and programming languages, and more. During the course of your career, you will most likely come in contact with a variety of different types of web applications. As you become more experienced, you will start to see some of the web applications repeatedly, whether from the standpoint of an attacker or a defender. One of the most common web applications used by all sizes and types of organizations is WordPress. This module's goal is to impart a deep understanding of how WordPress websites function to better position them to attack and defend them. In this module, we will cover:

-   An overview of WordPress and the structure of a WordPress website
-   Manual and automated enumeration techniques
-   Attacks against WordPress users
-   Manual and automated attacks against a WordPress installation and the underlying webserver
-   Security hardening best practices to defend against the techniques covered in this module

This module is broken down into sections with accompanying hands-on exercises to practice each of the tactics and techniques we cover. The module ends with a practical hands-on skills assessment to gauge your understanding of the various topic areas.

You can start and stop the module at any time and pick up where you left off. There is no time limit or "grading," but you must complete all of the exercises and the skills assessment to receive the maximum number of cubes and have this module marked as complete in any paths you have chosen.

The module is classified as "Easy." However, it assumes a working knowledge of the Linux command line, an understanding of web applications and web requests, and a basic understanding of core networking concepts.

A firm grasp of the following modules can be considered prerequisites for successful completion of this module:

-   Introduction to Networking
-   Linux Fundamentals
-   Web Requests