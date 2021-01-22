## Generate an SSH Key Pair with a Larger Number of Bits

SSH keys are 2048 bits by default. This is generally considered to be good enough for security, but you can specify a greater number of bits for a more hardened key.

To do this, include the `-b` argument with the number of bits you would like. Most servers support keys with a length of at least 4096 bits. Longer keys may not be accepted for DDOS protection purposes:

`ssh-keygen -b 4096`{{execute HOST1}}

If you had previously created a different key, you will be asked if you wish to overwrite your previous key:

`Overwrite (y/n)?`

If you choose “yes”, your previous key will be overwritten and you will no longer be able to log in to servers using that key. Because of this, be sure to overwrite keys with caution.