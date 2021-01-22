## Generating an SSH Key Pair

Generating a new SSH public and private key pair on your local computer is the first step towards authenticating with a remote server without a password. Unless there is a good reason not to, you should always authenticate using SSH keys.

A number of cryptographic algorithms can be used to generate SSH keys, including RSA, DSA, and ECDSA. RSA keys are generally preferred and are the default key type.

To generate an RSA key pair on your local computer, type:

`ssh-keygen`{{execute HOST1}}

This procedure has generated an RSA SSH key pair, located in the `.ssh` hidden directory within your user’s home directory. These files are:

* `~/.ssh/id_rsa`: The private key. DO NOT SHARE THIS FILE!
* `~/.ssh/id_rsa.pub`: The associated public key. This can be shared freely without consequence.
