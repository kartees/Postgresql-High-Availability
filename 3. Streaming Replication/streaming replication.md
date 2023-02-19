# Streaming Replication - Postgresql

intro
-  continous ship and apply the WAL records to number of standby servers

- implements the master slave configuration
- uses pgpool or HAproxy for load balancing the primary and replica db servers
- lag is very low
- asynchronous by default

on Asynchronous
- pros:
- fast response time
- cons
- data read on replicate may not be fresh
- data may be lost in case of failover

on Synchronous
- pros:
- suitable for failover
- daa read on replica will be fresh
- cons:
- longer response time

- need to be careful when choosing sync and async
- add replication server on the pg_hba.conf
- pg_basebackup connects primary with the replica

