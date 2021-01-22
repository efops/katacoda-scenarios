## Copying your Public SSH Key to a Server Manually

If you do not have password-based SSH access available, you will have to add your public key to 
the remote server manually.

On your local machine, you can find the contents of your public key file by typing:

`cat /home/ubuntu/.ssh/id_rsa.pub`{{execute HOST1}}

You can copy this value, and manually paste it into the appropriate location on the remote server. 

On the remote server, create the `~/.ssh` directory if it does not already exist:

`mkdir -p /home/ubuntu/.ssh`{{execute HOST2}}

Afterwards, you can create or append the `~/.ssh/authorized_keys` file by typing:

`echo public_key_string >> /home/ubuntu/.ssh/authorized_keys`{{copy}}