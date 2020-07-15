# How to find the maximum of an array in a column?



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

## 2.  Code 

```python
from pyspark.sql.functions import array_max
df.select(array_max(df.data).alias("array_max")).show()
```

{% hint style="info" %}
**Syntax:**  `array_min`\(_col_\)                                                                                                                 returns the minimum value of the array                                                                                                                                                                                                                                                       
{% endhint %}

## 3. Output

```python
+---------+
|array_max|
+---------+
|        8|
|       32|
+---------+
```

