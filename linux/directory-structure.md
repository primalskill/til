# Linux Directory Structure

1. `/` - 1st level.
2. `/usr` - 2nd level.
3. `/usr/local` - 3rd level.

The directories on each level usually repeat, e.g. `/bin` --> `/usr/bin` --> `/usr/local/bin`


```
/ - Root directory structure, everything is under root
├── /bin - Common system commands
├── /boot - Linux system boot files, anything necessary to boot up the system
├── /dev - Special device files
├── /etc - Configuration files for all proprams
│   └── /opt - Configuration files for binaries stored in /opt
├── /home - Users' home directory (example /home/george, /home/daniel, etc.)
├── /lib - System libraries
├── /media - Removable media mounts (e.g. cdrom, floppy, etc.)
├── /mnt - Temporary mounting points for devices (e.g. file system disks)
├── /opt - Optional packages by various software
├── /proc - Process and kernel info
├── /root - Home directory of the root user
├── /run - Runtime data, e.g. process PIDs
├── /sbin - System binaries essential for the system
├── /srv - Site-specific data (web scripts, ftp files, repositories)
├── /sys - Data about devices, kernel, etc.
├── /tmp - Temporary files, not preserved between system reboots
├── /usr - User data, usually read-only
│   ├── /bin - User binaries, not necessary for the system to work
│   ├── /lib - Libraries for user binaries
│   ├── /local - Local user data, specific to the host
│   │   └── /bin - Local user binaries, specific to the host
│   ├── /sbin - User services, daemons
│   └── /share - Shared data for user binaries
└── /var - Variable files that are expected to change
    ├── /cache - Cache data for various binaries
    ├── /lib - Data that's persisted by various binaries (e.g. databases)
    ├── /log - Various log files including system and non-essential binary logs
    ├── /run - Runtime variable data, usually a symlink to /run
    └── /tmp - Temporary data that are usually preserved between reboots, unlike /tmp
```

------------

**Refs**

- [Filesystem Hierarchy Standard](https://en.wikipedia.org/wiki/Filesystem_Hierarchy_Standard)
