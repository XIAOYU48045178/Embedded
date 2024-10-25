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

`关键字 typedef`
--

`其作用是为一种数据类型定义一个新的名字 包括内部数据类型和自定义数据类型`

`typedef unsigned long uint32; uint32 v; 即 unsigned long v;`

`变量与常量`
--

`> 变量的定义` 

`变量采用先定义后使用的规则` `说明符(一个或多个) 变量或变量变量表达式列表` `说明符包括 变量基本类型的关键字 存储类型 作用域` `相同作用域变量名不能重复`

`int var = 5` `首先电脑内存开辟一个名称为 var 的空间 然后进行赋值`

`int v = 5;` `int v; v = 5;` `int *v;`

`> 常量的定义`

`! const 定义常量`

`const int v = 10; int const v = 10;`

`const int *a;` `有则值无则指针`

`const 修饰指针 a 所指的对象 即 值 也就是说无法通过指针 a 修改其指向对象的值但是可以修改指针的地址即可以指向其他对象`

`int * const a;` 

`const 修饰的是指针 a 因此指针地址不可以改变而指针指向对象的值可以改变`

`! define 定义常量`

`define 是预处理命令 使用 define 定义常量实际是进行符号替换 #define符号名 替换列表 #define XI "XIAO YU" 所有的 XI 都会被替换为 XIAO YU`

`变量作用域`
--

``

`> 局部变量 全局变量`

`局部变量 定义在函数里面的变量称为局部变量 如果不进行初始化默认值为随机数`

`局部变量在函数或代码块内定义 其作用域和生命周期仅限于该区域 存储在栈上 动态分配并自动回收内存 它们有助于封装函数功能 提高代码模块化` 

`全局变量则在所有函数外部定义整个程序都可见 生命周期贯穿程序运行始终 存储在数据段静态分配内存 全局变量便于跨函数共享数据 但过度使用会降低代码可读性和可维护性且可能引发多线程并发访问问题 使用全局变量时需避免命名冲突防止意外覆盖或修改 同时在多线程环境中应特别小心考虑使用同步机制保护数据一致性 `



```
能表示数学式 x<y<z 的 C 语言表达式是


A)(x<y)&&(y<z)                  B (x<y)AND(y<z)
C) (x<y<z)                      D) (x<y)&(y<z)
```

```c
#include<stdio.h>
int main(){
    for(int i = 1; i <= 1000; i++){
        i % 3 == 0 && i % 5 != 0 && printf("%d\n",i);
    }
    return 0;
}
```

```c
#include<stdio.h>
int main(){
    
    return 0;
}