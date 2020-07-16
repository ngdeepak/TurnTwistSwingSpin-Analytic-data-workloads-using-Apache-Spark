# How to convert from timestamp to datetime format?

## 1.  Input:  Spark data frame consisting of a timestamp column 

```python
df = spark.createDataFrame([('2020-07-15 16:52:44',)], ['timestamp'])
df.show()
+-------------------+
|          timestamp|
+-------------------+
|2020-07-15 16:52:44|
+-------------------+
```

{% hint style="info" %}
G
{% endhint %}

## 2.  Output Spark data frame consisting of a datetime column 

```python
from pyspark.sql.functions import to_timestamp
df.select(to_timestamp(df.timestamp).alias('datetime')).collect()
[Row(datetime=datetime.datetime(2020, 7, 15, 16, 52, 44))]

from pyspark.sql.functions import to_timestamp
df.select(to_timestamp(df.timestamp, 'yyyy-MM-dd HH:mm:ss').alias('dt')).collect()
[Row(datetime=datetime.datetime(2020, 7, 15, 16, 52, 44))]
```

{% hint style="info" %}
Syntax:  `to_timestamp`\(_col_, _format=None_\)                                                                                      Converts a `Column` into [`pyspark.sql.types.TimestampType`](http://spark.apache.org/docs/latest/api/python/pyspark.sql.html?highlight=now#pyspark.sql.types.TimestampType) using the optionally specified format. Specify formats according to [datetime pattern](https://spark.apache.org/docs/latest/sql-ref-datetime-pattern.html).                    
{% endhint %}

