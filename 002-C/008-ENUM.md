`枚举`
--

`枚举是 C 语言中的一种基本数据类型 用于定义一组具有离散值的常量 它可以让数据更简洁更易读` `枚举类型通常用于为程序中的一组相关的常量取名字以便于程序的可读性和维护性` 

`定义一个枚举类型 需要使用 enum 关键字 后面跟着枚举类型的名称 以及用大括号 {} 括起来的一组枚举常量 每个枚举常量可以用一个标识符来表示 也可以为它们指定一个整数值 如果没有指定那么默认从 0 开始递增`

```c
enum DAY { MON = 1, TUE, WED, THU, FRI, SAT, SUN };
```

`第一个枚举成员的默认值为整型的 0 后续枚举成员的值在前一个成员上加 1 我们在这个实例中把第一个枚举成员的值定义为 1 第二个就为 2 以此类推`

`可以在定义枚举类型时改变枚举元素的值`

```c
enum season { spring, summer=3, autumn, winter };
```

`没有指定值的枚举元素 其值为前一元素加 1 也就说 spring 的值为 0 summer 的值为 3 autumn 的值为 4 winter 的值为 5`

`枚举变量的定义` 
--

`> 先定义枚举类型 再定义枚举变量`

`enum COLOR { RED, GREEN, BLUE};` `enum COLOR color;`

`> 定义枚举类型的同时定义枚举变量`

`enum COLOR { RED, GREEN, BLUE} color;`  

`> 省略枚举名称 直接定义枚举变量`

`enum { RED, GREEN, BLUE} color;`  

```c
#include <stdio.h>  
  
enum COLOR { RED, GREEN, BLUE };  
  
int main() {  
    enum COLOR color = RED;  
  
    if (color == RED) {  
        printf("isRED\n");  
    } else if (color == GREEN) {  
        printf("isGREEN\n");  
    } else if (color == BLUE) {  
        printf("isBLUE\n");  
    }  

    return 0;  
}
```

`枚举遍历`
--

`在 C 语言中 枚举类型是被当做 int 或者 unsigned int 类型来处理的 所以按照 C 语言规范是没有办法遍历枚举类型的` `不过在一些特殊的情况下 枚举类型必须连续是可以实现有条件的遍历`

`枚举类型不连续这种枚举不希望被遍历` `enum { ENUM_0, ENUM_10 = 10, ENUM_11 };`

`将整数转换为枚举`
--

```c
#include <stdio.h>
#include <stdlib.h>
 
int main()
{
    enum COLOR { RED, GREEN, BLUE};
    int i = 1;
    enum COLOR color;

    color = ( enum color ) i; --错误: color = i
    printf("color: %d",color);
    return 0;
}
```
