---
layout: post
title:  "HTTP Caches - I read RFC 7234 so you won’t have to. Part 1: The Basics"
date:   2020-02-16 15:20:00 +0100
tags: webdev caching
xpost_devto: https://dev.to/ericathedev/http-caches-i-read-rfc-7234-so-you-won-t-have-to-part-1-the-basics-kl6
excerpt: RFC 7234 is an Internet Standards document for Hypertext Transfer Protocol (HTTP) defined by the Internet Engineering Task Force (IETF). RFC 7234 defines how a cache should be implemented internally. 
---
## What is an HTTP cache?
An HTTP cache stores the responses of HTTP requests made over a network in a local store. The next time the cache receives a request matching the local copy of the response, the cache can return that instead of making the network call again. This reduces the response time and network bandwidth consumption on future HTTP requests.

## What is RFC 7234 and why should I care?

[RFC 7234](https://tools.ietf.org/html/rfc7234) is an Internet Standards document for Hypertext Transfer Protocol (HTTP) defined by the Internet Engineering Task Force (IETF). RFC 7234 defines how a cache should be implemented internally. 

Although most developers won’t have to implement an HTTP cache, it’s useful to know what’s happening under the hood, because as a Web Developer there will come a time when you’ll find yourself asking, “Is this being cached, and how do I make it stop?” 🤔. 

If you’re implementing client side code then you can send cache control headers in a request to influence whether you’re going to get information from the cache or not, depending on various criteria.

If you’re implementing server side code then cache control headers sent in the HTTP response inform the cache on how long it is safe to store the request in the cache. If as a server you don’t provide any cache control headers, the cache uses heuristics to estimate what can be cached, and for how long. 

## Where are these caches?
Caches fall into two types, private caches, dedicated to a single user, like the one in your browser, and shared caches, which are used by more than one user, like caches at your [ISP](https://en.wikipedia.org/wiki/Internet_service_provider), [CDN](https://en.wikipedia.org/wiki/Content_delivery_network) or server side caching. In the latter case, there are certain extra restrictions on what is cached, because you don’t want to be serving user specific data to other people by mistake 😬.

## What are the disadvantages of caching?
The most obvious disadvantage of caching is that you want to retrieve the latest information from a server, but somewhere along the way your request keeps getting cached.

The second less obvious disadvantage has to do with security. Bugs 🐛 or vulnerabilities in caches can result in a whole host of problems. These include:
- Since a large number of requests and responses are saved in caches, if the cache becomes compromised, there’s a lot of a user’s history available. 
- A compromised cache can be injected with malicious payloads. 
- Sensitive/private data can end up being cached due both due to bugs in the cache or misuse of caching headers.
- Or simply someone being able to tell that a website has been visited previously because a page takes less time to load, because it has been cached.

The potential gains for attackers are multiplied when they manage to target shared caches, as this allows them to reach multiple users.

## Want to learn more? Some great resources on caching from my research
- The original RFC 7234 itself - [https://tools.ietf.org/html/rfc7234](https://tools.ietf.org/html/rfc7234)
- An updated version of RFC 7234 with inline errata - [https://www.rfc-editor.org/rfc/inline-errata/rfc7234.html](https://www.rfc-editor.org/rfc/inline-errata/rfc7234.html)
- Mozilla's documentation explaining Cache Control [https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Cache-Control](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Cache-Control)
and [https://developer.mozilla.org/en-US/docs/Web/HTTP/Caching](https://developer.mozilla.org/en-US/docs/Web/HTTP/Caching)
- Mark Nottingham's super comprehensive Caching Tutorial - [https://www.mnot.net/cache_docs/](https://www.mnot.net/cache_docs/)
