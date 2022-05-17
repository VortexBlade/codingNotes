# 高精度算法:

## 高精度加法

算法的核心的是指针，进位运算

这里以高精度加法为例
```c
void ADD(int *a,int *b){             //两个数组存放高精度的数字,   ps.该指针不会影响原数组的指针，原因是c语言的按值传递的特性

    //高精度加法,计算结果存到a数组里
    int *A=a,cnt=0;                  //这里另存负责以后清零指针，便于下面的进位
    while(cnt<100){  
        *a+=*b;  
        a++;  
        b++;  
        cnt++;  
    }

    //进位运算  
    a=A;/*指针归零*/  
    cnt=0;/*计数器清零*/  
    while(cnt<100){  
        if(*a>9){  
            *(a+1)+=(*a/10);  
            *a%=10;  
        }  
        a++;  
        cnt++;  
    }  
}
```

## 例题（高精度阶乘求和）
源自洛谷[P1009](https://www.luogu.com.cn/problem/P1009)
```c
#include <stdio.h>
#include <stdlib.h>
//精度：100位内
void ADD(int *a,int *b){
    //高精度加法,计算结果存到a数组里
    int *A=a,cnt=0;  
    while(cnt<100){  
        *a+=*b;  
        a++;  s
        b++;  
        cnt++;  
    }  
    //进位运算  
    a=A;/*指针归零*/  
    cnt=0;/*计数器清零*/  
    while(cnt<100){  
        if(*a>9){  
            *(a+1)+=(*a/10);  
            *a%=10;  
        }  
        a++;  
        cnt++;  
    }  
}

void MUL(int *a,int t){  
    //高精度乘法，计算结果放在a数组里  
    int *A=a,cnt=0;  
    while(cnt<100){  
        *a*=t;  
        a++;  
        cnt++;  
    }  
    //进位运算  
    a=A;/*指针归零*/  
    cnt=0;/*计数器清零*/  
    while(cnt<100){  
        if(*a>9){  
            *(a+1)+=(*a/10);  
            *a%=10;  
        }  
        a++;  
        cnt++;  
    }  
}  


int main(){  
    int a[100]={},temp[100]={},n;  
    temp[0]++;  
    scanf("%d",&n);                //n是阶乘求和到几  
    int cnt=1;  
    while(cnt<=n){  
        int i=1;  
        while(i<=cnt){         //先计算阶乘  
            MUL(temp,i);  
            i++;  
        }  
        ADD(a,temp);  
        //temp数组清零  
        temp[0]=1;  
        for(int i=1;i<100;i++)  
            temp[i]=0;  
        cnt++;  
    }  
    //打印数组，先计算位数  
    int flag=1,num;  
    for(int i=99;i>=0&&flag;i--)  
        if(a[i]!=0){  
            flag=0;  
            num=i;  
        }  
    for(int i=num;i>=0;i--)  
        printf("%d",a[i]);  
    return 0;  
}  
```