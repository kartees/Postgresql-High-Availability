# Postgresql Partitioning Tutorial

intro
- crucial to keep the performance for databases with very large tables 
- when table size grow over time -> each operation costs more
- partitioning helps to divide it into small tables
- split large logical tables into small psychical tables

when to partition
- first sign is table size
- table bloat

how should partition tables
- access patterns - known either by knowing the application that access the database or by monitoring the logs and generating reports
- look for columns either in workloads or in join conditions
- access as few partitions possible

four methods on partition
- list  ( by categorize enum values)
- range ( most common ) ( by range value )
- hash  ( uses some hash like n % 3 = 0)
- composite ( sub partition ) ( multi level like both range and list )

two types of partitioning
- declarative  ( since postgres 10 - requires no maintenance - suits for more usecases )
- inheritance ( old - difficult to setup - write some code - more flexible)

table migration strategies
- traditional
- blue-green
- logical

example:
```
create table customers (id integer, age integer ) partition by range(age);
create table cust_young partition of customers for values from (MINVALUE) to (25);
```