## Installing Chrony on Ubuntu master

Set timezone.

`timedatectl set-timezone Asia/Baku`{{execute "controlplane"}}

Chrony can be installed on Ubuntu from package manager.

`apt install -y chrony`{{execute "controlplane"}}

After the installation, start and enable `chronyd` service.

`systemctl enable chrony`{{execute "controlplane"}}