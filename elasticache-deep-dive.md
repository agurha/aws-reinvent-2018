# ElastiCache Deep Dive: Design Patterns for In-Memory Data Stores

- shared = primary + replica
- Redis v5 signifanctly more performance than v4
- redis streams are new
- redis = most popular in-memory key/valye store
- understands various data structures.. hashes, streams, sorted sets..
- Elasticache is a managed service for scaling Redis/memcached
- data costs b/t VPCs are free with Elasticache.. self-managing would induce cost
- use cases:
    1. caching
    2. chat apps
    3. message queues
    4. machine learning
    5. media streaming
    6. real-time analytics
    7. session store
- vertical topology
    - scaleds vertically.. limited to large resources
- most popular topology: horiztonally scale
    - holds cluster map of shards
- read: https://docs.aws.amazon.com/elasticache/index.html#lang/en_us
- read: https://medium.com/@denisanikin/when-and-why-i-use-an-in-memory-database-or-a-traditional-database-management-system-5737f6d406b5
- cost per instance, not per operation
- common architectures:
    1. fast input.. then other consumers can pull from redis stream for other events
    1. aws iot core.. time series storage
    1. filtering streams .. e.g. kinesis
    1. mobile w/ geospatial redis + dynamo as primary db
    1. rate limiter
    1. graph + search integration w/ neptune as graph and redis for additonal info
- Caching Patterns:
    1. lazy loading -- assume in cache, if not, then lookup and write into cache
    2. proactively hydrating cache
- cluster sizing best practices:
    1. foe more read... add replicas
    1. for more write, add shards (scale out)
    1. for more network IO, use network noptiized instances and sacle out
    1. use pipelining for bulk reads/writes
- optimize using TTLs and eviction policies
- isolation: no isolation $ -> isolation by purpose $$ -> full isolation $$$
- recommendation: cloudwatch monitoring on everything
    - bytes used
    - aim for 80% cache hit
    - current connections
    - CPU utilization.. should not go over 90% allocation
    - evictions >1 .. if evictios.. should scale out
    - swap usage > few MBs .. should not use any.. at this point its just disk storage