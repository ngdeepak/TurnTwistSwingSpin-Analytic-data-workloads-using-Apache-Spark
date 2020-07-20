# How to create a map column from multiple array columns?



## 1.  Input:  Spark dataframe containing map column

```python
df = spark.createDataFrame([([2, 5], ['a', 'b'])], ['k', 'v'])
df.show()
+------+------+
|     k|     v|
+------+------+
|[2, 5]|[a, b]|
+------+------+
```

## 2.  Output: Spark dataframe containing an array

```python
from pyspark.sql.functions import map_entries
df = df.select(map_entries(df.data).alias("array")).show(truncate=False)
+----------------------+
|array                 |
+----------------------+
|[[a, 1], [b,], [c, 3]]|
+----------------------+
```

