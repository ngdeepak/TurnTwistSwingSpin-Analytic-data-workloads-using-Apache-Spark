# ORC

## 1. Input

#### [https://github.com/ngdeepak/TurnTwistSwingSpin-Analytic-data-workloads-using-Apache-Spark/tree/master/resources/data/orc/sample.orc](https://github.com/ngdeepak/TurnTwistSwingSpin-Analytic-data-workloads-using-Apache-Spark/tree/master/resources/data/orc/sample.orc)

## 2. Code

```python
df = spark.read.orc("/home/deepak/Documents/jupyter/data/orc/sample.orc")
df.show()
```

## 3. Output

```python
+---+----+
|age|name|
+---+----+
| 60|John|
| 30|Tony|
| 40|Mike|
+---+----+
```

