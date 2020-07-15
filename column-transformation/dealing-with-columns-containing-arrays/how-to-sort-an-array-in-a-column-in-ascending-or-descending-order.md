# How to sort an array in a column in ascending or descending order?

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
from pyspark.sql.functions import sort_array
df.select(sort_array(df.data, asc=True).alias('asc')).show()
+-----------------+
|              asc|
+-----------------+
|  [1, 2, 3, 4, 8]|
|[4, 5, 6, 32, 32]|
+-----------------+

from pyspark.sql.functions import sort_array
df.select(sort_array(df.data, asc=False).alias('asc')).show()
+-----------------+
|              asc|
+-----------------+
|  [8, 4, 3, 2, 1]|
|[32, 32, 6, 5, 4]|
+-----------------+
```

{% hint style="info" %}
**Syntax:**   `sort_array`\(_col_, _asc=True\)_                                                                                                                 sorts the input array in ascending or descending order according to the natural ordering of the array elements. Null elements will be placed at the beginning of the returned array in ascending order or at the end of the returned array in descending order. 
{% endhint %}

