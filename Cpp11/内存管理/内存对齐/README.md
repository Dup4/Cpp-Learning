# 内存对齐

## 三个原则

- 变量的起始地址能够被其对齐值整除，结构体变量的对齐值为最宽的成员大小。
- 结构体每个成员相对于起始地址的偏移能够被其自身对齐值整除，如果不能则在前一个成员后面补充字节。
- 结构体总体大小能够被最宽的成员的大小整除，如不能则在后面补充字节。
- 此外还有编译器的默认对齐值，一般默认对齐值为4(结构体的实际对齐值会取结构体对齐值和编译器默认对齐值中较小的那一个)。

## 为什么要对齐?

- 为了减少使用的内存
- 为了提升数据读取的效率


## Reference

[为什么要内存对齐](https://www.pengrl.com/p/20020/)