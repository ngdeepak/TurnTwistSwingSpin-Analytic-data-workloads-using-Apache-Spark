# What is schema?

A **schema** is the description of the structure of your data. It defines the names of all the fields, its data type & whether it can contain a null.

Let us create a spark data frame and look at the schema. 

```text
df = spark.createDataFrame([(1,2),(5,6)],["col1","col2"])
df.show()
+----+----+
|col1|col2|
+----+----+
|   1|   2|
|   5|   6|
+----+----+
```

How to display the schema?

Option\#1:

```text
df.schema
```

{% embed url="https://hub.gke2.mybinder.org/user/ngdeepak-sparkbook-j1irc647/notebooks/sparkbook-2.ipynb" %}



