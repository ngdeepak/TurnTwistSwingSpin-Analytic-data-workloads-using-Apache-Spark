# JSON

## 1. Input: JSON file

```python
{"name":"John","age":60}
{"name":"Tony", "age":30}
{"name":"Mike", "age":40}
```

## 2. Code

```python
url_json = "https://raw.githubusercontent.com/ngdeepak/TurnTwistSwingSpin-Analytic-data-workloads-using-Apache-Spark/master/resources/data/sample.json"
spark.sparkContext.addFile(url_json)
df = spark.read.json("file://"+SparkFiles.get("sample.json"))
df.show()
```

```python
df = spark.read.json("/home/deepak/Documents/jupyter/data/sample.json")
df.show()
```

## 3. Output Spar data frame

```python
+---+----+
|age|name|
+---+----+
| 60|John|
| 30|Tony|
| 40|Mike|
+---+----+
```

