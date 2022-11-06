# Ubuntu

tags: #ubuntu

## Tips and Tricks

**Check version of Ubuntu**

`lsb_release -a`

**locale-gen: command not found**

**locale-gen en_US.UTF-8**

**ping: command not found**

`sudo apt install iputils-ping`

**Add user to docker group, using snap package manager**

```shell
sudo addgroup --system docker
sudo adduser $USER docker
newgrp docker
sudo snap disable docker
sudo snap enable docker
```