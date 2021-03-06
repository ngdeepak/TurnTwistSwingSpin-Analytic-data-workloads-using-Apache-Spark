# Creating a Data Frame

## What is a Spark Data frame?

**Spark Data Frame** is a distributed collection of data organized into named columns. It can be constructed from a wide array of sources such as: structured data files, tables in Hive, external databases, or existing RDD, Lists, Pandas data frame.  

![](../.gitbook/assets/sparktable%20%283%29.png)

**What is distributed data?**  

To answer this question, let us first understand what a normal data \(non-distributed\) look like. Lets us assume that a table consisting of just 3 records is stored using mySQL RDBMS in Linux. 

![Non-Distributed data](../.gitbook/assets/2020_07_27_kleki.png)

   Having understood on how normal data is stored, let us look at how the same data is stored in a distributed data environment. Please note that distributed File System is required to store the data in distributed manner. 

Lets take a moment to understand what a distributed File System is.

![Distributed File System](../.gitbook/assets/2020_07_27_kleki-2-.png)

     

Below is an example of how data is distributed across 3 nodes. In this example, table consisting of 2 columns\(Name & Age\) and 3 rows are stored across 3 worker nodes .  Each node stores one record.

In spark, data operations are mostly carried out directly on a node where data resides instead of getting the data from other nodes.        

                                                                                                  

## Overview of how data is stored on a spark cluster

![](../.gitbook/assets/2020_07_27_kleki-3-.png)

## How to create a spark dataframe?

{% hint style="info" %}
Syntax:     `createDataFrame`\(_data_, _schema=None_, _samplingRatio=None_, _verifySchema=True_\)                                                                                                                                               Creates a [`DataFrame`](http://spark.apache.org/docs/latest/api/python/pyspark.sql.html?highlight=createdata#pyspark.sql.DataFrame) from an `RDD`, a list or a `pandas.DataFrame`.                                          When `schema` is a list of column names, the type of each column will be inferred from `data.`When `schema` is `None`, it will try to infer the schema \(column names and types\) from `data`, which should be an RDD of either [`Row`](http://spark.apache.org/docs/latest/api/python/pyspark.sql.html?highlight=createdata#pyspark.sql.Row), `namedtuple`, or `dict`.                                               When `schema` is [`pyspark.sql.types.DataType`](http://spark.apache.org/docs/latest/api/python/pyspark.sql.html?highlight=createdata#pyspark.sql.types.DataType) or a datatype string, it must match the real data, or an exception will be thrown at runtime.                                                                                                            If the given schema is not [`pyspark.sql.types.StructType`](http://spark.apache.org/docs/latest/api/python/pyspark.sql.html?highlight=createdata#pyspark.sql.types.StructType), it will be wrapped into a [`pyspark.sql.types.StructType`](http://spark.apache.org/docs/latest/api/python/pyspark.sql.html?highlight=createdata#pyspark.sql.types.StructType) as its only field, and the field name will be “value”. Each record will also be wrapped into a tuple, which can be converted to row later.
{% endhint %}

{% page-ref page="from-a-pandas-data-frame.md" %}

{% page-ref page="from-a-list.md" %}

{% page-ref page="from-rdd-resilient-distributed-dataset.md" %}



