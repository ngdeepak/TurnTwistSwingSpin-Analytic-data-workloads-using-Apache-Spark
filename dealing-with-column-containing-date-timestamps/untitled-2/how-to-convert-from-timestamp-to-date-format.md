# How to convert timestamp string to date format?

## 1.  Input:  Spark data frame consisting of a timestamp column 

```python
df = spark.createDataFrame([('2020-07-15 16:52:44',)], ['timestamp'])
df.show()
+-------------------+
|          timestamp|
+-------------------+
|2020-07-15 16:52:44|
+-------------------+

df.dtypes
[('timestamp', 'string')]
```

## 2.  Output Spark data frame consisting of a datetime column 

```python
from pyspark.sql.functions import to_date
df.select(to_date(df.timestamp).alias('datetime')).collect()
[Row(date=datetime.date(2020, 7, 15))]

df.dtypes
[('timestamp', 'date')]

from pyspark.sql.functions import to_date
df.select(to_date(df.timestamp, 'yyyy-MM-dd HH:mm:ss').alias('date')).collect()
[Row(date=datetime.date(2020, 7, 15))]

df.dtypes
[('timestamp', 'date')]
```

{% hint style="info" %}
Syntax:  `to_date`\(_col_, _format=None_\)                                                                                      Converts Converts a `Column` into [`pyspark.sql.types.DateType`](http://spark.apache.org/docs/latest/api/python/pyspark.sql.html?highlight=now#pyspark.sql.types.DateType) using the optionally specified format. Specify formats according to [datetime pattern](https://spark.apache.org/docs/latest/sql-ref-datetime-pattern.html).                   
{% endhint %}

