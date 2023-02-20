# Pgbouncer

- handle large amount of concurrent connections
- postgres handles 350 concurrent connections per

pgbouncer 
- rock solid in connection pooling
- reduces connection cost
- time consuming
- keeps an array of open connections and pool them
- quickly provide a connection to the application
- sort of proxy
- ideal for very large connection pools 

HA with pgbouncer
- pgbouncer itself can't help for deploying postgres with high availability
- so we need HA proxy or Pgpool load balancing capabilities with pgbouncer

configs
- edit the database configuration on the pgbouncer.ini file
- store the db users data on the userlist.txt file

- connect the database with the port of pgbouncer instead of postgres port
- for connection we get log entries 

advanced settings
- set min_pool_size -> important if many connections are created at the same time
- set default_pool_size -> connections per user
- max_client_conn -> no. of clients that can connect

pool modes
- session (default) -> safest | until client disconnects
- transaction -> if transaction is done, connection reassigns to another pool
- statement -> highly aggressive | returns connection back to pool immediately at end of statement

