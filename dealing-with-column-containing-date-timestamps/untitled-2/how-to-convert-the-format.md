# How to convert the format?

## 1.  Input:  Spark data frame consisting of a timestamp column 

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
G
{% endhint %}

## 2.  Output Spark data frame consisting of a datetime column 

```python
from pyspark.sql.functions import date_format
df.select(date_format('date', 'MM/dd/yyy').alias('date')).show()
+----------+
|      date|
+----------+
|07/15/2020|
+----------+
```

> Syntax :  `date_format`\(_date_, _format_\)                                                                                                             Converts a date/timestamp/string to a value of string in the format specified by the date format given by the second argument.

