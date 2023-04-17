# data_zoomcamp
Ejercicios del zoomcamp de datatalk 

# Instalar docker  
* [siguiendo](https://docs.docker.com/desktop/install/linux-install/)
* Versión docker-desktop-4.18.0-amd64

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

<pre>
$ sudo docker run -it ubuntu bash 
Unable to find image 'ubuntu:latest' locally
latest: Pulling from library/ubuntu
2ab09b027e7f: Pull complete 
Digest: sha256:67211c14fa74f070d27cc59d69a7fa9aeff8e28ea118ef3babc295a0428a6d21
Status: Downloaded newer image for ubuntu:latest
root@c7f6e7e77a8f:/# 

$ docker run -it ubuntu bash  # significa -it es interativo

</pre>

<pre>
sudo docker run -it python:3.9
Unable to find image 'python:3.9' locally
3.9: Pulling from library/python
b0248cf3e63c: Pull complete 
127e97b4daf7: Pull complete 
0336c50c9f69: Pull complete 
1b89f3c7f7da: Pull complete 
2d6277217976: Pull complete 
273fcda609d8: Pull complete 
10e914379794: Pull complete 
380814be3a80: Pull complete 
23224c967057: Pull complete 
Digest: sha256:2d8875d28ca023a9056a828518adcdd634ba03740e1e3b197c06eb4527c6152c
Status: Downloaded newer image for python:3.9
Python 3.9.16 (main, Apr 12 2023, 14:54:44) 
[GCC 10.2.1 20210110] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> pip install pandas
  File "<stdin>", line 1
    pip install pandas
        ^
SyntaxError: invalid syntax
>>> pip install pandas
  File "<stdin>", line 1
    pip install pandas
        ^
SyntaxError: invalid syntax
>>> exit
Use exit() or Ctrl-D (i.e. EOF) to exit
>>> exit
Use exit() or Ctrl-D (i.e. EOF) to exit
>>> 
KeyboardInterrupt
>>> 

</pre>
