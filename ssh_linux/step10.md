## Copying your Public SSH Key to a Server Without SSH-Copy-ID

If you do not have the `ssh-copy-id` utility available, but still have password-based SSH 
access to the remote server, you can copy the contents of your public key in a different way.

You can output the contents of the key and pipe it into the ssh command. On the remote side, 
you can ensure that the `~/.ssh` directory exists, and then append the piped contents into the 
`~/.ssh/authorized_keys` file:

`cat /home/ubuntu/.ssh/id_rsa.pub | ssh ubuntu@node01 "mkdir -p /home/ubuntu/.ssh && cat >> /home/ubuntu/.ssh/authorized_keys"`{{execute HOST1}}

After doing this, your key will be copied, allowing you to log in without a password:

`ssh ubuntu@node01`{{execute HOST1}}