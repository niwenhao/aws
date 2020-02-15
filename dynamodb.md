# DynamoDB FAQs
## Feature
1. consistency model
   1. eventually  
      default  
      consistency within a second
   2. strongly consistent reads  
      read all data writed before.
   3. ACID transaction  
      ACID crocess one or more table iyn a account and region
2. access
   1. Get and Put with primary key.
3. schema
   1. primary key
      1. partition key
      2. partition key + sort key
   2. index
## Durablity
## Performance
## Monitor
## Backup
## Security
## Limit
1. request
   1. per table
      1. 4000 read capacity units
      2. 4000 write capacity units
   2. per account
      1. 80,000 read capacity units
      2. 80,000 write capacity units
      3. not limit when on-demand
2. index
   1. 5 local secondary indexes per table.
   2. 20 global secondary indexes per table.
## Billing
