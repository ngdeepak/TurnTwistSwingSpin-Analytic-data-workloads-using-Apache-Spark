# How to extract year, month, date, hour, minute, second, day, weekday, week/quarter of year?



## 1.  Input:  Spark data frame consisting of a date/timestamp column 

```python
df = spark.createDataFrame([(),],)
df.select(current_timestamp().alias("curent_timestamp")).show(truncate=False)
+-----------------------+
|curent_timestamp       |
+-----------------------+
|2020-07-15 14:17:28.171|
+-----------------------+
```

{% hint style="info" %}
I
{% endhint %}

## 2.  Output

```python
from pyspark.sql.functions import year, month, dayofmonth, dayofweek, dayofyear, 
hour, minute, second, weekofyear, quarter
df = spark.createDataFrame([(),],)
df.select(df.timestamp,year(df.timestamp).alias("year"), 
month(df.timestamp).alias("month"), dayofmonth(df.timestamp).alias("dayofmonth"), 
dayofweek(df.timestamp).alias("dayofweek"), dayofyear(df.timestamp).alias("dayofyear"), 
hour(df.timestamp).alias("hour"), minute(df.timestamp).alias("minute"), 
second(df.timestamp).alias("second"), weekofyear(df.timestamp).alias("weekofyear"), 
quarter(df.timestamp).alias("quarter")).show(truncate=False)
+-----------------------+----+-----+----------+---------+---------+----+------+------+----------+-------+
|timestamp              |year|month|dayofmonth|dayofweek|dayofyear|hour|minute|second|weekofyear|quarter|
+-----------------------+----+-----+----------+---------+---------+----+------+------+----------+-------+
|2020-07-15 14:30:53.052|2020|7    |15        |4        |197      |14  |30    |53    |29        |3      |
+-----------------------+----+-----+----------+---------+---------+----+------+------+----------+-------+
+-------+
```

