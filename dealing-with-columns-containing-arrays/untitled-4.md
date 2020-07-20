# How to find the minimum value of an array in a column?

![](../.gitbook/assets/2020_07_20_kleki-13-.png)

## 1.  Input:  Spark dataframe with a column having an array

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
from pyspark.sql.functions import array_min
df.select(array_min(df.data).alias("array_min")).show()
+---------+
|array_min|
+---------+
|        1|
|        4|
+---------+
```

{% hint style="info" %}
**Syntax:**   `array_min`\(_col_\)                                                                                                                returns the minimum value of the array.                                                                                                                         
{% endhint %}

