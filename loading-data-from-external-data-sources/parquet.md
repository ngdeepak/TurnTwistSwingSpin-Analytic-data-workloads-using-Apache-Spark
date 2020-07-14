# Parquet

## 1. Input

#### [https://github.com/ngdeepak/TurnTwistSwingSpin-Analytic-data-workloads-using-Apache-Spark/tree/master/resources/data/parquet/sample.parquet](https://github.com/ngdeepak/TurnTwistSwingSpin-Analytic-data-workloads-using-Apache-Spark/tree/master/resources/data/parquet/sample.parquet)

## 2. Code

```text
df = spark.read.parquet("/home/deepak/Documents/jupyter/data/parquet/sample.parquet")
df.show()
```

## 3. Output

```text
+---+----+
|age|name|
+---+----+
| 60|John|
| 30|Tony|
| 40|Mike|
+---+----+
```

