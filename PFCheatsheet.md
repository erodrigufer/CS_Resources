<!-- vim-markdown-toc GFM -->

* [References](#references)
* [Commands](#commands)
	- [Tables](#tables)

<!-- vim-markdown-toc -->

## References
* [OpenBSD Handbook of pf](https://www.openbsdhandbook.com/pf/).

## Commands

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
