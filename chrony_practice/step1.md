## Installing Chrony on Ubuntu master

Set timezone.

`timedatectl set-timezone Asia/Baku`{{execute "HOST1"}}

Chrony can be installed on Ubuntu from package manager.

`apt install -y chrony`{{execute "HOST1"}}

After the installation, start and enable `chronyd` service.

`systemctl enable --now chronyd`{{execute "HOST1"}}