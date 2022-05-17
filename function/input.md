# ���뺯��

## getchar()
getchar������һ�����뺯����������Ϊ��

```c
int getchar(void);
```
�ɴ˿������ú���ֻҪ��buffer�����У��ڶ�ȡ��һ���ַ�֮��ͻ����һ���ַ�
```c
#include <stdio.h>
#include <stdlib.h>

int main(){
    int ch;
    while(ch=getchar())
        printf("%d\n",ch);
    return 0;
}
```
input:
```
1
```
output:

```
49
10
```
getchar��Ϊ����س����Բſ�ʼɨ�裬���������ȥ�ĳ������ֻ��лس������Ի��ӡ�������ַ���ASCII��

### ����^Z��EOF

![pic](1.jpg)

[�й�����](https://blog.csdn.net/chenming092100/article/details/79583189) 


����`getchar`�����^ZֻҪ��ǰ�����ַ��Ͳ���ʶ���EOF������ʶ���ASCII26���ַ�``

����^Z֮ǰ�����ַ��������ַ�����Ч

���룺��`\n`����֮�����뻺��������``���������ַ�֮ǰ��û���ַ�������еĻ��ͽ�``�ж�Ϊ^Z�������ж�������ջ�����

## gets()

ȫ�ƣ�get string

��������Ϊ
`c
char * gets(char * a);
`
�ú����ص㣺��ɨ���ַ����ĺ������ú������س���ֹͣ���룬���ҽ��س�����buffer����

**PS.��scanf����������**
1. scanf���������ո�tab���س�ֹͣ���룬���ҽ���Щ����buffer����gets���������ո�tab(���'\t')�������س�ֹͣ���룬�����߻س�
2. scanf�����ڶ����ǿհ��ַ�֮ǰ��**���Իس�(��˼���������س�)**(��Ҳ��Ϊʲô���scanfѭ��û������,ÿ��scanfѭ�����������һ�εĻس�)�����gets�����ڶ����հ��ַ�֮ǰֱ�Ӵ�س��Ļ���Ҳ��ֱ�����߻س�
3. gets�ǿ��Զ��س��ģ������Ǵ�(��һ�ε�)������������
4. scanf("");������ջ��������������пհ��ַ�

����

```c
#include <stdio.h>
#include <stdlib.h>
int main(){
    char a[10];
    gets(a);
    char b=*a;
    printf("..%c..",b);
    return 0;
}
```

input:
```
('\n')
```
output:
```
....
```
˵��get���ܶ���س�(�����(��յ���֤��ʽ:�����һ��getchar,���ֳ����ж�))
������

```c
#include <stdio.h>
#include <stdlib.h>
int main(){
    char a[10],b[10],c[10];
    scanf("%s%s",a,b);
    gets(c);
    puts(a);
    puts(b);
    puts(c);
    puts("ended here");
    return 0;
}
```

input:
```
12 34
```
output:
```
12
34

ended here
```
˵��gets��������һ�εĻ�������ȡ�˻س���
���ܽ᣺��εĻس��ǵ����ָ����������ϴεĻس��ǵ�����char������Ҫ����

�����[csdn](https://blog.csdn.net/weixin_42512488/article/details/82831952?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522164543963016780271520767%2522%252C%2522scm%2522%253A%252220140713.130102334.pc%255Fall.%2522%257D&request_id=164543963016780271520767&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~first_rank_ecpm_v1~rank_v31_ecpm-1-82831952.pc_search_result_cache&utm_term=gets%E5%87%BD%E6%95%B0&spm=1018.2226.3001.4187)


## scanf����

scanf�����й�`scanf("%d\n",&a);`֮��\n������  
��һ���������ֺͻس����һ���س��ᵱ���ָ���������scanf���ῴ������س�(�ûس����ڻ�������)�����Ի�ȴ�һ���س����ڶ����������һ�����ݣ����»س�֮����ʱscanf���ֵ�һ�����µĻس����Ƿָ������������ոûس�