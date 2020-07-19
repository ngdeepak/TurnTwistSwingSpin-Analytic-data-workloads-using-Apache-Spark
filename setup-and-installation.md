---
description: 'Objective: To set up Apache Spark for running all the examples'
---

# Setup & Installation

## How to set up?

![](.gitbook/assets/image%20%284%29.png)

## Software requirements:

![version : 3.6 + ](https://lh3.googleusercontent.com/9WNKzJjmXVZhkBkj-H8enzJx5w4g2f4Rgax10HaMsrlNXKcZyvBL70QttHB04KEd5dzn0cXUecwhv8d8dmRBd0KPoTVWve1myOZ-TEkIEWH8SHjInyTNV5Z04qn_MC05REAhoXWCjCo)

![Operating System ](.gitbook/assets/image%20%285%29.png)



![version : 3.0.0](https://lh4.googleusercontent.com/ykSJKi4a_FSJ4_HPhXXYnKXpxT0jNN0wfwvSno4T2fdi4JkiNRS7Q4HAFhJofqGsG6c_NRm_m8AsLPmJxT5vHstxNIPWEABA0kpGGzw_9hH0XDmcCRTCa2W2VH7yOd2Wot1XFPOMyG4)

![](.gitbook/assets/jupyter.png)

Recommend to install and run spark on Linux OS. If you have Windows, install WSL \(Windows Subsystem for Linux\). Recommend to install Anaconda & Jupyter Notebook. 

## Installation:

**Assumption:** Anaconda  has been already installed & Jupyter Notebook running in a conda environment. 

#### Installing Apache Spark on Jupyter Notbook :

```text
!pip install pyspark
```

### How to create a Spark session?

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

 

 

