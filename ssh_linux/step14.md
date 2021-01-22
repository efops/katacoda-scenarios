## Limiting the Users Who can Connect Through SSH

To explicitly limit the user accounts who are able to log in through SSH, you can take a few different approaches, each of which involve editing the SSH daemon config file.

On your remote server, open this file now with root or sudo privileges:

`sudo nano /etc/ssh/sshd_config`{{execute HOST2}}

The first method of specifying the accounts that are allowed to login is using the `AllowUsers` directive. Search for the AllowUsers directive in the file. If one does not exist, create it anywhere. After the directive, list the user accounts that should be allowed to login through SSH:

`AllowUsers ubuntu`{{copy}}

Save and close the file. Restart the daemon to implement your changes.

`sudo systemctl restart ssh`{{execute HOST2}}

If you are more comfortable with group management, you can use the `AllowGroups` directive instead. If this is the case, just add a single group that should be allowed SSH access (we will create this group and add members momentarily):

`AllowGroups sudo`{{copy}}

Save and close the file.

Now, restart the SSH daemon to implement your changes.

`sudo systemctl restart ssh`{{execute HOST2}}