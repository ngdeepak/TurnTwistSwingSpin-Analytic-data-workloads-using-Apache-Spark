# How to split a string?



## 1.  Input:  Spark data frame consisting of a column having a string

```python
df = spark.createDataFrame([('abc__def__ghc',)], ['string',])
df.show()
+-------------+
|       string|
+-------------+
|abc__def__ghc|
+-------------+
```

{% hint style="info" %}
I
{% endhint %}

## 2.  Output

```python
from pyspark.sql.functions import split
df.select(split(df.string,'__').alias('split_string')).show()
+---------------+
|   split_string|
+---------------+
|[abc, def, ghc]|
+---------------+
```

{% hint style="info" %}
**Syntax:**   `split`\(_str_, _pattern_, _limit=-1_\)                                                                                                                 

* **str** – a string expression to split
* **pattern** – a string representing a regular expression. The regex string should be a Java regular expression.
* **limit** –

  an integer which controls the number of times pattern is applied.

  * `limit > 0`: The resulting array’s length will not be more than limit, and the

    resulting array’s last entry will contain all input beyond the last matched pattern.

  * `limit <= 0`: pattern will be applied as many times as possible, and the resulting

    array can be of any size.            
{% endhint %}

