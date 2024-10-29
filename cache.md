`数据类型`
--

`C 语言数据类型可分为 基本类型 构造类型 空类型`

`> 基本类型` 

`C 语言程序设计中最小数据单元即原子数据类型 其他数据类型 结构体 共用体可以使用这些基本数据类型`

`基本数据类型可分为 整型 浮点型 字符型 枚举型 指针型`

`> 构造类型` 

`在基本数据类型基础上构造而成的复合数据类型表示更为复杂的数据类型`

`构造类型可分为 数组 结构体 共用体`


`所有的浮点运算都是以双精度进行的即使仅含 float 单精度量运算的表达式也要先转换成 double 型再作运算`

`关于 main 函数的参数`

在有些很专业的书会看到如下代码

int main( int argc, char *argv[] )
上面的代码中 main 函数带了参数。

但是有时又会看见main函数没有参数，如下：

int main()
那么 main 函数到底有没有参数，有没有参数会不会有什么影响？

main 函数其实与我们写的函数没有什么区别，它也会有自己的参数。

argc 和 argv 是 main 函数的形式参数。

这两个形式参数的类型是系统规定的。如果 main 函数要带参数，就是这两个类型的参数；否则main函数就没有参数。

变量名称argc和argv是常规的名称，当然也可以换成其他名称。在传入参数后main函数收到参数后就会做自己的事。那么，实际参数是如何传递给main函数的argc和argv的呢？我们知道，C程序在编译和链接后，都生成一个exe文件，执行该exe文件时，可以直接执行；也可以在命令行下带参数执行，命令行执行的形式为：可执行文件名称 参数1 参数2 ... ... 参数n。可执行文件名称和参数、参数之间均使用空格隔开。

如果按照这种方法执行，命令行字符串将作为实际参数传递给main函数。具体为：

 (1) 可执行文件名称和所有参数的个数之和传递给 argc；
 (2) 可执行文件名称（包括路径名称）作为一个字符串，首地址被赋给 argv[0]，参数1也作为一个字符串，首地址被赋给 argv[1]，... ...依次类推。





类型转换 int float 变量作用域 arr funcation




字符串
--

```c
#include<stdio.h>
int main(){
    char strArr[100] = {};

	scanf("%99[^\n]", strArr);

    printf("%s",strArr);
    
}
```


```c
#include<stdio.h>
#include<stdlib.h>
#include<time.h>

int main(){
    int arr1[7] = {};
    srand(time(0));

    for(int i = 0; i < 7; i++){
        arr1[i] = rand() % 35 + 1;
        for(int j = 0; j < i; j++){
            if(arr1[j] == arr1[i]){
                i--;
                break;
            }
        }    
    }

    int arr2[7] = {};
    for(int i = 0; i < 7; i++){
        scanf("%d",&arr2[i]);
    }
    
    
    for(int i = 0; i < 7; i++){
		printf("%d ",arr1[i]);
    }
    printf("\n");
    for(int i = 0; i < 7; i++){
		printf("%d ",arr2[i]);
    }
    printf("\n");
    

    int cnt = 0;
    for(int i = 0; i < 7; i++){
        for(int j = 0; j < 7; j++){
            if(arr2[i] == arr1[j]){
                cnt++;
                break;
            }
        }
    }
    
	printf("cnt: %d\n",cnt);

    switch(cnt){
        case 0: case 1: case 2:
            puts("0");
            break;
        case 3:
            puts("500");
            break;
        case 4:
            puts("5000");
            break;
        case 5:
            puts("10000");
            break;
        case 6:
            puts("1000000");
            break;
        case 7:
            puts("5000000");
            break;
    }
    
    return 0;
}
```

```c
#include<stdio.h>
#include<stdlib.h>
#include<time.h>

int main(){
    int v1 = 0;
    srand(time(0));


    v1 = rand() % 10 + 1;
  
    int v2 = 0;
    while(1){
        scanf("%d",&v2);
        if(v1 == v2){
            puts("YES");
            break;
        }
        if(v1 > v2){
            puts("小了");
        }
        if(v1 < v2){
            puts("大了");
        }
    }
    
    return 0;
}
```