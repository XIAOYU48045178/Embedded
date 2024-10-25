`hello world`
--

```c
#include<stdio.h> --# 预处理 include 包含 <stdio.h> 输入输出流头文件
int main(){ --不标准的主函数 有且只有一个 无论主函数在哪程序由主函数开始
    printf("hello world"); --输出流函数 程序到外界
    return 0;
}
```

`Basic`
--

```c
#include <stdio.h>
#define PI 3.14159

int add(int n1, int n2); --statement

int main() {
    int n1, n2, sum;

    printf("Please Input: ");
    scanf("%d %d", &n1, &n2);

    sum = add(n1, n2);

    printf("sum = %d\n", sum);

    return 0;
}

int add(int n1, int n2) { --定义
    return n1 + n2;
}
```

`> 头文件包含`

`头文件通常在程序的开头使用 #include 指令包含 头文件提供了函数和库的声明 如标准输入输出库 <stdio.h>、标准库 <stdlib.h> 等 它们定义了函数、宏、常量等使程序能够使用预定义的库函数 示例：#include <stdio.h>`

`> 宏定义`

`宏是通过 #define 指令定义的符号常量或代码片段 宏在编译前由预处理器替换为其定义的内容 常用于定义常量或者复杂的代码块 示例：#define PI 3.14159`

`> 函数声明`

`在 C 语言中 函数的声明必须在函数定义或调用之前 声明提供了函数的返回类型、函数名和参数列表 以便编译器知道如何调用该函数`

`> 主函数`

`main 函数是 C 程序的入口点 每个 C 程序都必须包含一个 main 函数 程序从 main 开始执行 返回值通常为 0 表示程序成功执行` 

`> 变量声明`

`在 C 程序中 所有变量必须在使用前声明 变量可以在 main 函数中声明 也可以在其他函数中或全局声明`

`> 语句和表达式`

`语句是 C 程序的基本执行单元 通常是函数调用、赋值、控制语句（如 if、for 等）或表达式 表达式是由变量、操作符和常量组成的代码片段` 

`> 控制流语句`

`控制流语句用于控制程序执行的顺序 包括 if、for、while、do-while 等循环和条件分支语句` 

`函数定义`

`函数定义包含实际的函数体 它描述了函数的具体实现 函数通常包含参数、局部变量和返回值` 

`返回语句`

`return 语句用于终止函数的执行 并将控制权交还给调用函数 main 函数的返回值通常是 0 表示正常执行` 

`分隔符 SEPARATORS`
--

`分隔符用于分隔语句和表达式常见的分隔符包括` ``逗号用于分隔变量声明或函数参数` `分号是语句结束符也就是说每个语句必须以分号结束它表明一个逻辑实体的结束` `括号 圆括号用于分组表达式函数调用 花括号 {} 用于定义代码块 方括号 [] 用于数组下标`

`注释`
--

`C 语言有两种注释方式 // /* */`

`标识符 Identifiers`
--

`标识符是程序中变量、函数、数组等的名字 标识符由字母数字和下划线组成但第一个字符必须是字母或下划线不能是数字`

`C 标识符内不允许出现标点字符如 @、$ 和 % C 是区分大小写的编程语言`

`常量 Constants`
--

`常量是固定值在程序执行期间不会改变 常量可以是整型常量、浮点型常量、字符常量、枚举常量等`

`字符串字面量 String LITERALS`
--

`字符串字面量是由双引号括起来的字符序列 字符串末尾会自动添加一个空字符 '\0'`

`运算符 OPERATORS`
--

`运算符用于执行各种操作如算术运算、逻辑运算、比较运算等`

`空格`
--

`只包含空格的行 被称为空白行 编译器会完全忽略它 在 C 中 空格用于描述空白符、制表符、换行符和注释 空格分隔语句的各个部分 让编译器能识别语句中的某个元素（比如 int）在哪里结束 下一个元素在哪里开始 为了增强可读性 您可以根据需要适当增加一些空格`

`关键字 KEYWORDS`
--

```c
int short long float double char signed unsigned enum struct union typedef sizeof
if else switch case default do while for continue break goto
auto  register static extern
void return 
const            
volatile 
```

`1999 年 12 月 16 日 ISO 推出了 C99 标准该标准新增了 5 个 C 语言关键字` `inline restrict _Bool _Complex _Imaginary`

`2011 年 12 月 8 日 ISO 发布 C 语言的新标准 C11 该标准新增了 7 个 C 语言关键字` `_Alignas _Alignof _Atomic _Static_assert _Noreturn _Thread_local _Generic`

`变量的存储类型有 auto static extern register 四种 而函数的存储类型却只有 static 和 extern 两种`

`> auto`

`在 C 语言中 auto 是一个存储类说明符 用于指定变量的存储期`

`auto 变量是局部的 它们只在定义它们的函数或代码块内有效一旦函数执行完毕或代码块被退出 auto 变量就会被销毁`

`auto 变量的存储期是临时的 它们存储在栈内存中当函数被调用时 auto 变量会被创建即分配栈内存当函数返回时 auto 变量会被销毁即释放栈内存`

`在 C 语言中 如果你在函数内部定义一个变量而没有指定存储类说明符 那么这个变量默认就是 auto 存储类的 因此 auto 关键字在大多数情况下是可以省略的`

`> static`

`! 修饰变量`

`!! 静态局部变量`

`当 static 修饰局部变量时 它会改变局部变量的存储位置 将其从栈区 自动变量存储区 移动到全局数据区 静态存储区 这样做的结果是 静态局部变量的生命周期被延长 它会在程序的整个运行期间保持其值 而不仅仅是在声明它的函数被调用期间 同时 静态局部变量的作用域仍然保持不变 即它只能在声明它的函数内部被访问`

`静态局部变量的生命周期是整个程序的执行过程所以当程序走出定义该静态局部变量的函数时变量并没有被销毁而一直存在直到再次调用该函数 因此静态局部变量在程序执行声明该变量时被首次初始化以后的函数调用不再进行初始化也有人称作静态局部变量只进行一次初始化`

```c
void cnt() {  
    static int cnt = 0;  
    cnt = cnt + 1;  
    printf("%d", cnt);  
}  

int main() {  
    for(int i = 0; i < 10; i++){
        cnt();
    }  
    return 0;  
}
```

`在这个例子中 cnt 是一个静态局部变量 它在 cnt 函数的多次调用之间保持其值从而实现了计数功能`

`!! 静态全局变量`

`当 static 修饰全局变量时 它会限制全局变量的作用域使其只能在声明它的源文件或编译单元内部被访问 这有助于封装数据防止不同模块之间的直接依赖 静态全局变量在程序的整个运行期间保持其值但它们不会像普通全局变量那样被其他文件访问或修改`

```c
--1.c 
static int moduleVar = 42;  

void modifieVar(int value) {  
    moduleVar = value;  
}  

void printVar() {  
    printf("VAR: %d\n", moduleVar);  
}  

--2.c 
#include "1.c"  

int main() { --moduleVar = 200 编译错误无法访问静态全局变量
    printVar(); --42  
    modifieVar(100);  
    printVar(); --100  
    return 0;  
}
```

`! 修饰函数`

`当 static 修饰函数时 它会限制函数的作用域 使其只能在声明它的源文件或编译单元内部被调用 这有助于隐藏实现细节 减少命名冲突 并提高程序的模块化程度 由于静态函数的作用域被限定在单个文件内 因此可以在不同的源文件中使用相同名称的函数而不会产生冲突`

```c 
--1.c 
static void helloFunction() {  
    printf("hello function\n");  
}  
  
void publicFunction() {  
    printf("public function\n");  
    helloFunction(); 
}  
  
--2.c 
#include "1.c"  
  
int main() { --helloFunction 编译错误无法访问静态函数
    publicFunction(); 
    return 0;  
}
```

`> const`

`在 C 语言中 const 可以修饰其值在初始化后不能被修改的变量 使用 const 关键字可以提高程序的可读性和安全性 因为它明确指出了哪些变量是不应该被修改的`

`! 场景`

`!! 修饰变量`

`const int maxValue = 100` `maxValue 被声明为一个常量 其值为 100 且不能在程序的其他部分被修改`

`!! 修饰指针`

`可以修饰 指针本身 指针所指向的值 同时修饰两者` 

`!!! 修饰指针指向的值`

`const int *p = &v1` `这个例子中 p 是一个指向 int 类型常量的指针` `你不能通过 p 修改它所指向的值即 v1 的值 但 p 本身可以指向其他地址`

`!!! 修饰指针本身`

`int *const p = &v1` `这个例子中 p 是一个常量指针` `它指向的地址不能改变 但你可以通过 p 修改它所指向的值即 v1 的值`

`!!! 同时修饰指针和指向的值`

`const int *const p = &v1` `这个例子中 p 既不能指向其他地址 也不能通过 p 修改它所指向的值`

`!! 修饰函数参数`

`在函数定义中 const 可以用于修饰参数 以表明该参数在函数内部不会被修改 这可以增加函数的安全性 并防止意外的修改`

`void printValue(const int v1) { --v1 的值在函数内部不能被修改 }`

`对于指针类型的参数 const 可以修饰指针本身 指针指向的值 同时修饰两者`

`!! 修饰函数返回值`

`const 也可以用于修饰函数的返回值 以表明返回的值是一个常量 不应该被修改 然而需要注意的是 对于基本数据类型的返回值 const 修饰符通常没有太大的实际意义 因为返回值通常是通过值传递的 而不是通过引用或指针传递的 但对于指针或引用类型的返回值 const 修饰符可以确保返回的对象不会被修改`

`> extern`

`不能定义变量或函数只能用于声明因此变量的声明和定义通常放在不同的文件中` `当声明一个全局变量或函数时需要确保该变量或函数的定义在编译链接时可以找到 否则编译器会报错` `可以多次声明同一个变量或函数 但只有第一次声明是有效的后续的声明只是重申了该变量或函数的存在性并不会产生新的存储空间` `本身不分配内存空间它只是告诉编译器某个变量或函数是在其他地方定义的并需要在链接阶段找到其定义` 

`提高代码的可维护性` `通过将变量或函数的声明与它们的定义分开可以更容易地更新和维护代码当需要修改变量或函数的定义时只需要在一个地方进行修改即可` `支持模块化编程` `允许在不同源文件中组织变量和函数从而提高代码的可重用性和可读性这有助于实现模块化编程使得代码更加清晰和易于管理`

`extern 变量和函数具有全局作用域可以在程序的任何地方访问`

`避免在多个文件中重复定义相同的变量或函数这会导致链接错误`

`头文件使用 通常将 extern 声明放在头文件中然后在需要的源文件中包含该头文件`

`! 声明外部变量`

`可以用来声明一个在其他源文件中定义的全局变量 这样 编译器在找不到变量的定义时会在其他文件中查找` `多个源文件可以共享同一个全局变量`

`! 声明外部函数`

`可以用来声明一个在其他源文件中定义的函数 这样 编译器在找不到函数的定义时 会在其他文件中查找` `需要注意的是对于函数的声明 如果函数已经在当前文件中定义了那么关键字可以省略 默认情况下函数的声明是全局可见的`

`! 引用外部符号`

`可以用来引用其他文件中定义的全局变量、函数或符号`

```c --variables.h
#ifndef VARIABLES_H
#define VARIABLES_H

extern int v1;
extern int v2;

#endif
```

```c --functions.h
#ifndef FUNCTIONS_H
#define FUNCTIONS_H

void printExternVariables();
void printHello();

#endif
```

```c --1.c
#include <stdio.h>
#include "variables.h"
#include "functions.h"

int v1 = 3;
int v2 = 5;

void printExternVariables() {
    printf("v1: %d, v2: %d\n", v1, v2);
}

void printHello() {
    printf("hello world\n");
}
```

```c --2.c
#include <stdio.h>
#include "variables.h"
#include "functions.h"

int main() {

    printf("v1 in main: %d\n", v1);
    printf("v2 in main: %d\n", v2);
    

    printExternVariables();
    printHello();
    
    return 0;
}
```

```c
--1.c  
extern void printHello();  
  
int main() {  
    printHello();
    return 0;  
}  
  
--2.c  
#include <stdio.h>  
  
void printHello() {
    printf("Hello World!\n");  
}
```

`> register`

`向编译器提出一个请求 即将某个变量存储在 CPU 的寄存器中 而不是存储在内存中 寄存器是 CPU 内部的一种快速存储单元 访问速度比内存快得多 因此如果编译器接受了这个请求那么使用这个变量进行的操作可能会执行得更快 然而 需要注意的是 register 关键字只是向编译器提出一个建议或请求 并不是强制性的编译器可能会忽略这个请求` 

`! 忽略这个请求几种情况 还有很多`

`寄存器数量有限现代 CPU 的寄存器数量是有限的 如果程序中使用了大量的 register 变量 编译器可能无法将它们全部存储在寄存器中`

`编译器优化 编译器可能会根据自己的优化策略来决定是否将变量存储在寄存器中 即使你使用了 register 关键字 编译器也可能出于优化考虑将其存储在内存中`

`变量地址需求 如果程序需要获取变量的地址例如 通过指针操作那么编译器通常无法将其存储在寄存器中 因为寄存器没有固定的内存地址`

`变量类型某些类型的变量如结构体或大型数组可能无法存储在寄存器中因为寄存器的大小有限`

`> sizeof`

`sizeof 是一个操作符 用于确定对象或类型所占的内存大小以字节为单位 它可以用于各种数据类型 如 int float double char 等 结构体 struct 联合体 union 以及指针类型 当 sizeof 用于确定一个变量或表达式的大小时 它会在编译时计算该值 而不是在运行时 这意味着 sizeof 的结果是一个编译时常量 其值在编译时就已确定`

```c
#include<stdio.h>
int main(){
	printf("%d",sizeof(int));
}
```

`> typedef`

`其作用是为一种数据类型定义一个新的名字 包括内部数据类型和自定义数据类型`

`typedef unsigned long uint32` `uint32 v1 即 unsigned long v1;`
