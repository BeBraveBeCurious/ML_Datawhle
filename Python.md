
## is或者is not的比较
【例子】比较的两个变量均指向不可变类型。
```
a = "hello"

b = "hello"

print(a is b, a == b)  # True True

print(a is not b, a != b)  # False False
```

True True
False False


【例子】比较的两个变量均指向可变类型。
```
a = ["hello"]

b = ["hello"]

print(a is b, a == b)  # False True

print(a is not b, a != b)  # True False
```

False True
True False

注意：

- is, is not 对比的是两个变量的内存地址
- ==, != 对比的是两个变量的值
- 比较的两个变量，指向的都是地址不可变的类型（str等），那么is，is not 和 ==，！= 是完全等价的。
- 对比的两个变量，指向的是地址可变的类型（list，dict，tuple等），则两者是有区别的。


## 运算符的优先级

一元运算符优于二元运算符。例如3 ** -2等价于3 ** (-2)。

先算术运算，后移位运算，最后位运算。例如 1 << 3 + 2 & 7等价于 1 << (3 + 2)) & 7。

逻辑运算最后结合。例如3 < 4 and 4 < 5等价于(3 < 4) and (4 < 5)。

