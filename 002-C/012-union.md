`共用体`
--

`共用体是一种特殊的数据类型 允许您在相同的内存位置存储不同的数据类型 您可以定义一个带有多成员的共用体 但是任何时候只能有一个成员带有值 共用体提供了一种使用相同的内存位置的有效方式` 

`定义共用体`

`为了定义共用体 您必须使用 union 语句 方式与定义结构类似 union 语句定义了一个新的数据类型 带有多个成员 union 语句的格式如下`

```c
union Data
{
   int i;
   float f;
   char str[20];
} data;
```

`可以根据需要在一个共用体内使用任何内置的或者用户自定义的数据类型`

`共用体占用的内存应足够存储共用体中最大的成员`

`访问共用体成员`

`为了访问共用体的成员 我们使用成员访问运算符 .`

```c
#include <stdio.h>
#include <string.h>
 
union Data
{
   int i;
   float f;
   char  str[20];
};
 
int main( )
{
   union Data data;        
 
   data.i = 10;
   data.f = 10.5;
   strcpy( data.str, "1234567890123456789");
 
   printf( "data.i : %d\n", data.i);
   printf( "data.f : %f\n", data.f);
   printf( "data.str : %s\n", data.str);
 
   return 0;
}
```

`在这里 我们可以看到共用体的 i 和 f 成员的值有损坏 因为最后赋给变量的值占用了内存位置 这也是 str 成员能够完好输出的原因`

`使用共用体的主要目的`

```c
#include <stdio.h>
#include <string.h>
 
union Data
{
   int i;
   float f;
   char  str[20];
};
 
int main( )
{
   union Data data;        
 
   data.i = 10;
   printf( "data.i : %d\n", data.i);
   
   data.f = 220.5;
   printf( "data.f : %f\n", data.f);
   
   strcpy( data.str, "123456789");
   printf( "data.str : %s\n", data.str);
 
   return 0;
}
```

`在这里所有的成员都能完好输出 因为同一时间只用到一个成员` 