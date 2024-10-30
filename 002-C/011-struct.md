`结构体`
--

`结构是 C 编程中另一种用户自定义的可用的数据类型 它允许您存储不同类型的数据项` `结构体中的数据成员可以是基本数据类型 也可以是其他结构体类型 指针类型等 `

`> 定义结构`

`结构体定义由关键字 struct 和结构体名组成 结构体名可以根据需要自行定义` 

`struct 语句定义了一个包含多个成员的新的数据类型`

```c
struct Class {
    class-list
    class-list
    ...
} class ;
```

`CLASS 是结构体标签` `class-list 是标准的变量定义` `class 结构变量 定义在结构的末尾 最后一个分号之前 您可以指定一个或多个结构变量`

```c
struct Id {
    int id;
    ...
} id;
```

`一般情况下 CLASS、class-list、class 这 3 部分至少要出现 2 个`

`拥有 2 个成员的结构体 分别为整型的 i 双精度的 d` `结构体的标签被命名为 Class 没有声明结构体变量`

```c
struct Class
{
    int i;
    double d;
};
```

`定义结构体变量 class1 class2 class3` `struct Class class1, class2[20], *class3;`

`可以用 typedef 创建新类型`

```c
typedef struct{
    int a;
    char b;
    double c;
} Class;
```

`现在可以用 Class 作为类型声明新的结构体变量` `Class class1, class2[20], *class3;`

`此结构体的声明包含了其他的结构体`

```c
struct Class1{
    char string[100];
    struct Class2 class;
};
```

`此结构体的声明包含了指向自己类型的指针`

```c
struct Class{
    char string[100];
    struct Class *class;
};
```

`如果两个结构体互相包含 则需要对其中一个结构体进行不完整声明`

`struct Class2;` `对结构体 Class2 进行不完整声明`

`结构体 Class1 中包含指向结构体 Class2 的指针`

```c
struct Class1{
    struct Class2 *class2;
};
```

`结构体 Class2 中包含指向结构体 Class1 的指针 在 Class1 声明完后  Class2 也随之进行声明`

```c
struct Class2{
    struct Class1 *class1;
};
```

`结构体变量的初始化`

`和其它类型变量一样 对结构体变量可以在定义时指定初始值` 

```c
#include <stdio.h>

struct Id{
   int id;
} id = { 0 };
```

`访问结构成员`

`为了访问结构的成员 我们使用成员访问运算符 .`

`可以使用 struct 关键字来定义结构类型的变量`

```c
struct Class{
    int id;
};

int main(){
    struct Class class;
    class.id = 0;
    return 0;
}
```

`结构作为函数参数`

`可以把结构作为函数参数 传参方式与其他类型的变量或指针类似`

`指向结构的指针`

您可以定义指向结构的指针 方式与定义指向其他类型变量的指针相似 如下所示：

struct Books *struct_pointer;
现在 您可以在上述定义的指针变量中存储结构变量的地址 为了查找结构变量的地址 请把 & 运算符放在结构名称的前面 如下所示：

struct_pointer = &Book1;
为了使用指向该结构的指针访问结构的成员 您必须使用 -> 运算符 如下所示：

struct_pointer->title;
让我们使用结构指针来重写上面的实例 这将有助于您理解结构指针的概念：


结构体大小的计算
C 语言中 我们可以使用 sizeof 运算符来计算结构体的大小 sizeof 返回的是给定类型或变量的字节大小 

对于结构体 sizeof 将返回结构体的总字节数 包括所有成员变量的大小以及可能的填充字节 

以下实例演示了如何计算结构体的大小：

注意 结构体的大小可能会受到编译器的优化和对齐规则的影响 编译器可能会在结构体中插入一些额外的填充字节以对齐结构体的成员变量 以提高内存访问效率 因此 结构体的实际大小可能会大于成员变量大小的总和 如果你需要确切地了解结构体的内存布局和对齐方式 可以使用 offsetof 宏和 __attribute__((packed)) 属性等进一步控制和查询结构体的大小和对齐方式 