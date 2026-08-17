# Infrastructure Report – KillerCoda Linux Server

## Overview
This report documents the findings of an inspection of the Linux server provisioned in the KillerCoda Playground, performed as part of the Cloud Infrastructure Assessment for CloudNova Technologies prior to any production deployment.

## Server Findings

| Item | Command Used | Result |
|---|---|---|
| Operating System | cat /etc/os-release | Ubuntu 24.04.4 LTS (Noble Numbat) |
| Kernel Version | uname -r | 6.8.0-136-generic |
| CPU Model | lscpu | grep "Model name" | Intel Xeon E312xx (Sandy Bridge, IBRS update) |
| Number of CPU Cores | nproc | 1 |
| Total RAM | free -h | 1.9Gi total, 412Mi used, 871Mi free, 1.5Gi available |
| Disk Capacity | df -h | /dev/vda1: 19G total, 5.4G used, 13G available (30% used, mounted on /) |
| Mounted File Systems | mount | column -t | Root filesystem (/dev/vda1) is ext4; /boot (/dev/vda16) is ext4; /boot/efi (/dev/vda15) is vfat; plus virtual filesystems: sysfs, proc, devtmpfs, devpts, tmpfs, cgroup2, and others |
| Hostname | hostname | ubuntu |
| IP Address | hostname -I | 172.30.1.2 (and 172.17.0.1) |


## Notes
This environment behaves like a lightweight virtual machine rather than a full physical server — it has only 1 CPU core and around 2GB of RAM allocated, which is typical for a sandboxed cloud playground rather than a production instance. The root filesystem uses ext4, a standard Linux filesystem, while /boot/efi uses vfat, which is required for UEFI boot compatibility. The presence of a second IP (172.17.0.1) suggests a Docker bridge network is also active on this host in addition to the main network interface.
