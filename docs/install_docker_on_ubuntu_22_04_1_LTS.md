**Create a Docker VM with Ubuntu 22.04.01 LTS**

1. Create a VM with Ubuntu 22.04.01 LTS, username: docker22, machine name: docker22
2. update the VM
3. Install openssh so that we can connect to nodes via ssh
4. Install curl
```
sudo apt-get update
sudo apt-get install openssh-server -y
sudo apt install curl -y
```
5. Note IP address of VMs
```
ip a
```
6. Install Docker using convinience script
```
curl -fsSL https://get.docker.com -o get-docker.sh
chmod +x get-docker.sh
./get-docker.sh
```
7. Configure Docker for a non-privileged user
```
sudo sh -eux
apt-get install -y uidmap
exit 
#run following command as docker22 user
dockerd-rootless-setuptool.sh install
vi ~/.bashrc #and add following lines 
export PATH=/usr/bin:$PATH
export DOCKER_HOST=unix:///run/user/1000/docker.sock
```
8. Open a new SSH session as user docker22 and use docker
```
docker run hello-world
```
