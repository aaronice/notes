---
layout:     post
title:      "Anti Anti-spider Strategy"
subtitle:   "Common strategies for coping with anti-spider"
date:       2016-02-15 12:00:00
author:     "aaronice"
keyword:    ["web", "crawler", "scrape", "spider", "data"]
header-img: ""
---

# The Anti Anti-scraping Strategy

Before knowing how to prevent being blacklisted while scraping, we need to understand how a website detect web crawlers.

There're multiple anti-scraping mechanisms to distinguish a spider from a normal user. Some of the methods are[<sup>[1]</sup>](https://learn.scrapehero.com/how-to-prevent-getting-blacklisted-while-scraping/):


>1. Unusual traffic/high download **rate** especially from a **single** client/or IP address within a short **time** span.
>
>2. **Repetitive** tasks performed on the website – based on an assumption that a human user won’t perform the same repetitive tasks all the time.
>
>3. Detection through **honeypots** – these honeypots are usually links which **aren’t visible** to a normal user but only to a spider. When a scraper/spider tries to access the link, the alarms are tripped.


Corresponding to the anti-scraping mechanisms are the following strategies:

## IP Addresses Rotation

IP blacklisting is the perhaps the easiest way of anti-scraping. By creating a pool of IP addresses, and making requests using different IP, will make it harder for server to detect crawlers.

- Use a list of IP from proxy services
  - Randomly pick an IP for certain time interval

## Cookie Rotation
Cookies are encrypted data stored in client side, some website use cookie to identify user. If a user client sends requests in high frequency, it's possible to be identified as suspicious crawler, thus denied access.

- Customize and manage a pool of cookies
  - Sending request to server without cookie headers, parse the package for set-cookie value; store it in cookie collector;
  - Get cookie from cookie collect and if the cookie is not usable, then delete it from cookie collector;
  - Manage the cookie collector with timestamp, in order for the spider to get the oldest cookie first each time.


- Disable cookie
  - By disabling cookie, it may help prevent being banned by some websites which use cookie to identify crawlers.


## User-Agent Imitation

To disguise as browser, one of the approaches is to modify the User-Agent. User-Agent is a string in request header that contains user-agent information, such as the version of web browser, client, operating system etc.

- Spoof the User-Agent by making a list of user agents and randomly pick one for each request. Setting the User-Agent to a common web
browser instead of using the default ones.

## Rate Limit

Slow down the crawling, treat the websites nicely, don't overwhelm it, or DDoS the server.

- Put some random sleeps between requests
- Add some delays after crawling a number of pages
- Use the lowest number of concurrent requests possible

## Be Careful About Honeypots

These honeypots usually are links that normal user can’t see but a spider can[<sup>[1]</sup>](https://learn.scrapehero.com/how-to-prevent-getting-blacklisted-while-scraping/). They might be having the CSS style "display:none". Thus the detection of honeypots can be tricky.

## Avoid Repetitive Crawling Pattern

Some websites implemented intelligent anti-crawling mechanisms, thus a repetitive action will be likely detected as spider. To make a spider looks like a human, add random clicks, mouse movement, random actions etc. Using automated testing tool like Selenium may simulator normal "human actions". 


## Reference

1. [HOW TO PREVENT GETTING BLACKLISTED WHILE SCRAPING](https://learn.scrapehero.com/how-to-prevent-getting-blacklisted-while-scraping/)

2. [防止爬虫被墙的方法总结](http://www.dianacody.com/2014/10/01/spider_5.html)

3. [应对反爬虫之换Cookie](https://medium.com/@Masutangu/%E5%BA%94%E5%AF%B9%E5%8F%8D%E7%88%AC%E8%99%AB%E4%B9%8B%E6%8D%A2cookie-d3b48b02d0e6)
