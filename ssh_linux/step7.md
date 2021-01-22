## Running a Single Command on a Remote Server

To run a single command on a remote server instead of spawning a shell session, you can add 
the command after the connection information, like this:

`ssh ubuntu@node01 date -R`{{execute HOST1}}

This will connect to the remote host, authenticate with your credentials, and execute the 
command you specified. The connection will immediately close afterwards.