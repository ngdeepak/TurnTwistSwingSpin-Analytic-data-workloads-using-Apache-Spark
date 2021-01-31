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

{% api-method method="get" host="" path="" %}
{% api-method-summary %}

{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="" type="string" required=false %}

{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

```text
<iframe src="https://elc.github.io/blog/iframes/ode-python/foxes-rabbits-iframe.html"></iframe>
```

