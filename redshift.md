# RedShift FAQs
## Feature
1. data warehouse.
2. column orient.
3. parallel query.
4. sophisticated query optimization.
5. redshift spectrum
   1. run sql query against s3 data lake.
6. load data
   1. from s3 dynamodb, emr, glue, data pipeline, ssh-enabled host.
   2. insert sql is slow.
   3. s3 or dynamodb is fast by parallel
## Durablity
1. drive failure
   1. use replica drive in same node
   2. move data to a healthy drive or node.
2. node failure
   1. hung service
   2. replace a failed node.
   3. load most frequently accessed data from s3
3. az failure
   1. hung until recover az
   2. create in other az by snapshort.
4. cann't multi-az
## Performance
1. scale out
   1. add compute node
   2. can not spectrum.
   3. concurrency scaling
      1. add transient capacity
      2. auto routes queries to scaling clusters.
   4. elastic resize
      1. add/remove nodes
2. avaliable during scale
   1. concurency scaling -> ok
   2. elastic resize -> hang fro 4 to 8 minutes.
   3. RA3 storage -> ok
      1. splite storage and compute node.
## Monitor
## Backup
1. continuous backup to s3
2. triple data
   1. origin
   2. replica on node
   3. s3
3. can asynchronously replicate to s3 in other region
## Security
1. ssl-enabled connecction
2. encrypt aes-256(redshift managed, aws hsms, aws kms)
3. spectrum use s3 server side encryption.
## Limit
1. Storage
   1. RA3
      1. minimum 2 node
      2. 2x64TB -> 128TB
      3. auto offloads data to S3.
   2. DC
      1. Large  
         2core + 160GB SSD
      2. 8xLarge  
         32core + 160GBx16 => 2.56TB SSD
   3. DS
      1. eXtra Large  
         2TB magnetic hdd
      2. 8eXtra Large  
         16TB magnetic hdd
2. backup
   1. retention 0 ~ 35 days  
      1(default)
   2. manual snapshot keeped when deleted cluster.
## Billing
1. compute node hours
2. backup storage
   1. 1 backup is free.
3. data transfer
   1. same region is free.
4. data scan
   1. redshift spectrum is free
   2. s3 is billed.
   3. copy command (parallel)
   4. aws import/export (snowball)
