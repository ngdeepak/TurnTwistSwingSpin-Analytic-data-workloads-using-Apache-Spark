# Creating a column with date or timestamp



## 1.  Output

```python
from pyspark.sql.functions import current_date
df = spark.createDataFrame([(),],)
df.select(current_date().alias("curent_day")).show()
+----------+
|curent_day|
+----------+
|2020-07-15|
+----------+

from pyspark.sql.functions import current_timestamp
df = spark.createDataFrame([(),],)
df.select(current_timestamp().alias("curent_day")).show(truncate=False)
+----------------------+
|curent_day            |
+----------------------+
|2020-07-15 13:58:18.74|
+----------------------+
```

