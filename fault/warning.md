# warning:表达式必须是可修改的左值

例如:  
在进行指针的运算时
```c
int *a;
*(a+1)++;
```
这种表达式是不能自加或者自减的

# 文件报错

文件的操作程序和文件同时打开之后再编辑文件会显示错误，原因是