# How to convert from a given time zone to UTC timestamps?

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

{% hint style="info" %}
`to_utc_timestamp`\(_timestamp_, _tz_\)    

This function takes a timestamp which is timezone-agnostic, and interprets it as a timestamp in the given timezone, and renders that timestamp as a timestamp in UTC.

Parameters

* **timestamp** – the column that contains timestamps
* **tz** – A string detailing the time zone ID that the input should be adjusted to. It should be in the format of either region-based zone IDs or zone offsets. Region IDs must have the form ‘area/city’, such as ‘America/Los\_Angeles’. Zone offsets must be in the format ‘\(+\|-\)HH:mm’, for example ‘-08:00’ or ‘+01:00’. Also ‘UTC’ and ‘Z’ are supported as aliases of ‘+00:00’. Other short names are not recommended to use because they can be ambiguous.
{% endhint %}

