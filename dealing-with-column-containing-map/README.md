# Dealing with column containing map

## What is MapType?

Think of storing location address in a column. For eg:  1100,  spring street, New York, NY 10001                                                               One option is to store the entire address as one string like below

| **address** |
| :--- |
| `"1100,  spring street, New York, NY 10001"` |

Disadvantage of storing as string is that you can retrieve the house no, street name, city, state and zip code individually . Then how do you store ?

Answer to the above  is to use dictionary structure to store the address as below

<table>
  <thead>
    <tr>
      <th style="text-align:left">address</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">
        <p><code>{</code>
        </p>
        <p><code>&quot;house_no&quot;: 420,</code>
        </p>
        <p><code>&quot;street_name&quot;: &quot;spring street&quot;,</code>
        </p>
        <p><code>&quot;city&quot;: &quot;New York&quot;,</code>
        </p>
        <p><code>&quot;state&quot;: &quot;NY&quot;,</code>
        </p>
        <p><code>&quot;zip&quot;: 10001</code>
        </p>
        <p><code>}</code>
        </p>
      </td>
    </tr>
  </tbody>
</table>

We call this type of column as MapType.                                                                                                       A MapType object comprises three fields,                                                                                                                                      `keyType (a DataType)                                                                                                                                                              valueType (a DataType)                                                                                                                                                                                                                             valueContainsNull (a bool).`                                                                                                                                        Keys in a map data type are not allowed to be null.

