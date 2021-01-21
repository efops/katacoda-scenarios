## Tuning your Swap Settings

Swappiness is a Linux kernel property that defines how often the system will use the swap space. Swappiness can have a value between 0 and 100. A low value will make the kernel to try to avoid swapping whenever possible, while a higher value will make the kernel to use the swap space more aggressively.

The default swappiness value is 60. You can check the current swappiness value by typing the following command:

`cat /proc/sys/vm/swappiness`{{execute}}

While the swappiness value of 60 is OK for most Linux systems, for production servers, you may need to set a lower value.

For example, to set the swappiness value to 10, you would run the following sysctl command:

`sysctl vm.swappiness=10`{{execute}}

To make this parameter persistent across reboots append the following line to the `/etc/sysctl.conf` file:

`nano /etc/sysctl.conf`{{execute}}

At the bottom, you can add:

`vm.swappiness=10`{{copy}}

## How to remove Swap File

If for any reason you want to deactivate and remove the swap file, follow these steps:

First, deactivate the swap by typing:

`swapoff -v /swapfile`{{execute}}

Remove the swap file entry `/swapfile none swap sw 0 0` from the `/etc/fstab file`.

Finally, delete the actual `swapfile` file using the `rm` command:

`rm /swapfile`{{execute}}