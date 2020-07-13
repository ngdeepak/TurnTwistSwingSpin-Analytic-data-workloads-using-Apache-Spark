# Setup & Installation

## Setup:

Recommend to install and run spark on Linux OS. If you have Windows, install WSL \(Windows Subsystem for Linux\). Recommend to install Anaconda & Jupyter Notebook. 

## Installation:

**Assumption:** Anaconda  has been already installed & Jupyter Notebook running in a conda environment. 

#### Installing Apache Spark on Jupyter Notbook :

```text
!pip install pyspark
```

### How to create Spark session?

```python
import pyspark
from pyspark.sql import SparkSession
spark = SparkSession \
    .builder \
    .appName("Python Spark SQL basic example") \
    .config("spark.some.config.option", "some-value") \
    .getOrCreate()
spark
```

You should see the following output to make sure spark installation is correct and spark session is working

```python
SparkSession - in-memory
SparkContext

Spark UI
Version
v3.0.0
Master
local[*]
AppName
Python Spark SQL basic example
```

 

 

