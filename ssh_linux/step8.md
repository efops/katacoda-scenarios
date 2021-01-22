## Logging in to a Server with a Different Port

By default the SSH daemon on a server runs on port `22`. Your SSH client will assume that this is 
the case when trying to connect. If your SSH server is listening on a non-standard port 
(this is demonstrated in a later section), you will have to specify the new port number when 
connecting with your client.

You can do this by specifying the port number with the `-p` option:

`ssh -p 22 ubuntu@node01`{{execute HOST1}}

To avoid having to do this every time you log in to your remote server, you can create or edit
a configuration file in the `~/.ssh` directory within the home directory of your local computer.

Edit or create the file now by typing:

`sudo nano /home/ubuntu/.ssh/config`{{execute HOST1}}

In here, you can set host-specific configuration options. To specify your new port, use a 
format like this:

``` 
Host remote_alias
   User username
   HostName remote_host
   Port port_num
```
This will allow you to log in without specifying the specific port number on the command line.