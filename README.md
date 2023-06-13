# C-p20-C-2-
C语言学习笔记 p20 C语言操作符详解(2)
#include<stdio.h>
int main()
{
    int a=0;
    char b='w';
    int arr[10]={0};
    printf("%d\n",sizeof(a));//这个变量的括号可以省略，但变量类型的括号不可以省略
    printf("%d\n",sizeof(int));
    
    printf("%d\n",sizeof(b));
    printf("%d\n",sizeof(char));

    printf("%d\n",sizeof(arr));//10*4=40
    printf("%d\n",sizeof(int [10]));
    return 0;
}

int main()
{
    short s=0;
    int a=10;
    printf("%d\n",sizeof(s=a+5));//这个表达式的输出取决于s的大小
    printf("%d\n",s);//sizeof内部的东西不参与运算，所以这行代码输出为0
    return 0;
}

//～这个符号的意思是：对一个数的二进制按位取反
int main()
{
    int a=0;
    //~按二进制位取反
    //00000000000000000000000000000000（0的二进制序列）
    //11111111111111111111111111111111-补码
    //00000000000000000000000000000001-原码，输出为-1
    printf("%d\n",~a);
    return 0;
}

int main()
{
    int a=11;
    a=a|(1<<2);
    printf("%d\n",a);
    a=a&(~(1<<2));//11
    //00000000000000000000000000001011
    //00000000000000000000000000000100(或这个值目的是将上一行代码两个1之间的那个0变成1）
    //1<<2
    //00000000000000000000000000000001（拿1左移两位得出47行的值）
    return 0;
}

int main()
{
    int a=(int)3.14//强制类型转换
    return 0;
}

int main()
{
    
    return 0;
}

//逻辑操作符
//&&逻辑与
//｜｜逻辑或
int main()
{
    int a=3;
    int b=5;
    int c=a&&b;
    printf("%d\n",c);//输出1，但只要有一个为假则为假
    return 0;
}

int main()
{
    int a=0;
    int b=5;
    int c=a||b;
    printf("%d\n",c);//输出1，一个为真则为真
    return 0;
}

int main()
{
    int i=0,a=0,b=2,c=3,d=4;
    i=a++&&++b&&d++;
    printf("a=%d\n b=%d\n c=%d\n d=%d\n",a,b,c,d);
    return 0;
}//输出为1，2，3，4，因为逻辑与只要左边为假，则后面通通不计算

int main()
{
    int i=0,a=0,b=2,c=3,d=4;
    i=a++｜｜++b｜｜d++;
    printf("a=%d\n b=%d\n c=%d\n d=%d\n",a,b,c,d);
    return 0;
}//2，2，3，4，只要有一个为真，后面的也不需要计算

//条件操作符
//三目操作符
//exp1？exp2:exp3  这句话的意思是，表达式1为真，表达式要算，表达式2是整个表达式的结果，为假则算表达式3，表达式3为整个表达式的结果
int main()
{
    int a=0;
    int b=0;
    if(a>5)
        b=3;
    else
        b=-3;
    b=(a>5?3:-3);
    return 0;
}

int main()
{
    int a=10;
    int b=20;
    int max=0;
    
    if(a>b)
        max=a;
    else
        max=b;
    max=(a>b?a:b);
    return 0;
}

//逗号表达式
//用逗号隔开表达多个表达式，从左向右依次执行，整个表达式的结果是最后一个表达式的结果
int main()
{
    int a=1;
    int b=2;
    int c=(a>b,a=b+10,a,b=a+1);
    return 0;
}//输出为13

int main()
{
    a=get_val();
    count_val(a);
    while(a>0)
    {
        a=get_val();
        count_val(a);
    }
    return 0;
}//这样写代码比较啰嗦，可以用逗号表达式来简化
int main()
{
    while(a=get_val(),count_val(a),a>0)
    {
        
    }
    return 0;
}















