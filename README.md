# data_zoomcamp
Ejercicios del zoomcamp de datatalk 

# Instalar docker  
* [siguiendo](https://docs.docker.com/desktop/install/linux-install/)
* Versión docker-desktop-4.18.0-amd64

## nueva instalación 

### Prerequisitos
<pre>

sudo apt-get purge docker-ce docker-ce-cli containerd.io
sudo rm -rf /var/lib/docker
sudo apt install gnome-terminal
sudo apt remove docker-desktop
rm -r $HOME/.docker/desktop
sudo rm /usr/local/bin/com.docker.cli
sudo apt purge docker-desktop

</pre>

### intalación  using the apt repository

**Set up the repository**

Update the apt package index and install packages to allow apt to use a repository over HTTPS:
<pre>

sudo apt-get update
sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg
</pre>
Add Docker’s official GPG key and set up the repository:
<pre>
sudo install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
sudo chmod a+r /etc/apt/keyrings/docker.gpg

echo \
  "deb [arch="$(dpkg --print-architecture)" signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  "$(. /etc/os-release && echo "$VERSION_CODENAME")" stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null


</pre>


Add Docker’s official GPG key and set up the repository:
<pre>
sudo install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
sudo chmod a+r /etc/apt/keyrings/docker.gpg

echo \
  "deb [arch="$(dpkg --print-architecture)" signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  "$(. /etc/os-release && echo "$VERSION_CODENAME")" stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null


</pre>


sudo apt-get install ./docker-desktop-4.18.0-amd64.deb

prueba docker run hello-world



<pre>


$systemctl --user start docker-desktop

$ docker compose version
Docker Compose version v2.17.2

$ docker --version
Docker version 23.0.3, build 3e7cbfd

$ docker version
Cannot connect to the Docker daemon at unix:///home/alourido/.docker/desktop/docker.sock. Is the docker daemon running?
Client: Docker Engine - Community
 Cloud integration: v1.0.31
 Version:           23.0.3
 API version:       1.42
 Go version:        go1.19.7
 Git commit:        3e7cbfd
 Built:             Tue Apr  4 22:06:10 2023
 OS/Arch:           linux/amd64
 Context:           desktop-linux


</pre>

<pre>

$ sudo docker run hello-world
Unable to find image 'hello-world:latest' locally
latest: Pulling from library/hello-world
2db29710123e: Pull complete 
Digest: sha256:4e83453afed1b4fa1a3500525091dbfca6ce1e66903fd4c01ff015dbcb1ba33e
Status: Downloaded newer image for hello-world:latest

Hello from Docker!
This message shows that your installation appears to be working correctly.

To generate this message, Docker took the following steps:
 1. The Docker client contacted the Docker daemon.
 2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
    (amd64)
 3. The Docker daemon created a new container from that image which runs the
    executable that produces the output you are currently reading.
 4. The Docker daemon streamed that output to the Docker client, which sent it
    to your terminal.

To try something more ambitious, you can run an Ubuntu container with:
 $ docker run -it ubuntu bash

Share images, automate workflows, and more with a free Docker ID:
 https://hub.docker.com/

For more examples and ideas, visit:
 https://docs.docker.com/get-started/

</pre>

[Week 1: Introduction & Prerequisites](2_docker_sql)

para parar el docker
<pre>
ocker_sql/ny_taxis/prueba_1$ sudo service docker stop

Warning: Stopping docker.service, but it can still be activated by:
  docker.socket

alourido@GRAD0356UBUNTU:~/Escritorio/data-engineering-zoomcamp/data_zoomcamp/2_docker_sql/ny_taxis/prueba_1$ sudo systemctl disable docker.service
Synchronizing state of docker.service with SysV service script with /lib/systemd/systemd-sysv-install.
Executing: /lib/systemd/systemd-sysv-install disable docker

alourido@GRAD0356UBUNTU:~/Escritorio/data-engineering-zoomcamp/data_zoomcamp/2_docker_sql/ny_taxis/prueba_1$ sudo service docker stop
Warning: Stopping docker.service, but it can still be activated by:
  docker.socket

alourido@GRAD0356UBUNTU:~/Escritorio/data-engineering-zoomcamp/data_zoomcamp/2_docker_sql/ny_taxis/prueba_1$ sudo systemctl stop docker.socket

alourido@GRAD0356UBUNTU:~/Escritorio/data-engineering-zoomcamp/data_zoomcamp/2_docker_sql/ny_taxis/prueba_1$ sudo service docker stop

</pre>