# JSON

## What is JSON file format?

**JSON** \(JavaScript Object Notation\) is a lightweight data-interchange format. It is easy for humans to read and write. It is easy for machines to parse and generate. JSON is a text format that is completely language independent .

JSON is built on two structures:

* A collection of name/value pairs. In various languages, this is realized as an object, record, struct, dictionary, hash table, keyed list, or associative array.
* An ordered list of values. In most languages, this is realized as an array, vector, list, or sequence.

JSON example:

```javascript
{
  "firstName": "John",
  "lastName": "Smith",
  "isAlive": true,
  "age": 27,
  "address": {
    "streetAddress": "21 2nd Street",
    "city": "New York",
    "state": "NY",
    "postalCode": "10021-3100"
  },
  "phoneNumbers": [
    {
      "type": "home",
      "number": "212 555-1234"
    },
    {
      "type": "office",
      "number": "646 555-4567"
    }
  ],
  "children": [],
  "spouse": null
}
```

## When to use JSON?

JSON should be used only for loading the data from legacy systems. When dealing with HDFS, recommend to use parquet/ORC file format for storing and querying the data for efficiency and performance. 

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

## 3. Output Spark data frame

```python
+---+----+
|age|name|
+---+----+
| 60|John|
| 30|Tony|
| 40|Mike|
+---+----+
```

