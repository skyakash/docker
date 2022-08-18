**Create a Docker VM with Ubuntu 22.04.01 LTS**

1. Create a VM with Ubuntu 22.04.01 LTS, username: docker22, machine name: docker22
2. update the VM
3. Install openssh so that we can connect to nodes via ssh
```
sudo apt-get update
sudo apt-get install openssh-server -y
```
4. Note IP address of VMs
```
ip a
```
