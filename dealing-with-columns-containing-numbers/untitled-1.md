# How to calculate the maximum value in a column?



## 

## 1.  Input:  Spark data frame with a column having numbers

```python
df = spark.createDataFrame([(1,),(2,),(3,)],['data'])
df.show()
+----+
|data|
+----+
|   1|
|   2|
|   3|
+----+
```

## 2.  Output

```python
from pyspark.sql.functions import max
df.select(max(df.data)).first()[0]
1.0
```

{% hint style="info" %}
**Syntax:**   `max`\(_col_\)

returns the maximum of the values in a group.      
{% endhint %}

