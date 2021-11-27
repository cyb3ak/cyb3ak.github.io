---
title: ffuf - Fuzz Faster U Fool
author: cyb3ak
date: 2021-11-22 14:10:00 +0800
categories: [Commands, Linux Commands, ffuf]
tags: [ffuf]
image: "/assets/img/posts/Commands/ffuf_thumb.png" 
---

for scanning web directories.
___

## Directory Enumeration
`ffuf -u <url>/FUZZ -w <wordlist>`
- Wordlist1 = `/usr/share/dirb/wordlists/common.txt`
- Wordlist2 = 

## Directory Enumeration using recursion
`ffuf -u <url>/FUZZ -w <wordlist> -recursion`
- Wordlist1 = `/usr/share/dirb/wordlists/common.txt`
___

## Sub-domain Enumeration
___

## file discovery
`ffuf -u <url>/FUZZ -w <wordlist> -e .php,.html,.txt`
- Extensions = `.php,.html,.txt,.sql,.bak,.tar,.tar.gz,.db,.zip,.sqlite`
- Wordlist1 = `/usr/share/wordlists/SecLists/Discovery/Web-Content/directory-list-2.3-medium.txt`

## file extension fuzzing
`ffuf -u <url_path>/file.FUZZ -w <wordlist>`
- Wordlist1 = `/usr/share/wordlists/SecLists/Fuzzing/extensions-skipfish.fuzz.txt`
___

## Virtual Host Enumeration
`ffuf -u <url> -w <wordlist> -H “Host: FUZZ.<domain.com>`

## Username enumeration
```
ffuf -w /usr/share/wordlists/SecLists/Usernames/Names/names.txt -X POST -d "username=FUZZ&email=x&password=x&cpassword=x" -H "Content-Type: application/x-www-form-urlencoded" -u http://MACHINE_IP/customers/signup -mr "username already exists"
```

# Learn more
- [Article by Coding.io](https://codingo.io/tools/ffuf/bounty/2020/09/17/everything-you-need-to-know-about-ffuf.html)
- https://www.geeksforgeeks.org/ffuf-fast-web-fuzzer-linux-tool-written-in-go/
- https://cybersecnerds.com/ffuf-everything-you-need-to-know/