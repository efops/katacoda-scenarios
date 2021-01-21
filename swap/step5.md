## Making the Swap File Permanent

Our recent changes have enabled the swap file for the current session. However, if we reboot, the server will not retain the swap settings automatically. We can change this by adding the swap file to our `/etc/fstab` file.

Back up the /etc/fstab file in case anything goes wrong:

`cp /etc/fstab /etc/fstab.bak`{{execute}}

`echo '/swapfile none swap sw 0 0' | sudo tee -a /etc/fstab`{{execute}}

Next we’ll review some settings we can update to tune our swap space.