# How to find no of days between 2 dates?



## 1.  Input:  Spark data frame consisting of  date columns 

```python
df = spark.createDataFrame([('2020-07-15','2020-06-10')], ['date11', 'date2'])
df.show()
+----------+----------+
|     date1|     date2|
+----------+----------+
|2020-07-15|2020-06-10|
+----------+----------+
```

{% hint style="info" %}
I
{% endhint %}

## 2.  Output

```python
from pyspark.sql.functions import datediff
df.select(datediff(df.date1,df.date2).alias('diff')).show()
+----+
|diff|
+----+
|  35|
+----+
```

{% hint style="info" %}
Syntax:  `datediff`\(_end_, _start_\)                                                                                                                          Returns the number of days between start and  end date.
{% endhint %}

