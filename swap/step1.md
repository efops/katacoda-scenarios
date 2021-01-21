## Checking the System for Swap Information

Before we begin, we can check if the system already has some swap space available. It is possible to have multiple swap files or swap partitions, but generally one should be enough.

We can see if the system has any configured swap by typing:

`swapon --show`{{execute}}

If you don’t get back any output, this means your system does not have swap space available currently.

You can verify that there is no active swap using the free utility:

`free -h`{{execute}}

If you get output, that means there is already a swap. So firstly we need to remove it.

`swapoff -a`{{execute}}

Then we need to remove swap file entry from `/etc/fstab`.

`sed '/swap/d' /etc/fstab`{{execute}}