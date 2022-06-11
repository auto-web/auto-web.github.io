# Requirements

## Debian-based OS

AutoWeb is tightly coupled with Debian packages configuration.

As it may be possible to install it on another operating system, we recommend setting up a Debian 11 (Bullseye) blank server to begin.

## Partitions and disks

Ideally, the disks should have been partitionned as follow :
 - `/` : the root filesystem
 - `/data` : a partition or disk that will hold all the users files. This partition will be configured with Quota ON.
 - `/var` : a partition of disk that will hold variable data, such as MySQL databases.
