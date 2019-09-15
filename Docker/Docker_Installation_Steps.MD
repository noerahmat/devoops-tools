# Installing Docker on Amazon Linux server

1.Update packages
```sh 
yum update -y
```
2.Install docker
```sh 
yum install docker -y
```


# Docker Installation on CentOS server
##### Referance URL : https://docs.docker.com/install/linux/docker-ce/centos/#install-using-the-repository
### PREREQUISITES

Please follow below steps to install docker CE on CentoOS server instance. For RedHat only Docker EE available 

1.Install required packages.

```sh 
sudo yum install -y yum-utils \
  device-mapper-persistent-data \
  lvm2
  
  ```
  
2.Use the following command to set up the stable repository.
 
 ```sh 
 sudo yum-config-manager \
    --add-repo \
    https://download.docker.com/linux/centos/docker-ce.repo
```

### INSTALLING DOCKER CE

1.Install the latest version of Docker CE.
```sh 
sudo yum install docker-ce
```

If prompted to accept the GPG key, verify that the fingerprint matches 
060A 61C5 1B55 8A7F 742B 77AA C52F EB6B 621E 9F35, and if so, accept it.

2.Start Docker.
```sh 
sudo systemctl start docker
```

3.Verify that docker is installed correctly by running the hello-world image.
```sh
sudo docker run hello-world
```
##########################################################################################################

Install Docker & Docker Compose - Centos 7
### Step 1 — Install Docker

Install needed packages:
```sh
sudo yum install -y yum-utils device-mapper-persistent-data lvm2
```
Configure the docker-ce repo:

```sh
sudo yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
```

Install docker-ce:
```sh
sudo yum install docker-ce
```

Add your user to the docker group with the following command.

```sh
sudo usermod -aG docker $(whoami)
```

Set Docker to start automatically at boot time:

```sh
sudo systemctl enable docker.service
```

Finally, start the Docker service:

```sh
sudo systemctl start docker.service
```

### Step 2 — Install Docker Compose

Install Extra Packages for Enterprise Linux

```sh
sudo yum install epel-release
```

Install python-pip

```sh
sudo yum install -y python-pip
```

Then install Docker Compose:

```sh
sudo pip install docker-compose
```

You will also need to upgrade your Python packages on CentOS 7 to get docker-compose to run successfully:

```sh
sudo yum upgrade python*
```

To verify a successful Docker Compose installation, run:

$ docker-compose version


########################################################################################################
#!/bin/sh

```sh
curl -fsSL https://get.docker.com -o get-docker.sh
sh get-docker.sh
```

#cek
#docker --version

#install docker compose

```sh
sudo apt  install docker-compose -y
```
#cek
#docker-compose --version


#install docker machine

```sh
base=https://github.com/docker/machine/releases/download/v0.16.0 &&
  curl -L $base/docker-machine-$(uname -s)-$(uname -m) >/tmp/docker-machine &&
  sudo install /tmp/docker-machine /usr/local/bin/docker-machine
```

#cek
#docker-machine --version


#sudo user docker
#sudo groupadd docker

```sh
sudo usermod -aG docker $USER
```

### !!!!!
sudo reboot

```sh
docker login
```

# !!cannot-login-to-docker-account

```sh
sudo apt install gnupg2 pass
```

#set access
```sh
sudo chown "$USER":"$USER" /home/"$USER"/.docker -R
sudo chmod g+rwx "$HOME/.docker" -R
```

