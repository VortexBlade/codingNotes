# ���ٱ�̵�С����

1. ���ٴ�����֪�ַ���:
```c
#include <stdio.h>
#include <stdlib.h>
int main(){
    char * a="abcde";
    puts(a);
    return 0;
}
```
PS.������������ʵ�����ַ�������Ϊ��ָ��û�з���ռ䣬��������������"��"�ַ����ǲ����޸����ݵģ�ֻ�ܽ���puts��ӡ��ֻ�漰�ַ���ָ��ĺ�������(����strcmp)

2. ���ٸ����ַ���
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
PS.ע��while����һ��Ҫ�зֺ�
