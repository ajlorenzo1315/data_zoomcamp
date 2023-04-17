# first class

## Probando comandos basicos de una imagen de ubuntu
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
## Probando comandos basicos de una imagen de python 3.9
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
## Probando comandos basicos de una imagen de python 3.9 que nos permite instalar mas imagenes 
<pre> 
sudo docker run -it --entrypoint=bash  python:3.9
root@5323c6902302:/# pip install pandas
Collecting pandas
  Downloading pandas-2.0.0-cp39-cp39-manylinux_2_17_x86_64.manylinux2014_x86_64.whl (12.4 MB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 12.4/12.4 MB 19.3 MB/s eta 0:00:00
Collecting python-dateutil>=2.8.2
  Downloading python_dateutil-2.8.2-py2.py3-none-any.whl (247 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 247.7/247.7 KB 53.4 MB/s eta 0:00:00
Collecting tzdata>=2022.1
  Downloading tzdata-2023.3-py2.py3-none-any.whl (341 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 341.8/341.8 KB 32.9 MB/s eta 0:00:00
Collecting pytz>=2020.1
  Downloading pytz-2023.3-py2.py3-none-any.whl (502 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 502.3/502.3 KB 31.6 MB/s eta 0:00:00
Collecting numpy>=1.20.3
  Downloading numpy-1.24.2-cp39-cp39-manylinux_2_17_x86_64.manylinux2014_x86_64.whl (17.3 MB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 17.3/17.3 MB 20.6 MB/s eta 0:00:00
Collecting six>=1.5
  Downloading six-1.16.0-py2.py3-none-any.whl (11 kB)
Installing collected packages: pytz, tzdata, six, numpy, python-dateutil, pandas
Successfully installed numpy-1.24.2 pandas-2.0.0 python-dateutil-2.8.2 pytz-2023.3 six-1.16.0 tzdata-2023.3
WARNING: Running pip as the 'root' user can result in broken permissions and conflicting behaviour with the system package manager. It is recommended to use a virtual environment instead: https://pip.pypa.io/warnings/venv
WARNING: You are using pip version 22.0.4; however, version 23.1 is available.
You should consider upgrading via the '/usr/local/bin/python -m pip install --upgrade pip' command.

</pre>

[ejecutando_primer_docker_file](only_pandas)