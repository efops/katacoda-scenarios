## Creating a Swap File

Now that we know our available hard drive space, we can create a swap file on our filesystem. We will allocate a file of the swap size that we want called swapfile in our root (/) directory.

The best way of creating a swap file is with the fallocate program. This command instantly creates a file of the specified size.

`fallocate -l 1G /swapfile`{{execute}}

If `fallocate` is not installed or if you get an error message saying `fallocate failed: Operation not supported` then you can use the following command to create the swap file:

`dd if=/dev/zero of=/swapfile bs=1024 count=1048576`{{execute}}

We can verify that the correct amount of space was reserved by typing:

`ls -lh /swapfile`{{execute}}