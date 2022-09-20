# CS Compendium
A centralized personal compendium of computer science resources.

# Table of contents
<!-- vim-markdown-toc GFM -->

* [Software engineering](#software-engineering)
	- [Design patterns](#design-patterns)
	- [Developer productivity](#developer-productivity)
	- [Git](#git)
	- [Regex](#regex)
* [Web development](#web-development)
	- [REST APIs](#rest-apis)
	- [HTML](#html)
	- [CSS](#css)
	- [HTTP(S)](#https)
	- [Security](#security)
* [Design](#design)
	- [Web design](#web-design)
* [FreeBSD sysadmin](#freebsd-sysadmin)
* [General sysadmin](#general-sysadmin)
	- [Networking](#networking)
	- [Docker](#docker)
	- [OS](#os)
* [Site reliability](#site-reliability)
* [Unix](#unix)
* [systemd](#systemd)
* [Observability](#observability)
* [Concurrency](#concurrency)
* [Databases](#databases)
	- [SQL](#sql)
	- [MongoDB](#mongodb)
* [SaaS/Business](#saasbusiness)
* [Security](#security-1)
	- [Random Number Generators](#random-number-generators)
	- [Malware](#malware)
* [Academia](#academia)
* [Misc](#misc)

<!-- vim-markdown-toc -->
## Software engineering
### Design patterns
* [Why is Global State so Evil?](https://softwareengineering.stackexchange.com/questions/148108/why-is-global-state-so-evil): A discussion with in-depth argumentation against writing code/functions that depend on _global state_. 

### Developer productivity
* [Fire and motion](https://www.joelonsoftware.com/2002/01/06/fire-and-motion/): The struggle with developer productivity in a nutshell. [_Joel Spolsky_]

### Git
* [Fortunately I don't squash my git commits](https://blog.ploeh.dk/2020/10/05/fortunately-i-dont-squash-my-commits/): A long bug hunting journey as a testament to not squashing commits. [_Mark Seemann_]

### Regex
* [Regex cheatsheet](https://paul.copplest.one/knowledge/tech/regex.html): Paul Copplestone's **regex cheatsheet** [_Paul Copplestone_]

## Web development
* [Move over JavaScript: Back-end languages are coming to the front-end](https://github.com/readme/featured/server-side-languages-for-front-end): Overview of different approaches to implement server-side rendering for complex web UIs.

### REST APIs
* [What RESTful actually means](https://codewords.recurse.com/issues/five/what-restful-actually-means): A meaningful description of what characterizes a RESTful application with links for further learning.
* [How did REST come to mean the opposite of REST](https://htmx.org/essays/how-did-rest-come-to-mean-the-opposite-of-rest/): A very good description of what really is a REST API (which MUST use hypermedia in its interface). It describes all the required characteristics of a true REST API and states that JSON APIs are definitely NOT REST APIs.

### HTML
* [HTML cheatsheet](https://paul.copplest.one/knowledge/tech/html-cheatsheet.html): Paul Copplestone's HTML cheatsheet [_Paul Copplestone_]

### CSS
* [Learning CSS animations by example](https://leerob.io/blog/learning-css-animations-by-example): An example implementation of a CSS animation.
* [CSS 'text-shadow' examples](https://www.sitepoint.com/moonlighting-css-text-shadow/): `text-shadow` property examples for CSS text styling.

### HTTP(S)
* [Conditional HTTP GET: The fastest requests need no response body](https://ieftimov.com/post/conditional-http-get-fastest-requests-need-no-response-body/): Handling server content update with ETags and Last-Modified _header fields_ in order to generate user-agent content caching [_Ilija Eftimov_]
* [Decrypting your own HTTPS traffic with Wireshark](https://www.trickster.dev/post/decrypting-your-own-https-traffic-with-wireshark/): Properly configuring Wireshark with the keys to decrypt local HTTPS traffic fow debugging and hacking

### Security
* [Do login forms need tokens against CSRF attacks?](https://stackoverflow.com/questions/6412813/do-login-forms-need-tokens-against-csrf-attacks): From StackOverflow, is it necessary to protect login forms against CSRF (Cross-site request forgery) attacks?
* [Exotic HTTP Headers](https://peteris.rocks/blog/exotic-http-headers/): In-depth explanation of HTTP Headers used to prevent all kinds of attacks XSS, Clickbaiting, etc.

## Design
### Web design
* [Why Japanese web design is so... different](https://randomwire.com/why-japanese-web-design-is-so-different/): An explanation about the cultural differences and the socio-technological context that makes some big Japanese web sites feel so different, like if they stayed behind within the web design paradigms of the 90s.
* [DALL·E 2 and the origin of vibe shift](https://every.to/divinations/dall-e-2-and-the-origin-of-vibe-shifts): How and why webdesign vibes shift over time. 
* [How stripe designs beautiful websites](https://leerob.io/blog/how-stripe-designs-beautiful-websites): Design principles taken from the design-centric Stripe webpages.

## FreeBSD sysadmin
* [Personal FreeBSD sysadmin cheatsheet](/FreeBSDSysadmin.md)

## General sysadmin
* [Cron best practices](https://blog.sanctum.geek.nz/cron-best-practices/): Best practices to manage and setup cronjobs in a secure way, e.g. periodically monitoring a web service with a cron job.
* [Land chad's guide to setting up a webserver](https://landchad.net/domain): Step by step guide by Luke Smith on how to setup a server, its domain, firewall, etc... [_Luke Smith_]
* [htop explained](https://peteris.rocks/blog/htop/): An in-depth guide into working with `htop`/`top`.

### Networking
* [Using UFW as a Firewall](https://landchad.net/ufw): Very minimalistic/simple guide to configure UFW on a server. [_Luke Smith_]
* [Firewalld in CentOS 8](https://www.digitalocean.com/community/tutorials/how-to-set-up-a-firewall-using-firewalld-on-centos-8): Configuring firewalld in CentOS 8. [_DigitalOcean_]

### Docker
* [Personal Docker cheatsheet](/DockerCheatsheet.md)
* [Docker cheatsheet](https://paul.copplest.one/knowledge/tech/docker.html): Docker cheatsheet [_Paul Copplestone_]
* [Docker -t flag (StackOverflow)](https://stackoverflow.com/questions/30137135/confused-about-docker-t-option-to-allocate-a-pseudo-tty): An explanation about the `-t` flag in Docker.

### OS
* [Choosing between FreeBSD and OpenBSD](https://unixsheikh.com/articles/choosing-between-openbsd-and-freebsd.html): Reasoning behind choosing between FreeBSD or OpenBSD [_Unix Sheikh_]

## Site reliability
* [Implementing health checks](https://aws.amazon.com/builders-library/implementing-health-checks/): An article about the reasoning behind implementing health checks and how they are implemented at AWS.
* [Monitoring small web services](https://jvns.ca/blog/2022/07/09/monitoring-small-web-services/): A guide to implement uncomplicated monitoring for tiny not-critical webservices. [_Julia Evans_]
* [Google's literature about SRE](https://sre.google/books/): Three O'Reilly books available online about SRE at Google's scale.

## Unix
* [A list of new(ish) command line tools](https://jvns.ca/blog/2022/04/12/a-list-of-new-ish--command-line-tools/): A list of _modern_ Unix command line tools, to improve on classic Unix command line tools. [_Julia Evans_]
* [Filesystem Hierarchy Standard](https://www.pathname.com/fhs/pub/fhs-2.3.html): Understanding the traditional Unix way of using the filesystem hierarchy.

## systemd
* [systemd.service(5) man page](https://man7.org/linux/man-pages/man5/systemd.service.5.html): systemd.service(5) man page. It explains all the parameters that can be used when developing a service daemon and writing its service file for systemd.

## Observability
* [Logging v. instrumentation](https://peter.bourgon.org/blog/2016/02/07/logging-v-instrumentation.html): Difference between logging and instrumentation, best practices for both. [_Peter Bourgon_]

## Concurrency
* [Scheduling In Go : Part I - OS Scheduler](https://www.ardanlabs.com/blog/2018/08/scheduling-in-go-part1.html): Description of how an OS scheduler works with multiple threads and the performance challenges faced by a multi-threaded program. [_William Kennedy_]

## Databases
* [How does database indexing work?](https://stackoverflow.com/questions/1108/how-does-database-indexing-work): Stackoverflow discussion about how database indexing works and why it is useful. It provides other links to other threads discussing the same topic.
* [PostgreSQL cheatsheet](https://paul.copplest.one/knowledge/tech/postgresql.html): PostgreSQL cheatsheet [_Paul Copplestone_]

### SQL
* [Animate SQL](https://animatesql.com/): Animated web resource to better the functionality of SQL commands in a graphical way.

### MongoDB
* [Securing MongoDB](https://www.vultr.com/docs/securing-mongodb): Basic configuration steps to secure a newly started MongoDB instance. [_Vultr Docs_]
* [Beginners questions about MongoDB (StackOverflow)](https://stackoverflow.com/questions/3490272/some-beginners-questions-about-mongodb): Why are there an admin and a local collections and some very simple queries.

## SaaS/Business
* [An Engineer's view of venture capital](https://spectrum.ieee.org/amp/an-engineers-view-of-venture-capitalists-2650252508): The pitfalls that an engineer will encounter while seeking VC money for a start-up. [_Nick Tredennick_]
* [Pricing low touch SaaS](https://stripe.com/en-gb-de/atlas/guides/saas-pricing)
* [Profit sharing](https://paul.copplest.one/blog/profit-sharing.html): A rather unorthodox approach to profit sharing in a private company. [_Paul Copplestone_]

## Security
### Random Number Generators
* [Banana Random Number Generator (Part 1)](https://www.valerionappi.it/brng-en/) [Part2](https://www.valerionappi.it/chi-squared/): A great introduction into the basics of RNGs, trying to verify true randomness in some numbers, Chi-Delta, etc. [_Valerio Nappi_]
### Malware
* [Malware targetting AWS Lambda](https://www.cadosecurity.com/cado-discovers-denonia-the-first-malware-specifically-targeting-lambda/): A malware written in Go that targets AWS Lambda functions.

## Academia
* [You should be reading academic CS papers](https://stackoverflow.blog/2022/04/07/you-should-be-reading-academic-computer-science-papers/): A Stackoverflow blog post recommending resources to get access to good academic computer science papers. [_Stackoverflow Blog_]

## Misc
* [How to become a full-time creator as a software engineer](https://blog.pragmaticengineer.com/how-to-become-a-full-time-creator/): Different approaches to move from being an employee to starting as a 'creator'/self-employed. [_Gergely Orosz_]
