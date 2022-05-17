# 有关回文数的算法

## 回文数的判断
最快方式：

```c
int isPalin(int n){
    int s=0,p;
    int m=n;
    while(n>0){
        s=s*10+n%10;
        n/=10;
    }
    return s==m;
}
```

较慢方式：
```c
int reverseNumberJudging(int n){
    int temp=n,lenth;
    for(lenth=0;temp>0;lenth++)
        temp/=10;
    int flag=1,shut=1;
    while(flag&&shut){
        if(n<10)
            shut=0;
        else if(n/(int)pow(10,lenth-1)==n%10){
            n%=(int)pow(10,lenth-1);//去掉最高位
            n/=10;//去掉最低位
            lenth-=2;
        }
        else
            flag=0;
        int button=1;
        while(button&&n!=0){
            if(n/(int)pow(10,lenth-1)==0){//进行是否中间消去了0的判断
                if(n%10==0){
                    n/=10;
                    lenth-=2;
                }
                else{
                    button=0;
                    flag=0;
                }
            }
            else
                button=0;
        }
    }
    return flag;
}
//当然打表也行，就另说了
```

## 回文数的生成

这里以生成回文非负数为例

较快方法：
```c
#include <stdio.h>
#include <stdlib.h>
#include <math.h>
int main(){
    int min,max,p=0,flag=1,i=10;//flag是判断奇数或者偶数的
    scanf("%d %d",&min,&max);
    for(int i=0;i<10;i++)
        if(i>=min&&i<=max)
            printf("%d\n",i);
    while(p<=max){
        for(int v=i;v<=i*10-1&&p<=max;v++){
            int s=0,n=v,len=0;
            while(n!=0){
                s=s*10+n%10;
                n/=10;
                len++;
            }
            p=(flag?(s%(int)pow(10,len-1)):s)+v*(int)pow(10,(len-flag));//生成奇数位的回文数
            if(p>=min&&p<=max)
                printf("%d\n",p);
        }
        flag=!flag;     //这里运用了奇偶开关
        i*=(flag?10:1);    //到偶数位的时候才能乘10
    }
    return 0;
}
```

### 总结：当一道题要求生成具有多种性质的数字的时候`从最小值到最大值一个一个判断是不是符合这些性质`要比`生成含部分性质的数字，在判断是不是符合其他性质`可能要快的多