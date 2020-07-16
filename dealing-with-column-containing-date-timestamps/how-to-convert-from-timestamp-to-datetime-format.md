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
Syntax:  `from_unixtime`\(_timestamp_, _format='yyyy-MM-dd HH:mm:ss'_\)                             Converts the number of seconds from unix epoch \(1970-01-01 00:00:00 UTC\) to a string representing the timestamp of that moment in the current system time zone in the given 
{% endhint %}

