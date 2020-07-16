# How to subtract no of days?

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

{% hint style="info" %}
I
{% endhint %}

## 2.  Output

```python
from pyspark.sql.functions import date_sub
df.select(date_sub(df.date, 1).alias('yesterday')).show()
+----------+
| yesterday|
+----------+
|2020-07-14|
+----------+
```

{% hint style="info" %}
Syntax:   `date_sub`\(_start_, _days_\)                                                                                                                             Returns the date that is days days before start.
{% endhint %}

## 

