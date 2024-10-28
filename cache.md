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
    float consumptionAmount = 0;
    char isMember = 0,way = 0;
    puts("请输入消费金额: ");
    scanf("%f",&consumptionAmount);
    puts("是否为会员？是 Y 否 N: ");
    scanf("%c",&isMember);

    if(consumptionAmount < 0){
        puts("不合法");
        return 0;
    }
    if(consumptionAmount < 2000){
        printf("%f\n",consumptionAmount);
        return 0;
    }
    if(isMember == 'N'){
        consumptionAmount = consumptionAmount * 0.95;
        printf("%f\n",consumptionAmount);
        return 0;
    }
    puts("请选择支付方式: Z V X");
    scanf("%c",&way);

    if(way == 'Z'){
        consumptionAmount = consumptionAmount * 0.85;
    }
    if(way == 'V'){
        consumptionAmount = consumptionAmount * 0.9;
    }
    if(way == 'X'){
        consumptionAmount = consumptionAmount * 0.8;
    }
    printf("%f\n",consumptionAmount);
    return 0;
}
```

`所有的浮点运算都是以双精度进行的即使仅含 float 单精度量运算的表达式也要先转换成 double 型再作运算`

类型转换 int float 变量作用域

```c
