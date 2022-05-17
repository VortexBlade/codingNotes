# 快速编程的小方法

1. 快速创建已知字符串:
```c
#include <stdio.h>
#include <stdlib.h>
int main(){
    char * a="abcde";
    puts(a);
    return 0;
}
```
PS.这样创建的其实不是字符串，因为该指针没有分配空间，所以这样创建的"假"字符串是不能修改内容的，只能进行puts打印和只涉及字符串指针的函数调用(比如strcmp)

2. 快速复制字符串
```c
#include <stdio.h>
#include <stdlib.h>
int main(){
    char a[]="abcde",b[10];
    char *src=a,*des=b;
    while(*des++=*src++);
    puts(b);
    return 0;
}
```
PS.注意while后面一定要有分号
