_Notes on an end-to-end workflow in AWS_

___

## AWS Applications
Access everything through the AWS Management Console. 

### Sagemaker 
Jupyter notebooks (blank or pre-built). 

### S3 (Simple Storage Service)
An Amazon S3 bucket is a container you store files in. You create bucket with a specified region. 
It's like Dropbox or Google Drive.

- Parquet is a 'columnar storage file format' and can be used in the Hadoop ecosystem (e.g. Hive, Impala, Pig, Spark) across any language, model etc. 
- it is an open source file format
- what does it mean to be column-oriented? it allows for more efficient processing and storage of big data since only the needed columns are read
- hence, this is preferred over CSV files

### EMR (Elastic MapReduce)
It's Hadoop runing on AWS. It uses EC2 for computing power and S3 for storage (retrieving data and writing results). It can be used on demand. An EMR cluster comes with one master instance and multiple slave instances (core or task nodes). 

- Apache Spark is often installed for data wrangling and EDA. It is a good choice for training ML models as it can store large amounts of data in memory and quickly run queries. It's much faster than Hadoop's MapReduce. PySpark is the Python API for Spark (written in Scala). 

### EC2 (Elastic Compute Cloud) Instance
It is a virtual server for running applications within EMR. You can increase/decrease capacity very quickly. 

### Glue
Glue has two uses:

1. It catalogs the metadata in one central repo for the data sources you own. Glue retrieves metadata about data files (e.g. a parquet). It 'crawls' for data in AWS and stores it in a catalog according to the specified schema, format or data types in the data. This catalog becomes a directory of data. A catalog is like a database: you can index, search and query it. This is stored as tables in the AWS Glue Data Catalog.

2. It is an ETL service (extract, transform, load). The purpose is to move data from different sources into a common data warehouse, or change it, or combine them together. 

Glue is serverless (always available, does not need an EC2 instance). [Example](https://docs.aws.amazon.com/glue/latest/dg/aws-glue-programming-python-samples-legislators.html)

You can also connect a SageMaker notebook to a Glue development endpoint directly. A development endpoint is a Spark environment to use the Glue ETL scripts. [More here](https://aws.amazon.com/about-aws/whats-new/2018/10/aws-glue-now-supports-connecting-amazon-sagemaker-notebooks-to-development-endpoints/)

## Tentative Workflow
In this particular project the workflow is straightforward. 
0. We have a master instance that assigns and monitors the cluster. It creates new instances if any fail. It divides the workload among the core/task nodes.  
1. Our raw (input) data is stored in an S3 bucket that also contains a Python script for the process.
2. We run our data wrangling and machine learning processes on the raw data across instance(s) 
4. The results are then written to another S3 bucket for storage
5. Terminate the cluster

## Links
[AWS Data Wrangler](https://buildmedia.readthedocs.org/media/pdf/aws-data-wrangler/latest/aws-data-wrangler.pdf)

[Parquet, Spark & S3](https://arnon.me/2015/08/spark-parquet-s3/)

[Spark & EMR in a real world application](https://confusedcoders.com/data-engineering/real-world-application-project-for-big-data-with-apache-spark-and-aws-emr)

[Optimus to do ML using PySpark](https://github.com/ironmussa/Optimus)

[SageMaker Spark](https://github.com/aws/sagemaker-spark/blob/master/README.md)

[Use Apache Spark with Amazon SageMaker](https://docs.aws.amazon.com/sagemaker/latest/dg/apache-spark.html)






