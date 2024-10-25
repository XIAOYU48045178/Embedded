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
void return extern
auto static 
const            
register           
volatile 
```

`1999 年 12 月 16 日 ISO 推出了 C99 标准该标准新增了 5 个 C 语言关键字` `inline restrict _Bool _Complex _Imaginary`

`2011 年 12 月 8 日 ISO 发布 C 语言的新标准 C11 该标准新增了 7 个 C 语言关键字` `_Alignas _Alignof _Atomic _Static_assert _Noreturn _Thread_local _Generic`

`> extern`



