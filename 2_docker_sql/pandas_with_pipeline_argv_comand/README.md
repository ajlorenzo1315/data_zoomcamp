##
### final
<pre>
~/Escritorio/data-engineering-zoomcamp/data_zoomcamp/2_docker_sql/pandas_with_pipeline_argv_comand$ sudo docker build -t test:pandas .
[+] Building 0.0s (9/9) FINISHED                                                
 => [internal] load .dockerignore                                          0.0s
 => => transferring context: 2B                                            0.0s
 => [internal] load build definition from dockerfile                       0.0s
 => => transferring dockerfile: 420B                                       0.0s
 => [internal] load metadata for docker.io/library/python:3.9              0.0s
 => [1/4] FROM docker.io/library/python:3.9                                0.0s
 => [internal] load build context                                          0.0s
 => => transferring context: 33B                                           0.0s
 => CACHED [2/4] RUN pip install pandas                                    0.0s
 => CACHED [3/4] WORKDIR /the/workdir/path                                 0.0s
 => CACHED [4/4] COPY pipelines.py pipelines_copy.py                       0.0s
 => exporting to image                                                     0.0s
 => => exporting layers                                                    0.0s
 => => writing image sha256:83e19dce0c1c14af6457c81e47cb87ed863598e27fbe9  0.0s
 => => naming to docker.io/library/test:pandas                             0.0s
</pre>
:~/Escritorio/data-engineering-zoomcamp/data_zoomcamp/2_docker_sql/pandas_with_pipeline_argv_comand$ sudo docker run -it test:pandas
['pipelines_copy.py', '1']
argunmento 1

<pre>

</pre>
### errores

docker file:
<pre>
FROM python:3.9

# intar dependencias
RUN pip install pandas

# path en el que se trabaja la copia siguiente
WORKDIR /the/workdir/path
# script que queresmos copiar y el nombre que le damos en el docker 
COPY pipelines.py pipelines_copy.py

# lo que quiero es que cuando al lanzar el docker es que realiza un python pipelines_copy.py
ENTRYPOINT ["python","pipelines_copy.py"]

</pre>

terminal

<pre>
~/Escritorio/data-engineering-zoomcamp/data_zoomcamp/2_docker_sql/pandas_with_pipeline_argv_comand$ sudo docker build -t test:pandas .
[+] Building 0.1s (9/9) FINISHED                                                
 => [internal] load .dockerignore                                          0.0s
 => => transferring context: 2B                                            0.0s
 => [internal] load build definition from dockerfile                       0.0s
 => => transferring dockerfile: 416B                                       0.0s
 => [internal] load metadata for docker.io/library/python:3.9              0.0s
 => [1/4] FROM docker.io/library/python:3.9                                0.0s
 => [internal] load build context                                          0.0s
 => => transferring context: 149B                                          0.0s
 => CACHED [2/4] RUN pip install pandas                                    0.0s
 => CACHED [3/4] WORKDIR /the/workdir/path                                 0.0s
 => [4/4] COPY pipelines.py pipelines_copy.py                              0.1s
 => exporting to image                                                     0.0s
 => => exporting layers                                                    0.0s
 => => writing image sha256:e78ba4f760224d8cbaaef009001b1bed811c039972b1d  0.0s
 => => naming to docker.io/library/test:pandas  
</pre>

<pre>

sudo docker run -it test:pandas
['pipelines_copy.py']
Traceback (most recent call last):
  File "/the/workdir/path/pipelines_copy.py", line 8, in <module>
    day=sys.argv[1]
IndexError: list index out of range


</pre>
## solución 

<pre>
FROM python:3.9

# intar dependencias
RUN pip install pandas

# path en el que se trabaja la copia siguiente
WORKDIR /the/workdir/path
# script que queresmos copiar y el nombre que le damos en el docker 
COPY pipelines.py pipelines_copy.py

# lo que quiero es que cuando al lanzar el docker es que realiza un python pipelines_copy.py
ENTRYPOINT ["python","pipelines_copy.py","1"]

</pre>
 
## solucion 2 
con el docker file anterior
<pre>

~/Escritorio/data-engineering-zoomcamp/data_zoomcamp/2_docker_sql/pandas_with_pipeline_argv_comand$ sudo docker run -it test:pandas 1
['pipelines_copy.py', '1']
argunmento 1


</pre>
 