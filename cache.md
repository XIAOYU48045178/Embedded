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

```c
#include<stdio.h>
int main(){
    int a[4]={};
    
    for(int i = 0; i <= 4; i++){
        scanf("%d",&a[i]);
    }

    int max = a[0];
    int min = a[0];
    int imax = 0, imin = 0;
    for(int i = 1; i <= 4; i++){
        max = max > a[i] ? max : a[i];
        imax = max == a[i] ? i : imax;

        min = min < a[i] ? min : a[i];
        imin = min == a[i] ? i : imin;
    }

    a[imax] = a[imax] ^ a[imin];
    a[imin] = a[imax] ^ a[imin];
    a[imax] = a[imax] ^ a[imin];

    printf("%d %d\n",max,min);

    printf("%d %d\n",imax,imin);

    for(int i = 0; i <= 4; i++){
        printf("%d\n",a[i]);
    }
    
    return 0;
}


```c
#include<stdio.h>
#define N 10
void sort(int a[],int n)
{
	int i,j,t;
	for(i=0;i<n-1;i++)
		for(j=0;j<n-1-i;j++)
			if(a[j]>a[j+1]) {t=a[j];a[j]=a[j+1];a[j+1]=t;}
}
int main()
{
	int a[N]={10,9,8,7,6,5,4,3,2,1},i;
	sort(a,N);
	for(i=0;i<N;i++)
		printf("%d  ",a[i]);
	printf("\n");
    return 0;
}
```

```c
#include<stdio.h>
int main(){
    int arr[19] = {1, 1};
    for(int i = 2; i < 20; i++){
        arr[i] = arr[i - 1] + arr[i -2];
    }

    for(int i = 0; i < 19 / 2 + 1; i++){
        arr[i] = arr[i] ^ arr[19 - i];
        arr[19 - i] = arr[i] ^ arr[19 - i];
        arr[i] = arr[i] ^ arr[19 - i];
    }

    for(int i = 0; i < 20; i++){
        printf("%d ",arr[i]);
    }
    return 0;
}


类型转换 int float 变量作用域 arr funcation

```c
#include<stdio.h>
int main(){
    int a[5]={10,20,30,40,50};
    int b[5]={};
    for(int i = 0; i < 5; i++){
        b[i] = a[i];
    }
    return 0;
}
```

bubble
--

原理：每次两个数进行比较，从数组的前两个元素开始，如果前
面的数>后面的数，就交换
第一趟会求出一个最大值，并且放在最后面，
然后依此类推，经过最多N-1趟，排好序

```c
#include<stdio.h>
int main(){
    int arr[8] = {89, 94, 23, 16, 90, 34, 67, 78};
    for(int i = 0; i < 8; i++){
        for(int j = 0; j < 8 - 1 - i; j++){
            if(arr[j] > arr[j + 1]){
                arr[j] = arr[j] ^ arr[j + 1];
                arr[j + 1] = arr[j] ^ arr[j + 1];
                arr[j] = arr[j] ^ arr[j + 1];
            }
        }
    }
    for(int i = 0; i < 8; i++){
        printf("%d ",arr[i]);
    }
    return 0;
}


字符串
--

