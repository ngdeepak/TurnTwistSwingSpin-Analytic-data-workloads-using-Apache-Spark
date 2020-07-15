# How to extract the values from a map column?

## 1.  Input:  Spark data frame consisting of a map column 

```python
df = spark.createDataFrame([({"a":1,"b":"2","c":3},)],["data"])
df.show(truncate=False)
+----------------------+
|data                  |
+----------------------+
|[a -> 1, b ->, c -> 3]|
+----------------------+
```

{% hint style="info" %}
I
{% endhint %}

## 2.  Output

```python
from pyspark.sql.functions import map_values
df.select(map_values(df.data).alias("values")).show()
+-------+
| values|
+-------+
|[1,, 3]|
+-------+
```

{% hint style="info" %}
Syntax:  `map_values`\(_col_\)                                                                                                                             Returns an unordered array containing the values of the map.
{% endhint %}

