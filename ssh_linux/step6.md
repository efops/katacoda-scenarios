## Basic Connection Instructions

The following section will cover some of the basics about how to connect to a server with SSH.

### Connecting to a Remote Server

To connect to a remote server and open a shell session there, you can use the ssh command.

The simplest form assumes that your username on your local machine is the same as that on 
the remote server. If this is true, you can connect using:

`ssh remote_host`

If your username is different on the remoter server, you need to pass the remote user’s 
name like this:

`ssh ubuntu@node01`{{execute HOST1}}

If you are using password authentication, you will be prompted for the password for the 
remote account here. If you are using SSH keys, you will be prompted for your private key’s 
passphrase if one is set, otherwise you will be logged in automatically.