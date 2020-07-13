# CSV

## 1 . Input

| Name | Age |
| :--- | :--- |
| John | 60 |
| Tony | 30 |
| Mike | 40 |

{% file src="../.gitbook/assets/simplecsv.csv" caption="Sample CSV file" %}

## 2. Code

```python
from pyspark import SparkFiles
url='https://raw.githubusercontent.com/ngdeepak/TurnTwistSwingSpin-Analytic-data-workloads-using-Apache-Spark/master/resources/data/simplecsv.csv'
spark.sparkContext.addFile(url)
df = spark.read.csv("file://"+SparkFiles.get("simplecsv.csv"), header=True, inferSchema= True)
df.show()
```

```python
df = spark.read.csv("/home/deepak/Documents/jupyter/data/simplecsv.csv", header=True, inferSchema= True)
df.show()
```

## 3. Output: Spark data frame

```python
+----+---+
|Name|Age|
+----+---+
|John| 60|
|Tony| 30|
|Mike| 40|
+----+---+
```

