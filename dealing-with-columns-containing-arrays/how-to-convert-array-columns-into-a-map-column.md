# How to combine two array columns into a map column?

map\_from\_array





## 1.  Input:  Spark dataframe with a column having 2 array columns

```python
df = spark.createDataFrame([([1, 2, 3, 4, 5],[6, 7, 8, 9, 10]), ([4, 5, 6, 7, 8],[6, 2, 3, 9, 4])], ['A','B'])
df.show()
+---------------+----------------+
|              A|               B|
+---------------+----------------+
|[1, 2, 3, 4, 5]|[6, 7, 8, 9, 10]|
|[4, 5, 6, 7, 8]| [6, 2, 3, 9, 4]|
+---------------+----------------+
```

## 2.  Output

```python
from pyspark.sql.functions import map_from_arrays
df.select(map_from_arrays(df.A, df.B).alias('map')).show(truncate=False)
+-----------------------------------------+
|map                                      |
+-----------------------------------------+
|[1 -> 6, 2 -> 7, 3 -> 8, 4 -> 9, 5 -> 10]|
|[4 -> 6, 5 -> 2, 6 -> 3, 7 -> 9, 8 -> 4] |
+-----------------------------------------+
```

{% hint style="info" %}
Syntax: `map_from_arrays`\(_col1_, _col2_\)                                                                                                  

Creates a new map from two arrays.Parameters

* **col1** – name of column containing a set of keys. All elements should not be null
* **col2** – name of column containing a set of values
{% endhint %}

