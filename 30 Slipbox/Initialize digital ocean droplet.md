---
created: 2024-05-16 17:39 
modified: Thursday 16th May 2024 17:39:13
alias: 
---
up::  [[How to deploy an api using Digital Ocean and Dokku]]
type:: #note/how-to
links::
## Initialize digital ocean droplet

1. Create [digital ocean](https://cloud.digitalocean.com/projects/30a9541f-c92b-4411-9533-7b51e0c2d737/resources?i=2a9ec8) droplet
2. SSH into the server 
**Generate ssh key**
```
ssh-keygen -t rsa -b 4096 
cat ~/.ssh/id_rsa.pub
```
**ssh into the server using that key**
```
ssh -i ~/.ssh/id_rsa root@5.161.114.220
```
3. [Install docker](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-20-04)
```
sudo apt update
sudo apt install apt-transport-https ca-certificates curl software-properties-common
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable"
apt-cache policy docker-ce
sudo apt install docker-ce
sudo systemctl status docker
```
5. [Install dokku](https://dokku.com/docs/getting-started/installation/)
```
wget -NP . https://dokku.com/install/v0.34.4/bootstrap.sh
sudo DOKKU_TAG=v0.34.4 bash bootstrap.sh
cat ~/.ssh/authorized_keys | dokku ssh-keys:add admin
```
6. set your global domain
```
# you can also use the ip of your server 
dokku domains:set-global 134.209.38.244.sslip.io
```

