My notes and binaries for installing LFS
========================================

I have forked taql's empty repository, because it was first result of Git-Hub's search.

I decided to install my LFS in VirtualBox. I hope it is good decision. All steps should be repeatable on non-virtual machine. I allso decided not to copy any binaries into my repository. In my opinion it isn't the purpose of repository like this. So enyone who starts with LFS can just clone my repository and start compiling :)

Day1 - Create Virtual Machine
-----------------------------
Time consume: 2h

I created VirtualBox VM with 10GB Dunamically allocated VDI drive. Then i downloaded ubuntu server as distribution which creates partitions and builds initial system. This will i install on special 5GB virtual drive. I'll delete this drive after i will be done. I have downloaded [Ubuntu 12.04 LTS 32 bit - server](http://www.ubuntu.com/download/server/thank-you?distro=server&release=lts&bits=32).

I have installed ubuntu server with all default settings.

After booting system, i have installed git and i checkouted this repository. With `bash version-check.sh` i checked which required software i have and then installed the rest with `sudo apt-get install xyz`. In Ubuntu `awk` link in `usr/bin/awk` points to `mawk` so i delete it and replace it with `ln -s gawk awk`.

Day2 - Preparings
-----------------
Time consume: 30 min

### Preparing new partition
With `sudo cfdisk` i have created 3 partitions:
* 100MB boot partition, that is supposed to be mounted to /boot
* 8GB root partition
* 400MB swap partition

And then with:
`
sudo mkfs sda1 -t ext2
sudo mkfs sda2 -t ext3
sudo mkswap ext3
`
i created filesystems.

`debugfs -R sdaX` showed me exactly what it shoud.. I'm glad, that ubuntu's makefs didn't gave me some addition problems. After i mounted sda1 to %LFS and sda2 to %LFS/boot i used wget list for download packages and other sources.
