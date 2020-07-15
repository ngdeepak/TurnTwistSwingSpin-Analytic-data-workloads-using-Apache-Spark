# How to create an array from a  column value  repeated  many times times?



## 1.  Input:  Spark data frame consisting of a column having a value

```python
df = spark.createDataFrame([(5,)], ['data'])
df.show()
+----+
|data|
+----+
|   5|
+----+
```

{% hint style="info" %}
In 
{% endhint %}

## 2.  Output

```python
from pyspark.sql.functions import array_repeat
df.select(array_repeat(df.data, 3).alias('repeat')).show()
+---------+
|   repeat|
+---------+
|[5, 5, 5]|
+---------+
```

{% hint style="info" %}
**Syntax:**  `array_repeat`\(_col_, _count_\)[\[source\]](http://spark.apache.org/docs/latest/api/python/_modules/pyspark/sql/functions.html#array_repeat)[  
](http://spark.apache.org/docs/latest/api/python/pyspark.sql.html?highlight=array#pyspark.sql.functions.array_repeat)creates an array containing a column repeated count times  ****                                                                                                                                                                                                                                      
{% endhint %}

