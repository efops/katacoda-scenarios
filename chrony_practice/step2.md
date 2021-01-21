## Configuring Chrony on Ubuntu master

After the installation, you can make the changes on Chrony main configuration file
`/etc/chrony/chrony.conf`

One main configuration change you can make is to set the time servers closest to you.

`nano /etc/chrony.conf`{{execute "T1"}}

Comment out the first pool line and add a list of NTP servers.

`#pool 2.debian.pool.ntp.org offline iburst`

`server 2.az.pool.ntp.org
server 2.asia.pool.ntp.org
server 0.asia.pool.ntp.org`{{copy}}

Set NTP synchronization.

`timedatectl set-ntp true`{{execute "T1"}}

Restart `chronyd` service after making the change.

`systemctl restart chronyd`{{execute "T1"}}