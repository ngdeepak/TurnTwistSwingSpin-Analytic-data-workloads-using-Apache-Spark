# From RDD\(Resilient Distributed Dataset \)

## Creating a  RDD

```python
rdd_spark = spark.sparkContext.parallelize([('John', 'Seattle', 60, True, 1.7, '1960-01-01'),
 ('Tony', 'Cupertino', 30, False, 1.8, '1990-01-01'),
 ('Mike', 'New York', 40, True, 1.65, '1980-01-01')]).collect()
```

## 1. Input: Spark RDD

```python
[('John', 'Seattle', 60, True, 1.7, '1960-01-01'),
 ('Tony', 'Cupertino', 30, False, 1.8, '1990-01-01'),
 ('Mike', 'New York', 40, True, 1.65, '1980-01-01')]
```

## 2. Code: 

```python
spark.createDataFrame(rdd_spark).show()
```

## 3. Output: Spark data frame

```python
+----+---------+---+-----+----+----------+
|  _1|       _2| _3|   _4|  _5|        _6|
+----+---------+---+-----+----+----------+
|John|  Seattle| 60| true| 1.7|1960-01-01|
|Tony|Cupertino| 30|false| 1.8|1990-01-01|
|Mike| New York| 40| true|1.65|1980-01-01|
+----+---------+---+-----+----+----------+
```

