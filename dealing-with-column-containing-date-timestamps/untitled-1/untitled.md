# How to find no of months between 2 dates?

## 1.  Input:  Spark data frame consisting of a map column 

```python
df = spark.createDataFrame([('2020-07-15 11:32:00', '2020-01-30')], ['date1', 'date2'])
df.show()
+-------------------+----------+
|              date1|     date2|
+-------------------+----------+
|2020-07-15 11:32:00|2020-01-30|
+-------------------+----------+
```

{% hint style="info" %}
I
{% endhint %}

## 2.  Output

```python
from pyspark.sql.functions import months_between
df.select(months_between(df.date1, df.date2)).show()
+----------------------------------+
|months_between(date1, date2, true)|
+----------------------------------+
|                        5.53163082|
+----------------------------------+
```

{% hint style="info" %}
Syntax:  `months_between`\(_date1_, _date2_, _roundOff=True_\)                                                                                                                             Returns number of months between dates date1 and date2. If date1 is later than date2, then the result is positive. If date1 and date2 are on the same day of month, or both are the last day of month, returns an integer \(time of day will be ignored\). The result is rounded off to 8 digits unless roundOff is set to False.
{% endhint %}

