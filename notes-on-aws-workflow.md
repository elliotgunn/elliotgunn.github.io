Access everything through the AWS Management Console. 


### S3 (Simple Storage Service)
An Amazon S3 bucket is a container you store files in. You create bucket with a specified region. 
It's like Dropbox or Google Drive.

- Parquet is a 'columnar storage file format' and can be used in the Hadoop ecosystem (e.g. Hive, Impala, Pig, Spark) across any language, model etc. 
- it is an open source file format
- what does it mean to be column-oriented? it allows for more efficient processing and storage of big data since only the needed columns are read
- hence, this is preferred over CSV files

### EC2 (Elastic Compute Cloud) Instance
It is a virtual server for running applications in AWS. You can increase/decrease capacity very quickly. 

### EMR (Elastic MapReduce)
It's Hadoop runing on AWS. It uses EC2 for computing power and S3 for storage (retrieving data and writing results). 

Master/slave

### Glue


## Workflow
In this particular project the workflow is straightforward. 
0. We have a master instance that assigns and monitors the cluster. It creates new instances if any fail. It divides the workload among the core/task nodes.  
1. Our raw (input) data is stored in an S3 bucket that also contains a Python script for the process.
2. We run our data wrangling and machine learning processes on the raw data across instance(s) 
4. The results are then written to another S3 bucket for storage





