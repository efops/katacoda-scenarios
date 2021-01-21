## cgroups

Let's start by creating a cgroup:

> Normally the `cgcreate` command is already installed, but if it is not, start by executing:

`apt -y install cgroup-tools`{{execute}}

Next:

`cgcreate -a root -g memory:efkan`{{execute}}

So far we haven't placed any limits on it, but let's take a look at what's been created:

`ls -l /sys/fs/cgroup/memory/efkan`{{execute}}

Among all these files, there is one called `memory.kmem.limit_in_bytes`. 
This is the one we'll use to set a 10M limit (which isn't much):

`echo 10000000 >/sys/fs/cgroup/memory/efkan/memory.kmem.limit_in_bytes`{{execute}}

And finally, we'll put our shell in this cgroup, limiting it to using 10M of memory:

`cgexec -g memory:efkan bash`{{execute}}