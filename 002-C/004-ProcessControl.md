`条件语句 IF`
--

```c
1、if(){...}

2、if(){...}else(){...}

3、if(){...}else if(){...}

4、if(){...}else if(){...}else{...}
```

`输入一个 int 数 是不是偶数 如果是那么它的一半是不是整数`

```c
#include<stdio.h>
int main(){
    int v1 = 0;
    scanf("%d",&v1);
    if(v1 % 2 == 0){
        printf("YES");
    }else{
        printf("NO");
        return 0;
    }
    if( (v1 / 2) % 2 == 0){
        printf("HALF is YES");
    }else{
        printf("HALF is NO");
    }
    return 0;
}
```

```c
#include<stdio.h>
int main(){
    int v = 2;
    if( 1 < v <3){ -- 1<2 1 1<3 
        printf("YES")
    }else{
        printf("NO")
    }
    return 0;
}
```

`三个数求最值`

```c
#include<stdio.h>
int main() {
    int a=0,b=0,c=0,max=0;
    scanf("%d%d%d",&a,&b,&c);
    max=a;
    if(max<b) {
        max=b;
    }
    if(max<c) {
        max=c;
    }
    printf("%d\n",max);
    return 0;
}
```

`三角形两边之和大于第三边`

```c
#include<stdio.h>
int main(){
    int v1 = 0, v2 = 0, v3 = 0, max = 0;
    scanf("%d%d%d",&v1,&v2,&v3);

    max = v1;
    max = v1 < v2 ? v2 : v1;
    max = max < v3 ? v3 : max;

    if(v1 + v2 + v3 - max - max > 0){
        printf("YES");
    }
    return 0;
}
```

`输入小时分钟和秒以空格分隔 1 秒后的时间是`

```c
#include <stdio.h>  
int main() {  
    int v1 = 0, v2 = 0, v3 = 0;  
    printf("请输入小时分钟和秒以空格分隔：");  
    scanf("%d %d %d", &v1, &v2, &v3);  
    if( v1 < 0 || v1 > 23 || v2 < 0 || v2 > 59 || v3 < 0 || v3 > 59){
        printf("Error");
        return 0;
    }
    v3 += 1;
    if (v3 == 60) {  
        v3 = 0;  
        v2 += 1;  
    }  
    if (v2 == 60) {  
        v2 = 0;  
        v1 += 1;  
    }  
    if (v1 == 24) {  
        v1 = 0;  
    }  
    printf("1 秒后的时间是: %02d:%02d:%02d\n", v1, v2, v3);  
    return 0;  
}
```

`条件分支语句 Switch`
--

```c
switch(已知条件){ --不能浮点数
    case 常量表达式 1:
        ...
        break; --无 break 穿透
    case 常量表达式 2: --不能与前面相同否则报错
        ...
        break;
    default: --无匹配项执行 如果前一个 case 无 break 则也执行
        ...
        break;
}
```

`季节`

```c
#include<stdio.h>
int main(){
    int v = 0;
    scanf("%d",&v)
    switch(v){
        case 3: case 4: case 5:
            printf("春天");
            break;
        case 6: case 7: case 8:
            printf("夏天");
            break;
        case 9: case 10: case 11:
            printf("秋天");
            break;
        case 12: case 1: case 2:
            printf("冬天");
            break;
        default:
            printf("Please input 1~12");
            break;
    }
}
```

`分数等级`

```c
#include<stdio.h>
int main(){
    int v = 0;
    scanf("%d",&v);

    switch(v / 10){
        case 10: case 9:
            printf("A");
            break;
        case 8:
            printf("B");
            break;        
        case 7:
            printf("C");
            break;        
        case 6:
            printf("D");
            break;   
        default:
            printf("不及格");
            break;
    }
    return 0;
}
```

`循环语句 while`
--

```c
定义初始变量
while(表达式){
    ...
    改变初始值
}
```

`! 最小公倍数 最大公约数`

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
  
--计算最大公约数的函数欧几里得算法
int gcd(int a, int b) {  
    while (b != 0) {  
        int temp = b;  
        b = a % b;  
        a = temp;  
    }  
    return a;  
}  
  
--计算最小公倍数的函数  
int lcm(int a, int b, int gcd_value) {  
    return (a / gcd_value) * b;  
}
```

`循环语句 do while`
--

```c
定义初始变量
do{
    ...
    改变初始值
} while(表达式)
```

`循环语句 for` 
--

`嵌套外层控行内层控列` `全部表达式了省略`

```c
for(定义初始变量；条件判断；改变初始值){
    ...
}
```

`! 9 x 9`

```c
#include<stdio.h>
int main()
{
	int i,j;
	for(i=1;i<=9;i++)
	{
		for(j=1;j<=i;j++){
			printf("%d*%d=%d\t",j,i,i*j);
        }
		printf("\n");
	}
	return 0;
}
```

`! 根据输入行数打印金字塔`

```c
#include <stdio.h>  
  
int main() {  
    int row, i, j, space, star;  
  
    printf("请输入金字塔的行数: ");  
    scanf("%d", &row);  
  
    for (i = 1; i <= row; i++) {   

        space = row - i;  
        for (j = 1; j <= space; j++) {  
            printf(" ");  
        }  
  
        star = 2 * i - 1;  
        for (j = 1; j <= star; j++) {  
            printf("*");  
        }  
  
        printf("\n");  
    }  
  
    return 0;  
}
```

`! 阶乘累加和`

```c
#include <stdio.h>  
   
unsigned long long factorial(int num);  
  
int main() {  
    int n;  
    unsigned long long sum = 0;

    printf("请输入一个正整数: ");  
    scanf("%d", &n);  
 
    if (n < 0) {  
        printf("错误：输入必须是正整数\n");  
        return 1;
    }  
  
    for (int i = 1; i <= n; i++) {  
        sum += factorial(i);  
    }  
  
    printf("%d的阶乘累加和是: %llu\n", n, sum);  
  
    return 0; 
}  
  
unsigned long long factorial(int num) {  
    unsigned long long result = 1;  
    for (int i = 1; i <= num; i++) {  
        result *= i;  
    }  
    return result;  
}
```

`Break Continue`
--

`> break`

`break 关键字用于立即终止循环 并跳出循环体 当程序执行到 break语句时 循环将立即终止 不再执行循环体内未执行的语句 然后程序将继续执行循环后面的代码 break 通常用在循环体内遇到满足某个条件时需要提前终止循环的情况` 

`> continue`

`continue 关键字用于跳过当前循环的剩余代码 继续执行下一次循环 当程序执行到 continue 语句时 将直接跳到循环条件判断处 继续下一次循环的执行 continue 通常用在循环体内遇到某个条件需要跳过当前循环的剩余代码时`

```c
#include<stdio.h>
int main(){
    int i = 0, sum = 0;
	while(i <= 100){
		if(i++ == 90){	
			continue;
		}
		sum+=i;
	}
    printf("%d",sum);
    return 0;
} --5060 没加 91 加 101 了
```

`输入一个不多于 5 位的正整数 位数 逆序数`

```c
#include <stdio.h>  
  
int main() {  
    int v1, rev = 0, occas, cnt = 0;  
   
    printf("请输入一个不多于 5 位的正整数: ");  
    scanf("%d", &v1);  
  
    if (v1 <= 0 || v1 > 99999) {  
        printf("输入的数字不合法 请输入一个不多于 5 位的正整数\n");  
        return 1;  
    }  
  
    occas = v1;  
    while (occas != 0) {  
        occas /= 10;  
        cnt++;  
    }  

    occas = v1;  
    while (occas != 0) {  
        int digit = occas % 10;  
        rev = rev * 10 + digit;
        occas /= 10;  
    }  
  
    printf("位数: %d 逆序数: %d\n", cnt, rev);  
  
    return 0;  
}
