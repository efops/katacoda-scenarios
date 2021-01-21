## Configure NTP Client on Ubuntu worker

Now that you have Chrony NTP Server installed and configured, you can configure NTP client.

Set timezone.

`timedatectl set-timezone Asia/Baku`{{execute "node01"}}

Install chrony and configure it as NTP client.

`apt install -y chrony`{{execute "node01"}}

Edit the configuration file to set NTP server to point your newly configured NTP server.

`nano /etc/chrony/chrony.conf`{{execute "node01"}}

`server 0.0.0.0`