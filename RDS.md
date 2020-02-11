1. Durablity
   1. Multi-AZ
      1. feature
         1. synchronous.
      2. create
         1. from single-az
            * snapshot
            * instance
            * synchronous replication configure
         2. failover
            1. flips cname to standby
            2. spend minutes.
      3. affect
         1. backup
            1. occure on standby
   2. RDS proxy
      1. reduce failover time.
2. performance
   1. read replicas
      1. feature
         1. can be in another region
      2. versions
         1. auto backup on replica need mysql5.6~
         2. posgresql 9.3.5~
         3. oracle 12.1.0.2.v12~
      3. API
         1. CreateDBInstanceReadReplica 
            1. specify multi-az
            2. region will specified with the endpoint.
            3. SourceDBInstanceIdentifier
               1. specify a valid DB instance ARN when other region
               2. specify DB instance identifier when same region
      4. RDS proxy
         1. connect pooling
      5. limit
         1. 5 read replicas
         2. only asynchronous.
         3. two tier replica
            1. mysql, mariadb, aurora
3. monitor
   1. feature
      1. collect os metrics and process info
  1. limit
     1. rds console
        1. 1 hour back granularity of 1 s.
        2. longer history with cloudwatch but with granularity of 1m.