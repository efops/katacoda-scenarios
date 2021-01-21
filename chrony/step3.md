## Configure Chrony

The configuration file of chrony is located at **/etc/chrony.conf** or **/etc/chrony/chrony.conf** 
and sample configuration file may look something like this:

```
server 0.rhel.pool.ntp.org iburst
server 1.rhel.pool.ntp.org iburst
server 2.rhel.pool.ntp.org iburst
server 3.rhel.pool.ntp.org iburst
 
stratumweight 0
driftfile /var/lib/chrony/drift
makestep 10 3
logdir /var/log/chrony
```

The above configuration provide the following information:

* **server** – this directive used to describe a NTP server to sync from.
* **stratumweight** – how much distance should be added per stratum to the sync source. The default value is 0.0001.
* **driftfile** – location and name of the file containing drift data.
* **Makestep** – this directive causes chrony to gradually correct any time offset by speeding or slowing down the clock as required.
* **logdir** – path to chrony’s log file.

If you want to step the system clock immediately and ignoring any adjustments currently being in progress, 
you can use the following command:

`chronyc makestep`{{execute}}

For to stop chrony, you can use the following command:

`systemctl stop chrony`{{execute}}