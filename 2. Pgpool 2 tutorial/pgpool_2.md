 # Pgpool - II 

intro
- can build HA systems
-operative even failures
- scalability
- load balancing
- middleware with database clients and postgreSQL

Features
- scaling out processing capacity of database system by addding more servers
- use as load balancing
- provides connection pooling (lighter tool)
- automatic failover (with some script)
- High availability (no single point of failure) - watchdog redandency

obstacles
- split brain
- consistency vs Availability  (CAP theorem)

Configure pgpool with streaming replication
- Requirements: use PostgreSQl built-in streaming replication and pgpool as load balancing
- easy to setup and reliable

hands on (watch video - https://www.youtube.com/watch?v=qpxKlH7DBjU&list=PLBrWqg4Ny6vVwwrxjgEtJgdreMVbWkBz0)
-use pg_basebackup for create replication

Failover recap
- pgpoool detects postgres master is down
- failover script is executed
- failover script creates the trigger file on the replica
- postgresql replica detects the trigger file
- postgresql replica reboots in read/write mode and completes recovery
 



