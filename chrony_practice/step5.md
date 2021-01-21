Set NTP synchronization.

`timedatectl set-ntp true`{{execute "node01"}}

Start and enable the service.

`systemctl enable chrony`{{execute "node01"}}

Verify the setting using the following command:

`chronyc sources`{{execute "node01"}}