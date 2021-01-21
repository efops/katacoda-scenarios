##Namespaces

The simplest example and which best illustrates the notion of namespace is the PID namespace. 
Your bash shell is one of the processes running on the machine you are on. 
It certainly has as its parent an sshd process, which itself has as its parent 
`/ usr / bin / sshd -D` which ultimately has as its parent `/ sbin / init` 
which is process 1.

You can see this just by running the command:

`
ps -ef
`{{execute}}

You can also by this command find the ID of your process (PID):

`echo $$`{{execute}}

It's time to isolate yourself by creating a namespace for your shell:

`unshare --fork --pid --mount-proc bash`{{execute}}

Now you are alone in the process:

`ps -ef`{{execute}}

And your shell now sees itself as the first process in the system, with PID 1:

`echo $$`{{execute}}