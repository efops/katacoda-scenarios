## Disabling Root Login

It is often advisable to completely disable root login through SSH after you have set up an 
SSH user account that has `sudo` privileges.

To do this, open the SSH daemon configuration file with root or sudo on your remote server.

`sudo nano /etc/ssh/sshd_config`{{execute HOST2}}

Inside, search for a directive called `PermitRootLogin`. If it is commented, uncomment it. 
Change the value to “no”:

```shell
PermitRootLogin no
```
Save and close the file. To implement your changes, restart the SSH daemon.

`sudo systemctl restart ssh`{{execute HOST2}}

