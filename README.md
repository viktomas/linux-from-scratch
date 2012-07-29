My notes and binaries for installing LFS
========================================

I have forked taql's empty repository, because it was first result of Git-Hub's search.

I decided to install my LFS in VirtualBox. I hope it is good decision. All steps should be repeatable on non-virtual machine. I allso decided not to copy any binaries into my repository. In my opinion it isn't the purpose of repository like this. So enyone who starts with LFS can just clone my repository and start compiling :)

Day1 - Create Virtual Machine
-----------------------------
I created VirtualBox VM with 10GB Dunamically allocated VDI drive. Then i downloaded ubuntu server as distribution which creates partitions and builds initial system. This will i install on special 5GB virtual drive. I'll delete this drive after i will be done. I have downloaded [Ubuntu 12.04 LTS 32 bit - server](http://www.ubuntu.com/download/server/thank-you?distro=server&release=lts&bits=32).

I have installed ubuntu server with all default settings.

After booting system, i have installed git and i checkouted this repository.
