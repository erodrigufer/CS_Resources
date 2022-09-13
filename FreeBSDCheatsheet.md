# FreeBSD Cheatsheet

## Table of contents
<!-- vim-markdown-toc GFM -->

* [Release management](#release-management)
	- [Upgrading to a major release](#upgrading-to-a-major-release)
	- [Periodically downloading patches with cron](#periodically-downloading-patches-with-cron)

<!-- vim-markdown-toc -->

## Release management
### Upgrading to a major release
1. `freebsd-update -r 11.1-RELEASE upgrade` : Use the `-r` flag to specify the major release to which the system should be upgraded. `11.1-RELEASE` should be the name of the major release to which the system should be upgraded. `CURRENT` and `STABLE` branches cannot be upgraded with this command. This command will fetch all the data that has to be updated in the actual system and makes a comparison between the current files and the files that will be upgraded. It will tell you which files need to be modified to perform an upgrade.
2. `freebsd-update install` : This command will actually upgrade the system.
3. `reboot` : Reboot the host to properly install the kernel. After installing the new kernel, we can again proceed with an installation of userland features.
4. `freebsd-update install` : After rebooting the system (which properly finishes the installation of a new kernel), continue upgrading userland programs.
5. `freebsd-update install` : Remove old shared libraries (check _Absolute FreeBSD Chapter 18 for more detail information about this configuration step_). 
6. `reboot` : Reboot one final time to check that everything works properly and the system can be cleanly initialized after a reboot.

### Periodically downloading patches with cron
1. Add the command `freebsd-update cron` to the crontab at a specific hour with a given periodicity. This will periodically try to `fetch` patches for the current FreeBSD major release and will notify if a fetch successfully downloaded new patches.
