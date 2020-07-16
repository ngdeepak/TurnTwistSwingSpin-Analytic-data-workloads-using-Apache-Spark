# How to add no of months to a date?



## 1.  Input:  Spark data frame consisting of a map column 

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
from pyspark.sql.functions import add_months
df.select(add_months(df.date, 1).alias('next_month')).show()
+----------+
|next_month|
+----------+
|2020-05-08|
+----------+
```

{% hint style="info" %}
Syntax:  `add_months`\(_start_, _months_\)                                                                                                                             Returns the date that is months months after start.
{% endhint %}

