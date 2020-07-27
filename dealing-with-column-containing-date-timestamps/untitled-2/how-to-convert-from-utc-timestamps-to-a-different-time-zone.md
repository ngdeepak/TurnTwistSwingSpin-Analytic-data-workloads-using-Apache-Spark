# How to convert timestamp in UTC timezone  to a given time zone?

## 1.  Input:  Spark data frame consisting of a timestamp column in UTC time zone 

```python
# Please note that below timestamp is in UTC.
df = spark.createDataFrame([(),],)
df = df.select(current_timestamp().alias("timestamp"))
df.show(truncate=False)
+-----------------------+
|timestamp              |
+-----------------------+
|2020-07-27 17:09:17.246|
+-----------------------+
```

## 2.  Output Spark data frame consisting of a timestamp column in diff timezone

```python
from pyspark.sql.functions import from_utc_timestamp
df.select(from_utc_timestamp(df.timestamp,'UTC-4').alias("timestamp in local tz")).show(truncate=False)
+-----------------------+
|timestamp in local tz  |
+-----------------------+
|2020-07-27 13:09:19.3|
+-----------------------+
```

{% hint style="info" %}
`from_utc_timestamp`\(_timestamp_, _tz_\) 

This function takes a timestamp which is timezone-agnostic, and interprets it as a timestamp in UTC, and renders that timestamp as a timestamp in the given time zone.

Parameters

* **timestamp** – the column that contains timestamps
* **tz** – A string detailing the time zone ID that the input should be adjusted to. It should be in the format of either region-based zone IDs or zone offsets. Region IDs must have the form ‘area/city’, such as ‘America/Los\_Angeles’. Zone offsets must be in the format ‘\(+\|-\)HH:mm’, for example ‘-08:00’ or ‘+01:00’. Also ‘UTC’ and ‘Z’ are supported as aliases of ‘+00:00’. Other short names are not recommended to use because they can be ambiguous
{% endhint %}

