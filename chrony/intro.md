## How to Install and Use Chrony in Linux (Ubuntu 20.04)

**Chrony** is a flexible implementation of the Network Time Protocol (NTP). It is used to synchronize the system clock from different NTP servers, reference clocks or via manual input.

It can also be used NTPv4 server to provide time service to other servers in the same network. It is meant to operate flawlessly under different conditions such as intermittent network connection, heavily loaded networks, changing temperatures which may affect the clock of ordinary computers.

Chrony comes with two programs:

* chronyc – command line interface for chrony
* chronyd – daemon that can be started at boot time