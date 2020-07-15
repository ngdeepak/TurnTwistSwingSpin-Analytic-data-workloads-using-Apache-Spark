# How to create a column containing array?

## 1.  Input:  Spark data frame having columns

```python
df = spark.createDataFrame([('John', 'Seattle', 60, True, 1.7, '1960-01-01'), 
('Tony', 'Cupertino', 30, False, 1.8, '1990-01-01'), 
('Mike', 'New York', 40, True, 1.65, '1980-01-01')],['name', 'city', 'age', 'smoker','height', 'birthdate'])
df.show()
+----+---------+---+------+------+----------+
|name|     city|age|smoker|height| birthdate|
+----+---------+---+------+------+----------+
|John|  Seattle| 60|  true|   1.7|1960-01-01|
|Tony|Cupertino| 30| false|   1.8|1990-01-01|
|Mike| New York| 40|  true|  1.65|1980-01-01|
+----+---------+---+------+------+----------+
```

{% hint style="info" %}
to be filled
{% endhint %}

## 2.  Code 

```python
from pyspark.sql.functions import array
df.select(array(df.age,df.height,df.city).alias("array_age_height")).show()
+--------------------+
|    array_age_height|
+--------------------+
|  [60, 1.7, Seattle]|
|[30, 1.8, Cupertino]|
|[40, 1.65, New York]|
+--------------------+
```

{% hint style="info" %}
**Syntax:   array\(\*columns\)**                                                                                                                      Creates a new array column                                                                                                                     
{% endhint %}

```

```

