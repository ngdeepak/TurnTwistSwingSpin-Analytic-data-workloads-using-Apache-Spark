# How to add no of days?

## 1.  Input:  Spark data frame consisting of a date column 

```python
df = spark.createDataFrame([('2020-07-15',)], ['date'])
df.show()
+----------+
|      date|
+----------+
|2020-07-15|
+----------+
```

## 2.  Output

```python
from pyspark.sql.functions import date_add
df.select(date_add(df.date, 1).alias('next_day')).show()
+----------+
|  next_day|
+----------+
|2020-07-16|
+----------+
```

{% hint style="info" %}
Syntax:   `date_add`\(_start_, _days_\)                                                                                                                             Returns the date that is days days after start.
{% endhint %}

