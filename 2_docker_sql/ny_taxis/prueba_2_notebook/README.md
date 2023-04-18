
Ahora copiamos y pegamso el siguiente comando en terminal

<pre>

docker run -it \
    -e POSTGRES_USER=root \
    -e POSTGRES_PASSWORD=root \
    -e POSTGRES_DB="ny_taxi" \
    -v $(pwd -P)/ny_taxi_progres_data:/var/lib/protgresql/data \
    -p 5432:5432 \
    postgres:13


</pre>

Luego ejecutamos el notebook de [yellow_taxi.ipynb](yellow_taxi.ipynb)


y luego en una terminal ejecutamos

<pre>
pgcli -h localhost -p 5432 -u root -d ny_taxi 
Server: PostgreSQL 13.10 (Debian 13.10-1.pgdg110+1)
Version: 3.5.0
Home: http://pgcli.com

root@localhost:ny_taxi> \dt
+--------+----------------------+-------+-------+
| Schema | Name                 | Type  | Owner |
|--------+----------------------+-------+-------|
| public | yellow_taxi_data_sql | table | root  |
+--------+----------------------+-------+-------+
SELECT 1
Time: 0.029s

root@localhost:ny_taxi> \d yellow_taxi_data_sql
+-----------------------+-----------------------------+-----------+
| Column                | Type                        | Modifiers |
|-----------------------+-----------------------------+-----------|
| index                 | bigint                      |           |
| Unnamed: 0            | bigint                      |           |
| VendorID              | bigint                      |           |
| tpep_pickup_datetime  | timestamp without time zone |           |
| tpep_dropoff_datetime | timestamp without time zone |           |
| passenger_count       | double precision            |           |
| trip_distance         | double precision            |           |
| RatecodeID            | double precision            |           |
| store_and_fwd_flag    | text                        |           |
| PULocationID          | bigint                      |           |
| DOLocationID          | bigint                      |           |
| payment_type          | bigint                      |           |
| fare_amount           | double precision            |           |
| extra                 | double precision            |           |
| mta_tax               | double precision            |           |
| tip_amount            | double precision            |           |
| tolls_amount          | double precision            |           |
| improvement_surcharge | double precision            |           |
| total_amount          | double precision            |           |
| congestion_surcharge  | double precision            |           |
:

root@localhost:ny_taxi>

</pre>

