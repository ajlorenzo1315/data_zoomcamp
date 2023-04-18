##

* docker run: Comando de Docker utilizado para crear y ejecutar un contenedor de Docker.
* -it: Opción que indica que el contenedor se ejecutará en modo interactivo y se conectará a la terminal.
* -postgres:13: Especifica la imagen de Docker que se utilizará para crear el contenedor.
* -e POSTGRES_USER="nytaxi": Especifica una variable de entorno llamada POSTGRES_USER con el valor nytaxi.
* -e POSTGRES_PASSWORD="nytaxi": Especifica una variable de entorno llamada POSTGRES_PASSWORD con el valor nytaxi.
* -e POSTGRES_DB="ny_taxi": Especifica una variable de entorno llamada POSTGRES_DB con el valor ny_taxi.
* -v ny_taxi_progres_data:/var/lib/protgresql/dara: Monta un volumen llamado ny_taxi_progres_data en la ruta /var/lib/protgresql/dara dentro del contenedor. dockquer necesita el path completo por lo que pndremso :
    /home/alourido/Escritorio/data-engineering-zoomcamp/data_zoomcamp/2_docker_sql/ny_taxis/prueba_1/ny_taxi_progres_data:/var/lib/protgresql/dara 
    (pwd)/ny_taxi_progres_data:/var/lib/protgresql/dara 
* -p 5432:5432: Mapea el puerto 5432 del contenedor al puerto 5432 del host.
* postgres:13: Especifica la imagen de Docker que se utilizará para crear el contenedor.

En resumen, esta línea de comandos crea y ejecuta un contenedor de Docker a partir de la imagen postgres:13. El contenedor se ejecuta en modo interactivo y se conecta a la terminal. Se especifican tres variables de entorno para configurar la base de datos PostgreSQL dentro del contenedor. También se monta un volumen para almacenar los datos de la base de datos y se mapea el puerto 5432 del contenedor al puerto 5432 del host.

Ahora copiamos y pegamso el siguiente comando en terminal

<pre>

docker run -it \
    -e POSTGRES_USER="root" \
    -e POSTGRES_PASSWORD="root" \
    -e POSTGRES_DB="ny_taxi" \
    -v $(pwd -P)/ny_taxi_progres_data:/var/lib/protgresql/data \
    -p 5432:5432 \
    postgres:13


docker run -it \
    -e POSTGRES_USER="root" \
    -e POSTGRES_PASSWORD="root" \
    -e POSTGRES_DB="ny_taxi" \
    -v /home/alourido/Escritorio/data-engineering-zoomcamp/data_zoomcamp/2_docker_sql/ny_taxis/prueba_1/ny_taxi_progres_data:/var/lib/protgresql/data \
    -p 5432:5432 \
    postgres:13

</pre>

<pre>
alourido@GRAD0356UBUNTU:~/Escritorio/data-engineering-zoomcamp/data_zoomcamp/2_docker_sql/ny_taxis/prueba_1$ sudo docker run -it \
>     -e POSTGRES_USER=root \
>     -e POSTGRES_PASSWORD=root \
>     -e POSTGRES_DB="ny_taxi" \
>     -v $(pwd -P)/ny_taxi_progres_data:/var/lib/protgresql/data \
>     -p 5432:5432 \
>     postgres:13
The files belonging to this database system will be owned by user "postgres".
This user must also own the server process.

The database cluster will be initialized with locale "en_US.utf8".
The default database encoding has accordingly been set to "UTF8".
The default text search configuration will be set to "english".

Data page checksums are disabled.

fixing permissions on existing directory /var/lib/postgresql/data ... ok
creating subdirectories ... ok
selecting dynamic shared memory implementation ... posix
selecting default max_connections ... 100
selecting default shared_buffers ... 128MB
selecting default time zone ... Etc/UTC
creating configuration files ... ok
running bootstrap script ... ok
performing post-bootstrap initialization ... ok
syncing data to disk ... ok

initdb: warning: enabling "trust" authentication for local connections
You can change this by editing pg_hba.conf or using the option -A, or
--auth-local and --auth-host, the next time you run initdb.

Success. You can now start the database server using:

    pg_ctl -D /var/lib/postgresql/data -l logfile start

waiting for server to start....2023-04-17 13:36:18.686 UTC [48] LOG:  starting PostgreSQL 13.10 (Debian 13.10-1.pgdg110+1) on x86_64-pc-linux-gnu, compiled by gcc (Debian 10.2.1-6) 10.2.1 20210110, 64-bit
2023-04-17 13:36:18.687 UTC [48] LOG:  listening on Unix socket "/var/run/postgresql/.s.PGSQL.5432"
2023-04-17 13:36:18.691 UTC [49] LOG:  database system was shut down at 2023-04-17 13:36:18 UTC
2023-04-17 13:36:18.694 UTC [48] LOG:  database system is ready to accept connections
 done
server started
CREATE DATABASE


/usr/local/bin/docker-entrypoint.sh: ignoring /docker-entrypoint-initdb.d/*

2023-04-17 13:36:18.869 UTC [48] LOG:  received fast shutdown request
waiting for server to shut down....2023-04-17 13:36:18.870 UTC [48] LOG:  aborting any active transactions
2023-04-17 13:36:18.870 UTC [48] LOG:  background worker "logical replication launcher" (PID 55) exited with exit code 1
2023-04-17 13:36:18.871 UTC [50] LOG:  shutting down
2023-04-17 13:36:18.877 UTC [48] LOG:  database system is shut down
 done
server stopped

PostgreSQL init process complete; ready for start up.

2023-04-17 13:36:18.994 UTC [1] LOG:  starting PostgreSQL 13.10 (Debian 13.10-1.pgdg110+1) on x86_64-pc-linux-gnu, compiled by gcc (Debian 10.2.1-6) 10.2.1 20210110, 64-bit
2023-04-17 13:36:18.994 UTC [1] LOG:  listening on IPv4 address "0.0.0.0", port 5432
2023-04-17 13:36:18.994 UTC [1] LOG:  listening on IPv6 address "::", port 5432
2023-04-17 13:36:18.995 UTC [1] LOG:  listening on Unix socket "/var/run/postgresql/.s.PGSQL.5432"
2023-04-17 13:36:18.997 UTC [63] LOG:  database system was shut down at 2023-04-17 13:36:18 UTC
2023-04-17 13:36:19.000 UTC [1] LOG:  database system is ready to accept connections
2023-04-17 13:40:45.944 UTC [1] LOG:  database system is ready to accept connections



</pre>

En otra terminal  para comprobar si nos conectamos correctamente

<pre>

alourido@GRAD0356UBUNTU:~/Escritorio/data-engineering-zoomcamp/data_zoomcamp/2_docker_sql/ny_taxis$ pgcli -h localhost -p 5432 -u root -d ny_taxi
Password for root: 
Server: PostgreSQL 13.10 (Debian 13.10-1.pgdg110+1)
Version: 3.5.0
Home: http://pgcli.com
root@localhost:ny_taxi> \dt
+--------+------+------+-------+
| Schema | Name | Type | Owner |
|--------+------+------+-------|
+--------+------+------+-------+
SELECT 0
Time: 0.019s
root@localhost:ny_taxi> exit
Goodbye!


</pre>
## Error 

<pre>
docker run -it postgres:13 \
    -e POSTGRES_USER="nytaxi" \
    -e POSTGRES_PASSWORD="nytaxi" \
    -e POSTGRES_DB="ny_taxi" \
    -v $(pwd -P)/ny_taxi_progres_data:/var/lib/protgresql/data \
    -p 5432:5432 \
    postgres:13
</pre>

<pre>
alourido@GRAD0356UBUNTU:~/Escritorio/data-engineering-zoomcamp/data_zoomcamp/2_docker_sql/ny_taxis/prueba_1$  sudo docker run -it postgres:13 \
>     -e POSTGRES_USER="nytaxi" \
>     -e POSTGRES_PASSWORD="nytaxi" \
>     -e POSTGRES_DB="ny_taxi" \
>     -v $(pwd -P)/ny_taxi_progres_data:/var/lib/protgresql/dara \
>     -p 5432:5432 \
>     postgres:13
[sudo] contraseña para alourido: 
Unable to find image 'postgres:13' locally
13: Pulling from library/postgres
26c5c85e47da: Pull complete 
1c30a4c3f519: Pull complete 
d5c0f1ae682d: Pull complete 
1b1b2890ec0f: Pull complete 
391087799df7: Pull complete 
b413b4057e31: Pull complete 
4fa4edfeab8b: Pull complete 
b0a4d596bc61: Pull complete 
8753c36b2ab1: Pull complete 
37eb6768c4ad: Pull complete 
cf064c836270: Pull complete 
40b552c18d4e: Pull complete 
ed1c42edf868: Pull complete 
Digest: sha256:67edfda7deeecfda8e40c9b00818eae76573a9e9466ba7edbc536662d128173b
Status: Downloaded newer image for postgres:13
Error: Database is uninitialized and superuser password is not specified.
       You must specify POSTGRES_PASSWORD to a non-empty value for the
       superuser. For example, "-e POSTGRES_PASSWORD=password" on "docker run".

       You may also use "POSTGRES_HOST_AUTH_METHOD=trust" to allow all
       connections without a password. This is *not* recommended.

       See PostgreSQL documentation about "trust":
       https://www.postgresql.org/docs/current/auth-trust.html

</pre>


## error
<pre>

 pgcli -h localhost -p 5432 -u root -d ny_taxi
Traceback (most recent call last):
  File "/home/alourido/.local/bin/pgcli", line 5, in <module>
    from pgcli.main import cli
  File "/home/alourido/.local/lib/python3.8/site-packages/pgcli/main.py", line 2, in <module>
    from pgspecial.namedqueries import NamedQueries
  File "/home/alourido/.local/lib/python3.8/site-packages/pgspecial/__init__.py", line 12, in <module>
    from . import dbcommands
  File "/home/alourido/.local/lib/python3.8/site-packages/pgspecial/dbcommands.py", line 7, in <module>
    from psycopg.sql import SQL
  File "/home/alourido/.local/lib/python3.8/site-packages/psycopg/__init__.py", line 9, in <module>
    from . import pq  # noqa: F401 import early to stabilize side effects
  File "/home/alourido/.local/lib/python3.8/site-packages/psycopg/pq/__init__.py", line 114, in <module>
    import_from_libpq()
  File "/home/alourido/.local/lib/python3.8/site-packages/psycopg/pq/__init__.py", line 106, in import_from_libpq
    raise ImportError(
ImportError: no pq wrapper available.
Attempts made:
- couldn't import psycopg 'c' implementation: No module named 'psycopg_c'
- couldn't import psycopg 'binary' implementation: No module named 'psycopg_binary'
- couldn't import psycopg 'python' implementation: libpq library not found


</pre>

## solución

<pre>
$ sudo apt-get install libpq-dev
</pre>