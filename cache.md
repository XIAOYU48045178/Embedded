`数据类型`
--

`C 语言数据类型可分为 基本类型 构造类型 空类型`

`> 基本类型` 

`C 语言程序设计中最小数据单元即原子数据类型 其他数据类型 结构体 共用体可以使用这些基本数据类型`

`基本数据类型可分为 整型 浮点型 字符型 枚举型 指针型`

`> 构造类型` 

`在基本数据类型基础上构造而成的复合数据类型表示更为复杂的数据类型`

`构造类型可分为 数组 结构体 共用体`

`> 空类型` 

`特殊的数据类型 所有数据类型的基础 空类型并非无类型`


`> 枚举类型`

```c
#include <stdio.h>  
  
enum color { RED, GREEN, BLUE};  
  
int main() {  
    enum color mColor = RED;  
  
    if (mColor == RED) {  
        printf("isRED\n");  
    } else if (mColor == GREEN) {  
        printf("isGREEN\n");  
    } else if (mColor == BLUE) {  
        printf("isBLUE\n");  
    }  

    return 0;  
}
```

`> 指针类型` `有则值无则指针`

```c
#include<stdio.h>
int main(){
	int v1 = 10;
    int *v2 = NULL;
    v2 = &v1;
    printf("%p %d %d",v2,v2,*v2);
    return 0;
}
```







```c
#include<stdio.h>
int main(){
    
    return 0;
}

类型转换 int float 变量作用域