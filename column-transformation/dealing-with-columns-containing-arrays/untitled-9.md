# How to zip 2 array columns ?



## 1.  Input:  Spark data frame having columns of arrays

```python
df = spark.createDataFrame([(([1, 2, 3], [4, 5, 6]))], ['A', 'B'])
df.show()
+---------+---------+
|        A|        B|
+---------+---------+
|[1, 2, 3]|[4, 5, 6]|
+---------+---------+
```

{% hint style="info" %}
to be filled
{% endhint %}

## 2. Output

```python
from pyspark.sql.functions import arrays_zip
df.select(arrays_zip(df.A, df.B).alias('zipped')).show(truncate=False)
+------------------------+
|zipped                  |
+------------------------+
|[[1, 4], [2, 5], [3, 6]]|
+------------------------+
```

{% hint style="info" %}
**Syntax:**   `arrays_zip`\(_\*cols_\)                ****                                                                                                      Returns a merged array.

* **cols** – columns of arrays to be merged.    
{% endhint %}

