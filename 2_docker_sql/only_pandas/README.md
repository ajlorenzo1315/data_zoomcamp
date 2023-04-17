
## creando nuestro dockerfile 

docker buildx build [OPTIONS] PATH | URL | -

-t, --tag stringArray               Name and optionally a tag (format:
                                      "name:tag")


<pre>

alourido@GRAD0356UBUNTU:~/Escritorio/data-engineering-zoomcamp/data_zoomcamp/2_docker_sql$ sudo docker build -t test:pandas .
[+] Building 9.7s (6/6) FINISHED                                                
 => [internal] load .dockerignore                                          0.0s
 => => transferring context: 2B                                            0.0s
 => [internal] load build definition from dockerfile                       0.0s
 => => transferring dockerfile: 98B                                        0.0s
 => [internal] load metadata for docker.io/library/python:3.9              0.0s
 => [1/2] FROM docker.io/library/python:3.9                                0.0s
 => [2/2] RUN pip install pandas                                           8.7s
 => exporting to image                                                     0.9s
 => => exporting layers                                                    0.9s
 => => writing image sha256:7b5da16089a6daea016868ce18069089e77a83904eaec  0.0s 
 => => naming to docker.io/library/test:pandas                             0.0s 

</pre>

## ejecutando nuestro dockerfile

<pre>

$ sudo docker run -it test:pandas
root@912a104afd35:/# python
Python 3.9.16 (main, Apr 12 2023, 14:54:44) 
[GCC 10.2.1 20210110] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> import pandas
>>> 
>>> pandas.__version__
'2.0.0'

</pre>
