# Postgresql High Availability tutorial 

Steps to achieve HA
- use replicas
- Failover 
- Failback 

Requirements for HA 
- How critical is the data?
- what are the expectations for RTO (Recovery Time Objective) and RPO (Recovery Point Objective)?
- Do we need auto-failover?
- Do we need cross-center replication?
- Do we open replica servers for read requests?
- What are the known limitations and trade-offs for a specific solution?

Log Shipping
- old school of replicate data
- ship WAL log file from primary to replica and update changes on replica
- some lag 

Streaming replication
- fast and safe replication
- lag is minimal
- change sync and async ease (async -default)
- multiple levels (lesser durability - faster performance)

Logical Replication
- less common solution 
- good for some use cases but not for HA

Cascading Replication
- 3 replicas for primary 
- if primary down -> one replica become secondary

Synchronous vs Asynchronous Replication

Synchronous
- Synchronous slows down data modification drastically
- Network lag in synchronous
- reduced availability
- Not guarantee in durability

Asynchronous
- provide HA and better performance with low risk of data loss

Automatic Fail-over
- how to avoid downtime with replicas
- with some popular tools like pgpool-II , patroni (use consensus Key-value store)

Simple HA solution Example
- failover mechanism


Better HA solution Example
- client connects HA proxy to 2 DC of primary and replicas
- sync in same DC and async between 2 DCs
- patroni to make failover automatically
