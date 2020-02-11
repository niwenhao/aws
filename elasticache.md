1. feature
   1. auto discovery
      1. named endpoint
      2. DNS
      3. query
      4. return question include all nodes
      5. select a node to invoke api
2. limit
   1. 250 nodes and shards. 170.6TB
   2. Nodes
      1. single cluster
         1. 1~20 for memcache
         2. 1 for redis.
      2. full
         1. 300 reserved nodes
         2. 100 nodes per region
      3. 5 read replicas(redis)
3. maintence
   1. 60 m.
4. billing
   1. node
   2. data transfer in/out ec2
5. Security
   1. Without VPC \
        enable host in specific "EC2 security groups"
   2. With VPC \
      Route or ACL
   3. Subnet Group
   4. Encryption
      1. communication
6. Durible
   1. Multi-AZ
   2. Cluster
   3. Read replica
      1. Perpose
         1. Scale out read wokrloads.
         2. Protect reade capacity when master failed.
         3. Data protection.
      2. asyncronous.
      3. Same region only.
   4. Failover
      1. DNS move to read replica.
   5. Backup
      1. for redis only.
      2. cause a short period of long latency.
      3. Backup window
7. For redis
   1. shards
      1. partions
   2. replica
