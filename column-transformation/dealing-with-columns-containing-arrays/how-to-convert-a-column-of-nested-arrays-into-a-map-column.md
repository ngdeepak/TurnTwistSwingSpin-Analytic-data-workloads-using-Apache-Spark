# How to convert a column of nested arrays into a map column?

## 1.  Input:  Spark data frame consisting of a column having a nested  array

```python
df = spark.sql("SELECT array(struct(1, 'a'), struct(2, 'b')) as data")
df.show()
+----------------+
|            data|
+----------------+
|[[1, a], [2, b]]|
+----------------+
```

{% hint style="info" %}
I
{% endhint %}

## 2.  Output

```python
from pyspark.sql.functions import map_entries
df.select(map_from_entries("data").alias("map")).show()
+----------------+
|             map|
+----------------+
|[1 -> a, 2 -> b]|
+----------------+
```

{% hint style="info" %}
Syntax: `map_from_entries`\(_col_\)                                                                                                   Returns a map created from the given array of entries
{% endhint %}

