# pf
## Table of contents
<!-- vim-markdown-toc GFM -->

* [References](#references)
* [Commands](#commands)
	- [Logging](#logging)
	- [Tables](#tables)

<!-- vim-markdown-toc -->

## References
* [OpenBSD Handbook of pf](https://www.openbsdhandbook.com/pf/).

## Commands

### Logging
* [OpenBSD Handbook of pf logging section](https://www.openbsdhandbook.com/pf/logging/): The section regarding logging of the OpenBSD pf Handbook is specially useful.

* Show current logs at `/var/log/pflog`:
```bash
tcpdump -n -e -ttt -r /var/log/pflog
```
The `tcpdump` command accepts arguments to filter the output.

* Show only packets that were **blocked**:
```bash
tcpdump -n -e -ttt -r /var/log/pflog action block

* action: block | pass
```

* Show only packets at a given **port**:
```bash
tcpdump -n -e -ttt -r /var/log/pflog port 22

```

* Show attempts of an **attacker** trying to brute-force a service at a particular port:
```bash
tcpdump -n -e -ttt -r /var/log/pflog action pass and port 27017

* action : Pass to show packets that were not blocked by pf.
* port : Show only attempts on port 27017 (MongoDB).
```

* Show packets being processed at a pflog interface in real-time:
```bash
tcpdump -n -e -ttt -i pflog0
```

### Tables
* Show members of a table:
```bash 
pfctl -t <TABLE_NAME> -T show

<TABLE_NAME> : Name of a table
```
* Show _counters_ of members of a table (for this option the table must originally be created with the _counters_ option). 

It will show the amount of packets blocked for a given member of the table (this option is useful to block SSH Bruteforce attackers).
```bash
pfctl -t <TABLE_NAME> -vvT show

<TABLE_NAME> : Name of a table
```
