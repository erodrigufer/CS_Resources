# FreeBSD Sysadmin Compendium
## Table of contents
<!-- vim-markdown-toc GFM -->

* [General sysadmin](#general-sysadmin)
	- [Installation](#installation)
* [Daemons](#daemons)
* [Monitoring](#monitoring)
* [Networking](#networking)
* [pf (Packet Filter)](#pf-packet-filter)
* [SSH](#ssh)
* [Databases](#databases)

<!-- vim-markdown-toc -->

## General sysadmin
* [Create a sudo user on FreeBSD](https://www.vultr.com/docs/create-a-sudo-user-on-freebsd): The real question is if it is even secured to install sudo on FreeBSD?
* [Explanation of colon operator in shell scripts](https://stackoverflow.com/questions/7444504/explanation-of-colon-operator-in-foo-value): Understanding the `: ${value}` syntax in FreeBSD shell scripts.

### Installation
* [Creating a FreeBSD bootable USB on OS X](https://hakk.dev/blog/posts/freebsd-usb-osx/): Step-by-step guide to properly format a USB stick to boot FreeBSD in a computer.

## Daemons
* [Supervised FreeBSD rc.d script for a Go daemon](https://redbyte.eu/en/blog/supervised-freebsd-init-script-for-go-deamon/): Run a go program as a supervised daemon in FreeBSD.
* [Practical rc.d scripting in BSD](https://docs.freebsd.org/en/articles/rc-scripting/index.html)
* [Write and auto-deploy daemons in FreeBSD](https://dev.to/zilti/updated-write-and-auto-deploy-daemons-on-freebsd-k7i): How to write and auto-deploy daemons using the `daemon(8)` FreeBSD functionality and rc.

## Monitoring
* [FreeBSD Install Logwatch Tool For Log Analysis and Monitoring](https://www.cyberciti.biz/faq/freebsd-unix-log-analyzer-configuration/): Tutorial on how to install and setup _Logwatch_ to get daily logs' analysis through emails.
* [Explaining top(1) on FreeBSD](https://klarasystems.com/articles/explaining-top1-on-freebsd/): Explaining the output of `top(1)` on FreeBSD.

## Networking
* [Check open ports on FreeBSD](https://linuxhint.com/check-open-ports-freebsd/): _sockstat_ command

## pf (Packet Filter)
* [OpenBSD Handbook pf cheat sheet](https://www.openbsdhandbook.com/pf/cheat_sheet/): OpenBSD Handbook section dedicated to pf.

## SSH
* [How to configure ssh key authentication on FreeBSD](https://www.digitalocean.com/community/tutorials/how-to-configure-ssh-key-based-authentication-on-a-freebsd-server)

## Databases
* [How to install MariaDB on FreeBSD](https://www.osradar.com/how-to-install-mariadb-on-freebsd-12/)
