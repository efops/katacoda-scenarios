## Enabling the Swap File

Now that we have a file of the correct size available, we need to actually turn this into swap space.

First, we need to lock down the permissions of the file so that only the users with root privileges can read the contents. This prevents normal users from being able to access the file, which would have significant security implications.

Make the file only accessible to **root** by typing:

`chmod 600 /swapfile`{{execute}}

Verify the permissions change by typing:

`ls -lh /swapfile`{{execute}}

As you can see, only the **root** user has the read and write flags enabled.

We can now mark the file as swap space by typing:

`mkswap /swapfile`{{execute}}

After marking the file, we can enable the swap file, allowing our system to start using it:

`swapon /swapfile`{{execute}}

Verify that the swap is available by typing:

`swapon --show`{{execute}}

We can check the output of the free utility again to corroborate our findings:

`free -h`{{execute}}