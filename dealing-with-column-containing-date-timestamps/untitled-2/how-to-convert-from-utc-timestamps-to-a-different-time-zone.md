# How to convert from UTC timestamps to a different time zone?

## 1.  Input:  Spark data frame consisting of a timestamp column in UTC 

```python
# Please note that below timestamp is i UTC.
df = spark.createDataFrame([(),],)
df = df.select(current_timestamp().alias("timestamp"))
df.show(truncate=False)
+-----------------------+
|timestamp              |
+-----------------------+
|2020-07-15 14:59:37.557|
+-----------------------+
```

{% hint style="info" %}
Given a timestamp like '2017-07-14 02:40:00.0', interprets it as a time in the given\(local\) time zone
{% endhint %}

## 2.  Output Spark data frame consisting of a timestamp column in diff timezone

```python
from pyspark.sql.functions import from_utc_timestamp
df.select(from_utc_timestamp(df.timestamp,'EST').alias("timestamp in local tz")).show(truncate=False)
+-----------------------+
|timestamp in local tz  |
+-----------------------+
|2020-07-15 11:41:03.707|
+-----------------------+
```

