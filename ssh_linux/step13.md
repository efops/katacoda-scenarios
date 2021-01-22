## Changing the Port that the SSH Daemon Runs On

Some administrators suggest that you change the default port that SSH runs on. This can help decrease the number of authentication attempts your server is subjected to from automated bots.

To change the port that the SSH daemon listens on, you will have to log in to your remote server.
Open the `sshd_config` file on the remote system with root privileges, either by logging in 
with that user or by using `sudo`:

`sudo nano /etc/ssh/sshd_config`{{execute HOST2}}

Once you are inside, you can change the port that SSH runs on by finding the Port `22` 
specification and modifying it to reflect the port you wish to use. For instance, to change 
the port to `4444`, put this in your file:

`#Port 22
Port 4444
`{{copy}}

Save and close the file when you are finished. To implement the changes, you must restart the SSH daemon.

`sudo systemctl restart ssh`{{execute HOST2}}

After the daemon restarts, you will need to authenticate by specifying the port number (demonstrated in an earlier section).