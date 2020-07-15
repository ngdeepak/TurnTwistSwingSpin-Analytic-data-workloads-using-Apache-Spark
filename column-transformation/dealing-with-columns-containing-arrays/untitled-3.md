# How to locate the position of first occurrence of the given value in the given array in a column?

## 1..  Input:  Spark data frame consisting of a column having an array

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
In 
{% endhint %}

## 2.  Output

```python
from pyspark.sql.functions import array_position
df.select(array_position(df.data, 4).alias("array_poition")).show()
+-------------+
|array_poition|
+-------------+
|            5|
|            1|
+-------------+
```

{% hint style="info" %}
**Syntax:**   `array_position`\(_col_, _value_\)  ****                                                                                                      Locates the position of the first occurrence of the given value in the given array                                                                              Note: The position is not zero based, but 1 based index. Returns 0 if the given value could not be found in the array.                                                                                                                       
{% endhint %}

