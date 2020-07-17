# How to convert to uppercase?

## 1.  Input:  Spark data frame consisting of a column having a string

```python
df = spark.createDataFrame([('ABCDEFGHI',)], ['string',])
df.show()
+---------+
|   string|
+---------+
|ABCDEFGHI|
+---------+
```

{% hint style="info" %}
I
{% endhint %}

## 2.  Output

```python
from pyspark.sql.functions import lower
df.select(lower(df.string).alias('lower_string')).show()
+------------+
|lower_string|
+------------+
|   abcdefghi|
+------------+
```

{% hint style="info" %}
**Syntax:**   `upper`\(_col_\)                                                                                                                                 Converts a string expression to upper case                                                                                                       
{% endhint %}

## 

