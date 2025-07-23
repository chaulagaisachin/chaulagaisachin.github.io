---
title: "How DNS works? Where do we see it, or we don’t!"
date: 2023-11-11
description: "A simple explanation of how DNS works, from browser to root servers, and why it matters for everyday internet users."
image: ""
author: "Sachin Chaulagai"
tags: [DNS, Browsers, System Design Interview, Interview, System]
---

## How DNS works? Where do we see it, or we don’t!

DNS or we say Domain Name System, has quietly weaves its magic in our daily online lives, like backstage crew making theatrical performance seamless. DNS is the reason you can effortlessly type “google.com” into your browser, instead of memorizing cryptic numbers. It’s like dialing your friend with a saved contact in your phone; you don’t have to remember their number. Yet, here’s the mesmerizing part — how does this digital wizardry unfold across the vast expanse of the internet, this colossal web of connections?

Imagine a world without street names, where you have to memorize a bunch of latitudes and longitudes to find your way around. Not particularly captivating, is it? Let’s delve into how DNS has transformed our world into something much simpler than it might appear.

**PRE-REQ:** IP Address, ISP, Operating System, Cache

### The Local Phase:

When you type a URL into your browser, it begins by checking its cache for the corresponding IP address. If found, it connects to the server. However, if the IP is not in the browser’s cache, it consults the operating system’s DNS client. The operating system, like the browser, maintains a cache of recently resolved DNS addresses. If the IP is present in the OS cache, the connection is established; otherwise, a DNS query is sent through your local network to the Internet Service Provider (ISP). This collaborative effort ensures that your browser and operating system work together to find the necessary IP address.

Consider the example of ‘www.google.com': If Google’s IP isn’t in your browser or OS cache, a DNS query is sent to the ISP, which provides the IP. This seamless process happens in the background, allowing you to access the website with a simple URL entry.

### ISP to ROOT DNS:

Now, the query is sent to the DNS resolver of the ISP. In a manner similar to the process described earlier, if the ISP’s DNS server already possesses the corresponding IP address for the queried domain (e.g., ‘www.google.com'), it promptly responds to the user’s network (LAN) with the IP address. However, if the DNS resolver does not have the required information cached, it initiates a DNS query by reaching out to one of the 13 root DNS servers using anycast.

Upon receiving the query, the root DNS server doesn’t directly provide the IP address for ‘www.google.com.' Instead, it responds with a referral, indicating the IP addresses of the Top-Level Domain (TLD) servers responsible for the ‘.com’ TLD. This redirection is a crucial step in the DNS hierarchy. The ISP’s DNS resolver then proceeds to send a new query specifically to the TLD DNS server for ‘.com,’ as the initial request was for ‘www.google.com.'

### ISP to Top Level Domain:

The TLD DNS server, in turn, responds to the ISP’s DNS resolver with another referral, this time directing it to the authoritative DNS server responsible for the ‘google.com’ domain. The DNS resolver finally sends a query to the authoritative DNS server for ‘google.com,’ and upon receiving the response, caches the IP address. Subsequently, the ISP’s DNS server provides the IP address to the user’s network, allowing the user’s browser to establish a connection with the web server hosting ‘www.google.com.'

### In Short:

In conclusion, DNS, our digital navigator, quietly shapes our online experience by translating user-friendly URLs into the intricate language of IP addresses. It seamlessly operates in the background, ensuring you effortlessly reach your desired websites with just a simple URL entry. From the local cache to the vast DNS hierarchy, this essential system transforms the complexity of the internet into a user-friendly journey.
