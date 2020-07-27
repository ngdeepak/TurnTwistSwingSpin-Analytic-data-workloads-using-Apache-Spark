# How to calculate the minimum value in a column?



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
from pyspark.sql.functions import min
df.select(min(df.data)).first()[0]
1.0
```

{% hint style="info" %}
**Syntax:**   `min`\(_col_\)

returns the minimum of the values in a group.      
{% endhint %}

## 

