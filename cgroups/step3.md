## Install openjdk

Where it's going to get crisp is when we're going to want to install openjdk-8-jdk:

`apt update && apt -y install openjdk-8-jdk`{{execute}}

Oops, we just encountered an error telling us that we were out of memory: `Cannot allocate memory`; 
cgroups or coincidence?