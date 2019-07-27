# Database Notes

## SQL

* mySQL
* Postgres
* SQlite

## need database for search optimised document store

## Redis for caching

Have leafs for increased read speed.
<https://mariadb.org/download/>
<https://medium.com/dev-bits/writing-memory-efficient-software-applications-in-node-js-5575f646b67f>

## Cassandra

* `cluster` is a container for `keyspaces`
* `keyspace` is the outermost container for data.
* `replication factor` the amount of nodes that will have duplicates of the data.
* `column family` roughly a table from a relational database

## `bash` Cassandra Helpers

```bash
sudo service cassandra active
```

```bash
nodetool status
```

```bash
cqlsh
```

## `cqlsh` Commands

```SQL
DESCRIBE keyspaces
```

List all keyspaces (outermost container for data) available.

```SQL
create keyspace dev ... with replication = {'class':'SimpleStrategy','replication_factor':1};
```

Create keyspace `dev`

```SQL
USE dev
```

Use keyspace `dev`

```SQL
create table emp (empid int primary key, ... emp_first varchar, emp_last varchar, emp_dept varchar);
```

Create column family `emp` in keyspace dev

```SQL
insert into emp (empid, emp_first, emp_last, emp_dept) ... values (1,'fred','smith','eng');
```

Insert data into `emp`

```SQL
select count(*) from dev.emp;`
```

Count records in keyspace `dev` column family `emp`

```SQL
COPY generalDescriptionService.homes(appliances,interiorFeatures,
construction,roof,exterior,flooring,homeId,homeAddress,price,beds,baths,rooms,stories,floorSize,spaces,houseDescription,houseType,yearBuilt,heating,cooling,parking,lotSize,daysListed,saves) FROM '~/data.csv' WITH DELIMITER=';' AND HEADER=TRUE;
```

import data

```SQL
drop table homes
```

Delete keyspace `homes`

```SQL
SELECT * FROM homes WHERE homeId=123;
```

Query example

`EXPAND ON`

Pretty Print

`TRACING ON`

Tracing on

## `generalDescriptionService` table

```sql
CREATE TABLE homes(
   appliances text,
   interiorFeatures text,
   construction text,
   roof text,
   exterior text,
   flooring text,
   homeId int PRIMARY KEY,
   homeAddress text,
   price int,
   beds int,
   baths int,
   rooms int,
   stories int,
   floorSize int,
   spaces text,
   houseDescription text,
   houseType text,
   yearBuilt int,
   heating text,
   cooling text,
   parking int,
   lotSize int,
   daysListed int,
   saves int
   );
```

## General Cassandra Use Case Notes

[ ] generate 10M records with node

cassandra - gossip
eventual consistency

* column oriented database
* key value pairs
* does not require empty positions to be filled with anything saving space
* fault tolerant, data is replicated to multiple nodes
* fast ***
* decentralized, no single point of failure
* scalable
* elastic, adding machines makes more performance
* no joins
* horizontal scaling to hit higher RPS

|Relational Database | NoSQL Database|
|-------------------|----------------|
|Handles data coming in low velocity|Handles data coming in high velocity|
|Data arrive from one or few locations|Data arrive from many locations|
|Manages structured data|Manages structured unstructured and semi-structured data.|
|Supports complex transactions (with joins)|Supports simple transactions
|single point of failure with failover|No single point of failure
|Handles data in the moderate volume.|Handles data in very high volume
|Centralized deployments|Decentralized deployments
|Transactions written in one location|Transaction written in many locations
|Gives read scalability|Gives both read and write scalability
|Deployed in vertical fashion|Deployed in Horizontal fashion

## CAP Theorem
![CAP Theorem](CAPTheoremDatabase.PNG)
* Available
* Consistant
* Partition Tolerant

Cassandra = AP
PostgreSQL = CA

<http://cassandra.apache.org/download/>

There are following features that Cassandra provides.

Massively Scalable Architecture: Cassandra has a masterless design where all nodes are at the same level which provides operational simplicity and easy scale out.
Masterless Architecture: Data can be written and read on any node.
Linear Scale Performance: As more nodes are added, the performance of Cassandra increases.
No Single point of failure: Cassandra replicates data on different nodes that ensures no single point of failure.
Fault Detection and Recovery: Failed nodes can easily be restored and recovered.
Flexible and Dynamic Data Model: Supports datatypes with Fast writes and reads.
Data Protection: Data is protected with commit log design and build in security like backup and restore mechanisms.
Tunable Data Consistency: Support for strong data consistency across distributed architecture.
Multi Data Center Replication: Cassandra provides feature to replicate data across multiple data center.
Data Compression: Cassandra can compress up to 80% data without any overhead.
Cassandra Query language: Cassandra provides query language that is similar like SQL language. It makes very easy for relational database developers moving from relational database to Cassandra.