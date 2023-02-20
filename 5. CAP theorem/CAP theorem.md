# CAP theorem & Postgres vs Cassandara

CAP - Consistency Availability Partition tolerance

if limit exceeds we can scale server by
- vertically means increasing the capacity
- horizontally means adding additional machines

example for more scable solution - casssandra (distributed & No SQL )

cassandra
- less flexible in functionality
- dont provide easy searching
- no consistency in ACID principle

postgres
- supports high concurrent isoled transactions
- provide all in ACID principle
- however all in single machine

can we structure postgres like cassandra ? 
basically its NO
but can done by CAP theorem
- a distributed data storage can support only two of the three following features at a time
    - partition tolerance
    - consistency
    - availability

Cassandra vs postgres

cassandra
- basically cassandra provides availability and partition tolerance 
- if node breaks it doesn't breaks the whole db

postgres
- basically consistent and available but not normally seperated in partitions
- not a distributed system

usecases:
- banking -> consistency is more important and then partial availability is lower requirement
- instagram -> high-volume , consistency is not important, availability is important

