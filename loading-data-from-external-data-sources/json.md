# JSON

## 1. Input: JSON file

```text
{"name":"John","age":60}
{"name":"Tony", "age":30}
{"name":"Mike", "age":40}
```

## 2. Code

```text
url_json = "https://raw.githubusercontent.com/ngdeepak/TurnTwistSwingSpin-Analytic-data-workloads-using-Apache-Spark/master/resources/data/sample.json"
spark.sparkContext.addFile(url_json)
df = spark.read.json("file://"+SparkFiles.get("sample.json"))
df.show()
```

```text
df = spark.read.json("/home/deepak/Documents/jupyter/data/sample.json")
df.show()
```

## 3. Output Spar data frame

```text
+---+----+
|age|name|
+---+----+
| 60|John|
| 30|Tony|
| 40|Mike|
+---+----+
```

