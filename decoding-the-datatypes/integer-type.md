# IntegerType

It is a variable to hold a integer \(number without decimals\). This is a 32 bit signed integer.

If you need to store 64 bit integer , please use LongType. In case, you need to store a smaller integer ,  use ShortType \(16 bit integer\). If you still need to store a smaller number, use BinaryType \(8 bit integer\).

When to Use What data types:

| **Data Type** | No of Bytes | **Number Range** |
| :--- | :--- | :--- |
| BinaryType | 1 | -128 to +127 |
| ShortType | 2 | -32768 to + 32767 |
| IntegerType | 4 | -2147483648 to +2147483647 |
| LongType | 8 | -9223372036854775808 to + 9223372036854775807 |
| DecimalType |  | no of digits before the dot is 38 and no of digits after the dot is 18 |



