# How to convert to uppercase?



## 1.  Input:  Spark data frame consisting of a column having a string

```python
df = spark.createDataFrame([('abcdefghc',)], ['string',])
df.show()
+---------+
|   string|
+---------+
|abcdefghc|
+---------+
```

{% hint style="info" %}
I
{% endhint %}

## 2.  Output

```python
from pyspark.sql.functions import upper
df.select(upper(df.string).alias('upper_string')).show()
+------------+
|upper_string|
+------------+
|   ABCDEFGHC|
+------------+
```

{% hint style="info" %}
**Syntax:**   `upper`\(_col_\)                                                                                                                                 Converts a string expression to upper case                                                                                                       
{% endhint %}

