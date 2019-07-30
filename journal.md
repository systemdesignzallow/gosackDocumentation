
# SDC Journal

## 7/29/19
 * Incorperated comments into code from team lead.
 * Abstracted functionality for server into model.
 * Created Artillery script and seperated helper functions for benchmarking.
 * Revised routes for proper error handling.
 * Abstracted fake script for arbitrary record generation, output path. Added commandline arguments and export.

## 7/27/19
* Chose MariaDB based on metrics and research.
* Wrote database defense.
* Got basic querying working through nodejs.
* Have service working with MariaDB backend.
* Rebuilt data with address field due to mistake in generation.
* Looking at artillery for stress testing

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
