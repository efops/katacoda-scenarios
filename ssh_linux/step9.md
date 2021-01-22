## Copying your Public SSH Key to a Server with SSH-Copy-ID

To copy your public key to a server, allowing you to authenticate without a password, a number of approaches can be taken.

If you currently have password-based SSH access configured to your server, and you have the 
`ssh-copy-id` utility installed, this is a simple process. The `ssh-copy-id` tool is included 
in many Linux distributions’ OpenSSH packages, so it very likely may be installed by default.

If you have this option, you can easily transfer your public key by typing:

`ssh-copy-id ubuntu@node01`{{execute HOST1}}

This will prompt you for the user account’s password on the remote system.

After typing in the password, the contents of your `~/.ssh/id_rsa.pub` key will be appended to 
the end of the user account’s `~/.ssh/authorized_keys` file.

You can now log in to that account without a password:

`ssh ubuntu@node01`{{execute HOST1}}