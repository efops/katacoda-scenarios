You can also specify IP addresses or network address block that is allowed to access your NTP server.

`# Allow NTP client access from local network.
allow 0.0.0.0/24`

If you have active firewall service, allow ntp port.

`ufw allow ntp `{{execute "HOST1"}}

`ufw reload`{{execute "HOST1"}}

Check if NTP server is working.

`chronyc sources`{{execute "HOST1"}}