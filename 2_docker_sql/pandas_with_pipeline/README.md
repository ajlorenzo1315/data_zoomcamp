##
### final


<pre>
~/Escritorio/data-engineering-zoomcamp/data_zoomcamp/2_docker_sql/pandas_with_pipeline$ sudo docker build -t test:pandas .
[+] Building 0.0s (9/9) FINISHED                                                
 => [internal] load .dockerignore                                          0.0s
 => => transferring context: 2B                                            0.0s
 => [internal] load build definition from dockerfile                       0.0s
 => => transferring dockerfile: 159B                                       0.0s
 => [internal] load metadata for docker.io/library/python:3.9              0.0s
 => [1/4] FROM docker.io/library/python:3.9                                0.0s
 => [internal] load build context                                          0.0s
 => => transferring context: 103B                                          0.0s
 => CACHED [2/4] RUN pip install pandas                                    0.0s
 => CACHED [3/4] WORKDIR /the/workdir/path                                 0.0s
 => [4/4] COPY pipelines.py pipelines.py                                   0.0s
 => exporting to image                                                     0.0s
 => => exporting layers                                                    0.0s
 => => writing image sha256:f464aff2623a9d4a1bc4430d57a25fe58936e50172612  0.0s
 => => naming to docker.io/library/test:pandas 
</pre>
<pre>

$ sudo docker run -it test:pandas
root@3f3799167042:/the/workdir/path# ls
pipelines_copy.py
root@3f3799167042:/the/workdir/path# python pipelines_copy.py
pipeline works!!
root@3f3799167042:/the/workdir/path# 

</pre>

### errores 
dockerfile:
<pre>

FROM python:3.9

RUN pip install pandas

COPY pipelines.py

ENTRYPOINT [ "bash"]
</pre>

<pre>

alourido@GRAD0356UBUNTU:~/Escritorio/data-engineering-zoomcamp/data_zoomcamp/2_docker_sql/pandas_with_pipeline$ sudo docker build -t test:pandas .
[+] Building 0.0s (2/2) FINISHED                                                
 => [internal] load build definition from dockerfile                       0.0s
 => => transferring dockerfile: 119B                                       0.0s
 => [internal] load .dockerignore                                          0.0s
 => => transferring context: 2B                                            0.0s
dockerfile:5
--------------------
   3 |     RUN pip install pandas
   4 |     
   5 | >>> COPY pipelines.py
   6 |     
   7 |     ENTRYPOINT [ "bash"]
--------------------
ERROR: failed to solve: dockerfile parse error on line 5: COPY requires at least two arguments, but only one was provided. Destination could not be determined.


</pre>

solución

<pre>

FROM python:3.9

RUN pip install pandas

COPY pipelines.py pipelines.py

ENTRYPOINT [ "bash"]
</pre>