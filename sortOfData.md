# 字符串类型

字符串类型，也叫字符数组。

字符串常量
`"1234"`
双引号做了三件事：

1. 申请了空间（在字符串常量区），存放了字符串
2. 在字符串尾加上了`'\0'`
3. 返回字符串首个字符的地址

PS.易错点:
1. 注意给字符串申请空间的时候注意要包括字符串结尾的`'\0'`
2. 如果想把一个字符串常量赋值给一个字符数组，一定要设立字符指针之后分配空间；  
注意这里不能直接赋值给一个字符数组（`char a[10]="123"`），因为字符串常量会返回首个字符的地址，而字符数组实际上是一个指针常量

相当于声明：
`c
char * const a;
`
指向的是变量，自身是常量

