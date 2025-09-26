# Apache Iceburg Quickstart Guide

## Step by step guide

1. Create docker-compose.yml file

2. Run docker
```bash
docker compose up -d
```

3. Run Spark session (SparkSQL)
```bash
docker exec -it spark-iceberg spark-sql
```

4. Creating a table

To create your first Iceberg table in Spark, run a CREATE TABLE command. Let's create a table using demo.nyc.taxis where demo is the catalog name, nyc is the database name, and taxis is the table name.

```sql
CREATE TABLE demo.nyc.taxis
(
  vendor_id bigint,
  trip_id bigint,
  trip_distance float,
  fare_amount double,
  store_and_fwd_flag string
)
PARTITIONED BY (vendor_id);
```

5. Writing Data to a Table
```sql
INSERT INTO demo.nyc.taxis
VALUES (1, 1000371, 1.8, 15.32, 'N'), (2, 1000372, 2.5, 22.15, 'N'), (2, 1000373, 0.9, 9.01, 'N'), (1, 1000374, 8.4, 42.13, 'Y');
```

6. Reading Data from a Table
```sql
SELECT * FROM demo.nyc.taxis;
```



## Reference
1. [Apache Iceberg™ - Spark](https://iceberg.apache.org/spark-quickstart/)
2. [PyIceberg - Python API](https://py.iceberg.apache.org/api/)