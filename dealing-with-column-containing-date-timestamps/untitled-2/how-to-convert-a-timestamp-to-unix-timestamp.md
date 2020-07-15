# How to convert a timestamp to unix timestamp?

## 1.  Input:  Spark data frame consisting of a timestamp column in UTC 

```python
#timezone 'EST'
df = spark.createDataFrame([(),],)
df = df.select(current_timestamp().alias("timestamp"))
df.show(truncate=False)
+-----------------------+
|timestamp              |
+-----------------------+
|2020-07-15 16:51:21.309|
+-----------------------+
```

{% hint style="info" %}
Given a timestamp like '2017-07-14 02:40:00.0', interprets it as a time in the given\(local\) time zone
{% endhint %}

## 2.  Output Spark data frame consisting of a timestamp column in diff timezone

```python
from pyspark.sql.functions import unix_timestamp
df.select(unix_timestamp(df.timestamp).alias("unixtimestamp")).show(truncate=False)
+-------------+
|unixtimestamp|
+-------------+
|1594846364   |
+-------------+
```

{% hint style="info" %}
Syntax:  `unix_timestamp`\(_timestamp=None_, _format='yyyy-MM-dd HH:mm:ss'_\)                Convert time string with given pattern \(‘yyyy-MM-dd HH:mm:ss’, by default\) to Unix time stamp \(in seconds\), using the default timezone and the default locale, return null if fail
{% endhint %}

