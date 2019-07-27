
# SDC Journal

## 7/26/19

Loaded 10M records into MariaDB and have tested the speed of individual queries.
Documentation for this is in the [database](./database.md) file.
Completed benchmarking, but realized that I did not make an apples to apples 
comparison as I was running Cassandra on the Windows Subsystem for Linux
and I ran MariaDB on an Arch Linux install. The performance of MariaDB was 
7x faster and I find that a bit fishy... 
Documentation for the benchmarks are in the [database](./database.md) file.

## 7/25/19

Loaded 10M records into cassandra and have tested the speed of individual queries.
Documentation for this is in the [database](./database.md) file.

## 7/24/19

Generated the 1e7 records required for database testing.
Have researched Cassandra and am beginning the insertion of the data for taking metrics.
