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

`int main( int argc, char *argv[] )`

`int main()`

`那么 main 函数到底有没有参数 有没有参数会不会有什么影响 main 函数其实与我们写的函数没有什么区别 它也会有自己的参数` 

`argc 和 argv 是 main 函数的形式参数 这两个形式参数的类型是系统规定的 如果 main 函数要带参数 就是这两个类型的参数 否则 main 函数就没有参数` 

`变量名称 argc 和 argv 是常规的名称 当然也可以换成其他名称 在传入参数后 main 函数收到参数后就会做自己的事 那么 实际参数是如何传递给 main 函数的 argc 和 argv 的呢 我们知道 C 程序在编译和链接后 都生成一个 exe 文件 执行该 exe 文件时 可以直接执行 也可以在命令行下带参数执行 命令行执行的形式为：可执行文件名称 参数1 参数2 ... ... 参数n 可执行文件名称和参数、参数之间均使用空格隔开` `如果按照这种方法执行 命令行字符串将作为实际参数传递给 main 函数`

`可执行文件名称和所有参数的个数之和传递给 argc`

`可执行文件名称包括路径名称作为一个字符串 首地址被赋给 argv[0] 参数 1 也作为一个字符串 首地址被赋给 argv[1] ... ...依次类推` 



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
int main(){
    int a[3][4] ={ {1,2,3,4},{5,6,7,8},{9,10,11,12} };
    int b[3][4]={ {1,1,1,1},{2,2,2,2},{3,3,3,3} };
    int c[3][4] = {}；

    int* p1 = a;
    int* p2 = b;
    int* p3 = c;

    for(int i = 0; i < 12; i++){
        *p3 = *p1 + *p2;

        printf("%d ",*p3);

        p1++;
        p2++;
        p3++;
    }
}
```

```c
#include<stdio.h>
int sum(int n){
    int sum = 0;
    for(int i = 0; i <= n; i++){
        sum += i;
    }
    return sum;
}

int main(){
    int n = 0;
    scanf("%d",&n);

    printf("%d",sum(n));
    return 0;
}
```

```c
#include <stdio.h>  
  
int gcd(int a, int b);  
int lcm(int a, int b, int gcd_value);  
  
int main() {  
    int num1, num2;  
    int gcd_value, lcm_value;  #include<stdio.h>

float min(float n1, float n2){
    return n1 < n2 ? n1 : n2;
}

int main(){
    float n1 = 1.2, n2 = 1.3;

    printf("%.2f",min(n1, n2));
}
  
    printf("请输入两个整数：\n");  
    scanf("%d %d", &num1, &num2);  
  
    gcd_value = gcd(num1, num2);  
    printf("最大公约数: %d\n", gcd_value);  
   
    lcm_value = lcm(num1, num2, gcd_value);  
    printf("最小公倍数: %d\n", lcm_value);  
  
    return 0;  
}  
  
int gcd(int a, int b) {  
    while (b != 0) {  
        int temp = b;  
        b = a % b;  
        a = temp;  
    }  
    return a;  
}  
    
int lcm(int a, int b, int gcd_value) {  
    return (a / gcd_value) * b;  
}
```

```c
#include <stdio.h>  
  
int gcd(int a, int b);  
int lcm(int a, int b, int gcd_value);  
  
int main() {  
    int num1, num2;  
    int gcd_value, lcm_value;  
  
    printf("请输入两个整数：\n");  
    scanf("%d %d", &num1, &num2);  
  
    gcd_value = gcd(num1, num2);  
    printf("最大公约数: %d\n", gcd_value);  
   
    lcm_value = lcm(num1, num2, gcd_value);  
    printf("最小公倍数: %d\n", lcm_value);  
  
    return 0;  
}  
  
int gcd(int a, int b) {  
    
    int min = a < b ? a : b;
    int i = 0;
    for(i = min; i > 1; i--){
        if(a % i == 0 && b % i == 0) break;
    }
    return i;  
}  
    
int lcm(int a, int b, int gcd_value) {  
    int max = a > b ? a : b;
    int i = 0;
    for(i = max; i <= a * b; i++){
        if(i % a == 0 && i % b == 0) break;
    }
    return i;   
}
```

```c
#include <stdio.h>

int main(void){
	int b[4][4]={ {1,2,3},{4,5,6},{7,8,9} };

	printf("%d %d %d %d\n",b[0][2],b[1][3],b[2][1],b[3][0]);
	
	int b1[3][3]={ {1,2,3},{4,5,6},7,8 };
	printf("%d\n",b1[2][1]);
	return 0;
}
```

```c
#include <stdio.h>

int main(void){
	int b[3][3]={ {1,2,3},4,5,{7,8,9} };
	printf("%d %d %d %d\n",b[0][2],b[1][2],b[2][1],b[2][0]);
	return 0;
}
```


`判断数组中是否存在鞍点鞍点的数为该数在该行最大在该列最小`

```c
#include<stdio.h>
int main(){
    int arr[3][4] = { {1, 2, 6, 4}, {5, 6, 7, 8}, {9, 10, 11, 9} };

    for(int i = 0; i < 3; i++){
        int max = arr[i][0];
        int imax = 0;
        for(int j = 0; j < 4; j++){     
            max = max > arr[i][j] ? max : arr[i][j];
            imax = max == arr[i][j] ? j : imax;
        }

        int min = arr[0][imax];
        for(int j = 0; j < 3; j++){
            if(min > arr[j][imax]){
                min=arr[j][imax];
            }
        }

        if(min == max){
            printf("%d %d %d",max, i + 1, imax + 1);
        }
    }
}
```


```c
#include<stdio.h>
#include<string.h>

int i(int n1, int n2, int n3){
    return n1 + n2 == n3;
}

int main(){

    int n1 = 10, n2 = 20, n3 = 30;
    int i1 = i(n1, n2, n3);
    if(i1){
        puts("YES");
    }else{
        puts("NO");
    }
}
```

```c
#include<stdio.h>

int n(int n1){
    int cnt = 0;
    do{
        if(n1 % 2){
            cnt++;
        }
    }while(n1 = n1 >> 1);
    return cnt;
}

int main(){
    int n1 = 7;
    int cnt = n(n1);
    printf("%d",cnt);
}
```

```c
#include<stdio.h>

int main(){
    int a = 1;

    int* p = &a;

    a = 20;
    printf("a is %d\n",a);
    printf("a is %d\n",a);
    printf("p is %p\n",p);
    *p=30;

    printf("a is %d\n",a);
    printf("&a is %p\n",&a);
    printf("p is %p\n",p);

    printf("%p\n",p);
}
```

```c
#include<stdio.h>
int main(){
    float fn1 = 1.1;
    float *q = &fn1;
    *q = 3.14;
    printf("%d %d\n",fn1, *q); --%f
}
```

```c
#include<stdio.h>
int main(){
    int arr[5] = {};

    int *p = arr;

    for(int i = 0; i < 5; i++){
        scanf("%d",p);
        printf("%d ",*p);
        p++;
    }
    return 0;
}


在C语言中，使用变量来定义数组的大小是不允许的，这是因为在C标准中，数组的大小必须在编译时是已知的常量表达式。在你的例子中，M 是一个变量，它的值在运行时才确定，因此不能用它来定义数组 a 的大小。

c
int M = 9;  
int a[M];  // 这是不合法的，因为M是一个变量，不是编译时常量
从C99标准开始，C语言支持变长数组，这意味着你可以使用变量来定义数组的大小，但这个变量必须在数组定义的作用域内是已知的。
c
void func() {  
    int M = 9;  
    int a[M];  // 在C99及更高版本中，这是合法的  
    // 使用数组a...  
}
但是，请注意，变长数组的使用有一些限制和潜在的陷阱，特别是在嵌套函数或大型数组的情况下，因为它们可能导致栈溢出。因此，在使用变长数组时要特别小心。

```c
#include<stdio.h>
float mavg(float *p, int size){
    float sum = 0;
    float avg = 0;

    for(int i = 0; i < size; i++){
        sum += *(p+i);
    }

    return avg = sum * 1.0 / size;
}

int main(){
    float arr[5] = {60, 70, 80, 90, 100};
    int size = sizeof(arr) / sizeof(arr[0]);
    float avg = mavg(arr,size);
    printf("%f\n", avg);
}
```

输出的时候一定看好数据类型 否则可能为错误的数据

```c
#include<stdio.h>

int mstrlen(char *p){
    int i = 0;
    for(i = 0; *p != 0; i++){
        p++;
    }
    return i;
}

int main(){
    char arr[100] = "";
    gets(arr);
    printf("%d\n",mstrlen(arr));
}