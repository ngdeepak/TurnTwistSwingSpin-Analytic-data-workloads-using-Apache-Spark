# How to return an array of the elements in the union of column A and column B, without duplicates?

## 1.  Input:  Spark data frame having columns of arrays

```python
df = spark.createDataFrame([(["a", "b"], ["b", "c"],), (["a"], ["b", "c"],),(["a", None], ["b", None],) ], ['A', 'B'])
df.show()
+------+------+
|     A|     B|
+------+------+
|[a, b]|[b, c]|
|   [a]|[b, c]|
|  [a,]|  [b,]|
+------+------+
```

## 2. Output

```python
from pyspark.sql.functions import arrays_overlap
df.select(arrays_overlap(df.A, df.B).alias("overlap")).show()
+-------+
|overlap|
+-------+
|   true|
|  false|
|   null|
+-------+
```

{% hint style="info" %}
**Syntax:**   `arrayS_overlap`\(_col1_, _col2_\)                ****                                                                                                      returns true if the arrays contain any common non-null element; if not, returns null if both the arrays are non-empty and any of them contains a null element; returns false otherwise.

* **col1** – name of column containing array
* **col2** – name of column containing array                  
{% endhint %}

