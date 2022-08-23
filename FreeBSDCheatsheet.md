# FreeBSD Cheatsheet

## Table of contents
<!-- vim-markdown-toc GFM -->

* [Release management](#release-management)
	- [Upgrading to a major release](#upgrading-to-a-major-release)

<!-- vim-markdown-toc -->

## Release management
### Upgrading to a major release
* `freebsd-update -r 11.1-RELEASE upgrade` : `11.1-RELEASE` should be the name of the major release to which the system should be upgraded. `CURRENT` and `STABLE` branches cannot be upgraded with this command.
