# include <string.h>

ͷ�ļ�:string.h

���ֺ���(�Ҿ��ÿ����õ�)

1. strcpy(string copy)

    ����:
    ```c
    char * strcpy (char * destin , char * source);
    ```

    ����:����һ���ַ�������һ��(����'\0')

2. strncpy

    ����:
    ```c
    char * strncpy (char * dest , char * src , size_t n);
    ```

    ���ܣ����ַ���src�����n���ַ����Ƶ��ַ�����dest��(��������strcpyһ������NULL��ֹͣ���ƣ����ǵȴչ�n���ַ���ֹͣ���ƣ�������ָ��  dest��ָ�롣

3. strcat(string catenate)

    ����:
    ```c
    extern char * strcat (char * dest, const char * src);
    ```

    ����:��src����destָ����ַ�������

4. strcmp(string compare)

    ����:
    ```c
    extern int strcmp (char *str1 , char *str2);
    ```

    ����:�������������ASCII����бȽϣ���������ȵ��ַ�����'\0'ֹͣ�������򷵻�������С�ڷ��ظ�������ȷ���0

    1. "A"<"B"  
    2. "A"<"AB"   
    3. "Apple"<"Banana"  
    4. "A"<"a"  
    5. "compare"<"computer"  

    PS.ע���Ƿ����������߸��������ǡ�1

5. strlen(string lenth)

    ����:
    ```c
    size_t strlen (const char * a);
    ```

    ����:������ַ����ĳ��ȣ����ַ������׵�ַ��ʼ��������һ��'\0'ֹͣ����

6. strstr

    ����:
    ```c
    char * strstr (char *str1 , char *str2);
    ```

    ����:�ڴ��в���ָ���ַ����ĵ�һ�γ��֣����ص���str1��ĳ��Ԫ�ص�ָ��

