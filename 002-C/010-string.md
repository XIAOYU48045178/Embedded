`字符串`
--

`在 C 语言中 字符串实际上是使用空字符 \0 结尾的一维字符数组 因此 \0 是用于标记字符串的结束` `空字符又称结束符是一个数值为 0 的控制字符 \0 是转义字符 不是字符 0 而是空字符` 

`由于在数组的末尾存储了空字符 \0 所以字符数组的大小比单词 hello 的字符数多一个` `char strArr[6] = {'h', 'e', 'l', 'l', 'o', '\0'};` `依据数组初始化规则可以把上面的语句写成` `char strArr[] = "hello"` `不需要把 null 字符放在字符串常量的末尾 C 编译器会在初始化数组时自动把 \0 放在字符串的末尾`
 
`统计字符数组中字符的个数`
--

```c
#include<stdio.h>
int strlen(char strArr[]){

	for(int i=0; strArr[i]!='\0'; i++);
	return i;
}
int main(){
	char strArr[100] = {};
    int n = 0;
	gets(strArr);
	n=strlen(strArr);

	printf("%d\n",n);
	return 0;
}
```

`字符串连接`
--

```c
#include<stdio.h>
void lencat(char strArr1[],char strArr2[]){
	int i = 0;
	for(i=0; strArr1[i]!='\0'; i++);
	for(int j=0; strArr2[j]!='\0'; j++){	
		strArr1[i++]=strArr2[j];
	}
	strArr1[i]='\0';
}
int main(){
	char strArr1[100] = {}, strArr2[20] = {};
	gets(strArr1);
	gets(strArr2);
	lencat(strArr1,strArr2);
	puts(strArr1);
    return 0;
}
```

`字符统计`
--

```c
#include <stdio.h>  
  
int countCharOccurrences(const char *strArr, char c1);  
  
int main() {  
    char strArr[] = "hello world! hello C!";  
    char c1;  
  
    printf("请输入要统计的字符: ");  
    scanf(" %c", &c1); --注意%c前的空格，用于消耗可能存在的换行符  
  
    int count = countCharOccurrences(strArr, c1);  
  
    printf("字符 '%c' 在字符串中出现了 %d 次\n", c1, count);  
  
    return 0;  
}  
   
int countCharOccurrences(const char *strArr, char c1) {  
    int count = 0;  
    while (*strArr != '\0') {  
        if (*strArr == c1) {  
            count++;  
        }  
        strArr++;  
    }  
    return count;  
}
```

`字符串删除`
--

```c
#include<stdio.h>
void strdel(char strArr[]){
	int i,j=0;
	for(i=0;strArr[i]!='\0';i++)
		if(strArr[i]>='A'&&strArr[i]<='Z'||strArr[i]>='a'&&strArr[i]<='z')	strArr[j++]=strArr[i];
	strArr[j]='\0';
}
int main(){
	char strArr[100] = {};
	gets(strArr);
	strdel(strArr);
	puts(strArr);
    return 0;
}
```
