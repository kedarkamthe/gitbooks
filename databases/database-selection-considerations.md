# ⚒️ Database selection considerations



1. Identify type data like structured or unstructured&#x20;
2. Identify whether a system is read-heavy or write-heavy based on Read and write Volume.
   1. Identify the volume of reads per day
   2. Identify the volume of writes(including Create, Update, and Delete) per day
3. Identify what relationships need to be supported&#x20;
   1. one -one&#x20;
   2. one-to-many&#x20;
   3. many-to-one
   4. many-to-many
4. Identify How Failover is handled in case of an outage&#x20;
5. Identify how Availability is managed and does replication is supported
6. Identify how scalability is managed&#x20;
7. Identify cost-effectiveness
8. Identify Team skillset and awareness/comfort about database&#x20;
9. RDBMS:&#x20;
   1. Can we leverage transactional capabilities like ACID
   2. Suits well for structured data where data can be normalized in multiple tables
   3. Writes like  Create, Update, and Delete can be handled efficiently
   4. Queries that involve multiple joins as data spread across multiple tables may reduce the performance of read operations
10. NoSql:
    1.
