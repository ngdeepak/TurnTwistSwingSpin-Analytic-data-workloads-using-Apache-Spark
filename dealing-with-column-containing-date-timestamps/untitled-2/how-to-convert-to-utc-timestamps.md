# How to convert to UTC timestamps?

## 1.  Input:  Spark data frame consisting of a timestamp column 

```python
# Please note that local time zone is EST.
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

## 2.  Output

```python
from pyspark.sql.functions import to_utc_timestamp
df.select(to_utc_timestamp(df.timestamp,'GMT-4').alias("timestamp in UTC")).show(truncate=False)
+-----------------------+
|timestamp in UTC       |
+-----------------------+
|2020-07-15 19:00:59.089|
+-----------------------+
```

