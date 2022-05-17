# include <string.h>

头文件:string.h

部分函数(我觉得可以用的)

1. strcpy(string copy)

    声明:
    ```c
    char * strcpy (char * destin , char * source);
    ```

    功能:拷贝一个字符串到另一个(包括'\0')

2. strncpy

    声明:
    ```c
    char * strncpy (char * dest , char * src , size_t n);
    ```

    功能：将字符串src中最多n个字符复制到字符数组dest中(它并不像strcpy一样遇到NULL才停止复制，而是等凑够n个字符才停止复制），返回指向  dest的指针。

3. strcat(string catenate)

    声明:
    ```c
    extern char * strcat (char * dest, const char * src);
    ```

    功能:把src接在dest指向的字符串后面

4. strcmp(string compare)

    声明:
    ```c
    extern int strcmp (char *str1 , char *str2);
    ```

    功能:从左到右逐个按照ASCII码进行比较，遇到不相等的字符或者'\0'停止，大于则返回正数，小于返回负数，相等返回0

    1. "A"<"B"  
    2. "A"<"AB"   
    3. "Apple"<"Banana"  
    4. "A"<"a"  
    5. "compare"<"computer"  

    PS.注意是返回正数或者负数，不是±1

5. strlen(string lenth)

    声明:
    ```c
    size_t strlen (const char * a);
    ```

    功能:求的是字符串的长度，从字符串的首地址开始到遇到第一个'\0'停止计数

6. strstr

    声明:
    ```c
    char * strstr (char *str1 , char *str2);
    ```

    功能:在串中查找指定字符串的第一次出现，返回的是str1的某个元素的指针

