# How to convert unix timestamp to a timestamp string ?

## 1.  Input:  Spark data frame consisting of a timestamp column in unix timestamp 

```python
df = spark.createDataFrame([(1594846364,)], ['unix_time'])
df.show()
+----------+
| unix_time|
+----------+
|1594846364|
+----------+
```

## 2.  Output Spark data frame consisting of a timestamp column 

```python
from pyspark.sql.functions import from_unixtime
df.select(from_unixtime(df.unix_time).alias("timestampstring")).show(truncate=False)
+-------------------+
|timestampstring    |
+-------------------+
|2020-07-15 16:52:44|
+-------------------+
```

{% hint style="info" %}
Syntax:  `from_unixtime`\(_timestamp_, _format='yyyy-MM-dd HH:mm:ss'_\)                             Converts the number of seconds from unix epoch \(1970-01-01 00:00:00 UTC\) to a string representing the timestamp of that moment in the current system time zone in the given format
{% endhint %}

