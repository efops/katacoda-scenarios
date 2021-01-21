Set NTP synchronization.

`timedatectl set-ntp true`{{execute "HOST2"}}

Start and enable the service.

`systemctl enable --now chronyd`{{execute "HOST2"}}

Verify the setting using the following command:

`chronyc sources`{{execute "HOST2"}}