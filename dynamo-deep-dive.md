# DynamoDB Deep Dive

- relational data store optimizes storage... and requires CPU
- storage used to be expensive.. now CPU is the most expensive
- SQL = optimized for storage
- NoSQL = optimized for compute
- OLTP = online transaction processing
- OLAP = Online analyical processing
- dynamoDB = document or k/v, event driven programming, fully managed
- table row includes required partition key, optional sort key, and other attributes
- scaling includes breaking up key spaces across nodes
- partitions are three-way replicated... will get ack after two 
- default is eventually consistent reads... strong reads are twice the cost and read from primary
- local secondary indexes (LSI) .. new way to sort
- global secondary index (GSI) .. new way to group.. or sort

- nosql data modeling
    1. understand the use case -- transaction? analytical?
    2. identify access patterns -- document all workflows
        - r/w workloads
    3. data modeling -- 1 app service = 1 table
    4. review/repeat/review
- dynamodb streams and AWS Lambda
    -- think "stored procedrues"
    -- stream and lambda is separate from table
- "hierachies are celestial.  in hell all are equal"

- composite keys are used to create hierachies... allow scalable filtering
    -- example: `StatusDate` .. "PENDING_2018-09-08"
- **Transactions API - new API**
    -- full ACID implementation

- *Best Practices for DynamoDB* article on AWS site talks about how to do complex design into single table modelling

- Things are still relational
- ERD still matters