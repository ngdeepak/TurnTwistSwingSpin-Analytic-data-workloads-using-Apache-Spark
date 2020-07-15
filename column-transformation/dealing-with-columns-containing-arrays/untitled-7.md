# How to find the list of elements that occurs in both  column A & column B without duplicates?



## .  Input:  Spark data frame consisting of a columns having an array

```python
df = spark.createDataFrame([([1, 2, 3, 4, 5],[6, 7, 5, 9, 10]), ([4, 5, 5, 4, 6],[6, 2, 3, 2, 4])], ['A', 'B'])
df.show()
+---------------+----------------+
|              A|               B|
+---------------+----------------+
|[1, 2, 3, 4, 5]|[6, 7, 5, 9, 10]|
|[4, 5, 5, 4, 6]| [6, 2, 3, 2, 4]|
+---------------+----------------+
```

{% hint style="info" %}
t
{% endhint %}

## 2.  Code 

```python
from pyspark.sql.functions import array_intersect
df.select(array_intersect(df.A,df.B).alias("array_intersect")).show()
```

{% hint style="info" %}
**Syntax:**   `array_intersect`\(_col1_, _col2_\) ****                                                                                                      returns an array of the elements in the intersection of col1 and col2, without duplicates                                                                                         
{% endhint %}

## 3. Output

```python
+---------------+
|array_intersect|
+---------------+
|            [5]|
|         [4, 6]|
+---------------+
```

