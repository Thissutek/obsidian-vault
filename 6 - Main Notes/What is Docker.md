2025-07-11 03:09

Status:

Tag: [[Software Engineering]] [[DevOps]] [[Docker]]

## What is Docker
Docker is a tool that packages your app and everything it needs into a container its kind of like a mini virtual machine

But unlike VM's they share the host OS, start in seconds, use less memory/CPU and are easy to ship, version and run anywhere 

### Containers
a container is sandboxed process that runs your app with its own file system, dependencies and its own environment. But it use's the host OS kernel unlike VM's which simulate its own OS

### Why 
So all machines can run the program no more excuses where it doesn't work on my machine. 

### Key Terms
DockerFile - Script to run the containers image
Image - a snapshot of your app and its environment 
Container - the running instance of an image
Docker hub - like github a public repo for images
Volumes - Mounted folders or persistent data
Ports - Expose internal container ports to the outside world

"Package once run anywhere"
## References 