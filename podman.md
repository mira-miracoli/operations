# Podman and Playbook Testing
This file gives a short introduction on podman. GalaxyEU will use this instead of Docker for testing Ansible Playbooks with GitHub Actions as part of CI.
## What is the difference between Podman and Docker?
Podman mirrors Docker's commands and it can be used as an alias (even if it might be confusing then).  Even the DockerHub is the standard registry and images are compatible between both runtimes.
Podman was developed by RedHat to add a native Systemd support for containers, which is also the reason why we use it. Let's keep it simple
and make a List of the main differences  
| Property | Docker | Podman |
| ----------- | ----------- | ------------ |
| root privilege | Daemon runns on root, </br> containers might be `--privileged` or not | Both Daemon and Containers can run as </br> `--privileged` or not |
|local repositiory </br> location | `/var/lib/docker` | `/var/lib/containers` and </br> `~/.local/share/containers` for </br> non-root|

## How do we use it?
Images are WIP and might consist of a Dockerfile which basically installs Ansible and copies and runs a playbook that then prepares the container. After that it can be considered as a 'normal VM' and playbooks can run against it.