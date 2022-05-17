# 打表法（预处理法/离线算法）

打表法就是将题目中需要的答案集合提前算出来，存到代码里，根据题目所需取答案，这种方法通常只需要将程序挂着，在表打完后进行加工，最终取答案程序时间复杂度为O(1)，空间复杂度为O(n)(n为答案规模)； ——~~~沃兹·基朔德~~~

以洛谷[P1980](https://www.luogu.com.cn/problem/P1980)为原例，计算1到n的所有数字中，1出现了多少次

正常做法：
```c
#include <stdio.h>
#include <stdlib.h>
int main(){
    int n,cnt=0,temp;
    scanf("%d",&n);
    for(int i=1;i<=n;i++){
        temp=i;
        while(temp){
            if(temp%10==1)
                cnt++;
            temp/=10;
        }
    }
    printf("%d",cnt);
    return 0;
}
```

但是如果是有多组输入的话，比如第一组输入100，第二组输入200；这样的输入如果还是分两次大循环，那么其实1~100的数据计算了两次。为了改进第一次的结果可以用在第二次中

~~实际上可以直接把进行次数最多的大循环的结果放在一个数组里面，然后直接在数组里面寻找答案就好；~~
也可以不用次数最多的那一个循环，直接循环很多次数也行

↑该方法不行，因为scanf函数必须得在打表之后

```c
#include <stdio.h>
#include <stdlib.h>
int main(){
    int n,cnt=0,temp,a[10000]={};
    
    for(int i=1;i<=10000;i++){
        temp=i;
        while(temp){
            if(temp%10==1)
                cnt++; 
            temp/=10;
        }
        a[i]=cnt;
    }
    scanf("%d",&n);
    printf("%d",a[n]);
    return 0;
}
```
 
"这几秒在提交的代码中过不去，但可以在做题的时候挂着，如此简单的AC啊。"