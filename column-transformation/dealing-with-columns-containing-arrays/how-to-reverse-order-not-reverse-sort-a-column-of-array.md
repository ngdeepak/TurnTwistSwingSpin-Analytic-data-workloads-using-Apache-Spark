# How to reverse order\(not reverse sort\) a column of array ?



## 1.  Input:  Spark data frame consisting of a column having an array

```python
df = spark.createDataFrame([([1, 2, 3, 8, 4],), ([4, 5, 32, 32, 6],)], ['data'])
df.show()
+-----------------+
|             data|
+-----------------+
|  [1, 2, 3, 8, 4]|
|[4, 5, 32, 32, 6]|
+-----------------+
```

{% hint style="info" %}
I
{% endhint %}

## 2.  Output

```python
from pyspark.sql.functions import reverse
df.select(reverse(df.data).alias('reversesort')).show(truncate=False)
+-----------------+
|reversesort      |
+-----------------+
|[4, 8, 3, 2, 1]  |
|[6, 32, 32, 5, 4]|
+-----------------+
```

{% hint style="info" %}
**Syntax:**   `reverse`\(_col_\)                                                                                                                 returns returns a reversed string or an array with reverse order of elements                 
{% endhint %}

