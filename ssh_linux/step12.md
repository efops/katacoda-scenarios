## Server-Side Configuration Options

This section contains some common server-side configuration options that can shape the way that your server responds and what types of connections are allowed.
Disabling Password Authentication

If you have SSH keys configured, tested, and working properly, it is probably a good idea to disable password authentication. This will prevent any user from signing in with SSH using a password.

To do this, connect to your remote server and open the `/etc/ssh/sshd_config` file with root 
or sudo privileges:

`sudo nano /etc/ssh/sshd_config`{{execute HOST2}}

Inside of the file, search for the `PasswordAuthentication` directive. If it is commented out, 
uncomment it. Set it to `no` to disable password logins:

```shell
PasswordAuthentication no
```
After you have made the change, save and close the file. To implement the changes, you should restart the SSH service.

`sudo systemctl restart ssh`{{execute HOST2}}

Now, all accounts on the system will be unable to log in with SSH using passwords.