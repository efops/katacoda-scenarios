## Adding new user

First off all we need to add new user with following command (in the first host):

`adduser ubuntu`{{execute HOST1}}

Then we need to add this user to `sudo` group, in order to have administrative rights (in the first host).

`usermod -aG sudo ubuntu`{{execute HOST1}}

Then we need to do the same for second host.

`adduser ubuntu`{{execute HOST2}}

`usermod -aG sudo ubuntu`{{execute HOST2}}

Then we need to change user in both machine to our new user.

First Host:

`su - ubuntu`{{execute HOST1}}

Second Host:

`su - ubuntu`{{execute HOST2}}