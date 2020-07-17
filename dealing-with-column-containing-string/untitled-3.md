# How to slice  string?

## 1.  Input:  Spark data frame consisting of a column having a string

```python
df = spark.createDataFrame([('abcdefghi',)], ['string',])
df.show()
+---------+
|   string|
+---------+
|abcdefghi|
+---------+
```

{% hint style="info" %}
I
{% endhint %}

## 2.  Output

```python
from pyspark.sql.functions import substring
df.select(substring(df.string,1,4).alias('substring')).show()
+---------+
|substring|
+---------+
|     abcd|
+---------+
```

{% hint style="info" %}
**Syntax:**    `substring`\(_str_, _pos_, _len_\)                                                                                                                 Substring starts at pos and is of length len when str is String type or returns the slice of byte array that starts at pos in byte and is of length len when str is Binary type.             
{% endhint %}

