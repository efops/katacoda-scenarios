Set NTP synchronization.

`timedatectl set-ntp true`{{execute "T2"}}

Start and enable the service.

`systemctl enable chrony`{{execute "T2"}}

Verify the setting using the following command:

`chronyc sources`{{execute "T2"}}