---
title: 如何写出C-Style的代码
date: 2018-07-28 23:00:07
tags:
    - C
    - C++
categories: skills
---
了解过Python的人大都知道代码要想写得Pythonic，是要遵循许多规则的。但对于C/C++来说，显然没听说过什么Cic或Cppic之类的东西（@_@？）但是，C系的语言也是有着其独特的代码风格的，总结了一些典型的基础风格供大家参考，学习。
<!--more-->
## Function writing style

### 1、每一个函数都必须有注释，即使函数短到可能只有几行。头部说明需要包含包含的内容和次序如下：
```
/************************************************************************
* Function Name : nucFindThread
* Create Date : 2000/01/07
* Author/Corporation : your name/your company name
**
Description : Find a proper thread in thread array.
* If it’s a new then search an empty.
*
* Param : ThreadNo： someParam description
* ThreadStatus： someParam description
**
Return Code : Return Code description,eg:
ERROR_Fail: not find a thread
ERROR_SUCCEED: found
*
* Global Variable : DISP_wuiSegmentAppID
* File Static Variable : naucThreadNo
* Function Static Variable : None
*
*------------------------------------------------------------------------
* Revision History
* No. Date Revised by Item Description
* V0.5 2008/01/07 your name … …
************************************************************************/
static unsigned char nucFindThread(unsigned char ThreadNo,unsigned char ThreadStatus)
{
…
   }
```

### 2、每个函数定义结束之后以及每个文件结束之后都要加一个或若干个空行。例如：
```
/************************************************************************
* ………
* Function1 Description
* ………
************************************************************************/
void Function1(……)
{
   …
}
//Blank Line
/************************************************************************
* ………
* Function2 Description
* ………
************************************************************************/
void Function2(……)
{
   …
}
//Blank Line
/************************************************************************
* ………
* Function3 Description
* ………
************************************************************************/
void Function3(……)
{
   …
}
//Blank Line
```

### 3、在一个函数体内，变量定义与函数语句之间要加空行。例如：
```
/************************************************************************
* ………
* Function Description
*………
************************************************************************/
void Function1()
{
   int n;
   //Blank Line
   statement1
   …….
}
```

### 4、逻揖上密切相关的语句之间不加空行，其它地方应加空行分隔。例如：
```
//Blank Line
while (condition)
{
   statement1;
   //Blank Line
   if (condition)
   {
      statement2;
   }
   else
   {
      statement3;
   }
   //Blank Line
   statement4
}
```

### 5、复杂的函数中，在分支语句，循环语句结束之后需要适当的注释，方便区分各分支或循环体。
```
while (condition)
{
   statement1;
   if (condition)
   {
      for(condition)
      {
         Statement2;
      }//end “for(condition)”
   }
   else
   {
      statement3;
   }//”end if (condition)”
   statement4
}//end “while (condition)”
```

### 6、修改别人代码的时候不要轻易删除别人的代码，应该用适当的注释方式。例如：
```
while (condition)
{
   statement1;
   //////////////////////////////////////
   //your name , 2008/01/07 delete
   //if (condition)
   //{
   // for(condition)
   // {
   // Statement2;
   // }
   //}
   //else
   //{
   // statement3;
   //}
   ////////////////////////////////////////
   ///////////////////////////////////////
   // your name , 2000/01/07 add
   …
   new code
   …
   ///////////////////////////////////////
   statement4
}
```

### 7、用缩行显示程序结构，使排版整齐，缩进量统一使用4个字符（不使用TAB缩进）。
每个编辑器的TAB键定义的空格数不一致，可能导致在别的编辑器打开你的代码乱成一团糟。

### 8、在函数体的开始、结构/联合的定义、枚举的定义以及循环、判断等语句中的代码都要采用缩行。

### 9、同层次的代码在同层次的缩进层上。例如：
<table>    <tr>        <th>提倡的风格</th>        <th>不提倡的风格</th>    </tr>    <tr>        <td>            <pre>
            void Function(int x)
            {
                //program code
            }            </pre>        </td>        <td>            <pre>
            void Function(int x)
            {
            //program code
            }            </pre>        </td>    </tr>    <tr>        <td>            <pre>
            struct tagMyStruct
            {
                int a;
                int b;
                int c;
            };            </pre>        </td>        <td>            <pre>
            struct tagMyStruct{
            int a;
            int b;
            int c;
            };            </pre>        </td>    </tr>    <tr>        <td>            <pre>
            if(condition)
            {
                //program code
            }
            else
            {
                //program code
            }            </pre>        </td>        <td>            <pre>
            if(condition){
            //program code
            }else{
            //program code
            }            </pre>        </td>    </tr></table>

### 10、代码行最大长度宜控制在80 个字符以内，较长的语句、表达式等要分成多行书写。

### 11、长表达式要在低优先级操作符处划分新行，操作符放在新行之首（以便突出操作符）。拆分出的新行要进行适当的缩进，使排版整齐，语句可读。例如：
```
if ((very_longer_variable1 >= very_longer_variable12)
&& (very_longer_variable3 <= very_longer_variable14)
&& (very_longer_variable5 <= very_longer_variable16))
{
   dosomething();
}
for (very_longer_initialization;
very_longer_condition;
very_longer_update)
{
   dosomething();
}
```

### 12、如果函数中的参数较长，则要进行适当的划分。例如：
```
void function(float very_longer_var1,
float very_longer_var2,
float very_longer_var3)
```

### 13、用正确的反义词组命名具有互斥意义的变量或相反动作的函数等。例如：
```
int aiMinValue;
int aiMaxValue;
int niSet_Value(…);
int niGet_Value(…);
```

### 14、如果代码行中的运算符比较多，用括号确定表达式的操作顺序，避免使用默认的优先级。例如：
```
leap_year = ((year % 4 == 0) && (year % 100 != 0)) || (year % 400 == 0)；
```

### 15、不要编写太复杂的复合表达式。例如：
```
i = a >= b&&c < d && c + f <= g + h; 复合表达式过于复杂
```

### 16、不要有多用途的复合表达式。例如：
```
d = (a = b + c) + r;
```
该表达式既求a 值又求d 值。应该拆分为两个独立的语句：
```
a = b + c;
d = a + r;
```

### 17、尽量避免含有否定运算的条件表达式。例如：
```
if (!(num >= 10))
```
应改为：
```
if (num < 10)
```

### 18、参数的书写要完整，不要贪图省事只写参数的类型而省略参数名字。如果函数没有参数，则用void 填充。例如：

<table>    <tr>        <th>提倡的风格</th>        <th>不提倡的风格</th>    </tr>    <tr>        <td><pre>
            void set_value(int width, int height);
            float get_value(void);        </pre></td>        <td><pre>
            void set_value (int, int);
            float get_value ();        </pre></td>    </tr></table>

## Function parameter style

### 1、原则上尽量少使用全局变量，因为全局变量的生命周期太长，容易出错，也会长时间占用空间。各个源文件负责本身文件的全局变量，同时提供一对对外函数，方便其它函数使用该函数来访问变量。

比如：`niSet_ValueName(...); niGet_ValueName(...);`不要直接读写全局变量，尤其是在多线程编程时，必须使用这种方式，并且对读写操作加锁。

### 2、参数命名要恰当，顺序要合理。

例如编写字符串拷贝函数`str_copy`，它有两个参数。如果把参数名字起为`str1`和`str2`，例如
```
void str_copy (char *str1, char *str2);
```
那么我们很难搞清楚究竟是把`str1`拷贝到`str2`中，还是刚好倒过来。

可以把参数名字起得更有意义，如叫`strSource`和`strDestination`。这样从名字上就可以看出应该把`strSource`拷贝到`strDestination`。

还有一个问题，这两个参数那一个该在前那一个该在后？参数的顺序要遵循程序员的习惯。一般地，应将目的参数放在前面，源参数放在后面。如果将函数声明为：
```
void str_copy (char *strSource, char *strDestination);
```
别人在使用时可能会不假思索地写成如下形式：
```
   char str[20];
   str_copy (str, “Hello World”);
```
参数顺序颠倒

### 3、如果参数是指针，且仅作输入参数用，则应在类型前加const，以防止该指针在函数体内被意外修改。例如：
```
void str_copy (char *strDestination，const char *strSource);
```

### 4、不要省略返回值的类型，如果函数没有返回值，那么应声明为void类型。

如果没有返回值，编译器则默认为函数的返回值是`int`类型的。

### 5、在函数体的“入口处”，对参数的有效性进行检查。

尤其是指针参数，尽量使用`assert`宏做入口校验，而不使用`if`语句校验。

### 6、return 语句不可返回指向“栈内存”的“指针”，因为该内存在函数体结束时被自动销毁。例如：
```
char * Func(void)
{
   char str[30];
   //...
   return str;
}
```
`str`属于局部变量，位于栈内存中，在`Func`结束的时候被释放，所以返回`str`将导致错误。

### 7、函数的功能要单一，不要设计多用途的函数。

微软的Win32 API就是违反本规则的典型，其函数往往因为参数不一样而功能不一，导致很多初学者迷惑。

### 8、函数体的规模要小，尽量控制在80行代码之内。

### 9、相同的输入应当产生相同的输出。尽量避免函数带有“记忆”功能。

带有“记忆”功能的函数，其行为可能是不可预测的，因为它的行为可能取决于某种“记忆状态“。这样的函数既不易理解又不利于测试和维护。在C语言中，函数的`static`局部变量是函数的“记忆”存储器。建议尽量少用`static`局部变量，除非必需。

### 10、避免函数有太多的参数，参数个数尽量控制在4个或4个以内。

如果参数太多，在使用时容易将参数类型或顺序搞错。微软的`Win32 API`就是违反本规则的典型，其函数的参数往往七八个甚至十余个。比如一个`CreateWindow`函数的参数就达11个之多。

### 11、尽量不要使用类型和数目不确定的参数。

C标准库函数`printf`是采用不确定参数的典型代表，其原型为：
```
int printf(const chat *format[, argument]…);
```
这种风格的函数在编译时丧失了严格的类型安全检查。

### 12、有时候函数不需要返回值，但为了增加灵活性如支持链式表达，可以附加返回值。

例如字符串拷贝函数strcpy 的原型：
```
char *strcpy(char *strDest，const char *strSrc);
```
`strcpy`函数将`strSrc`拷贝至输出参数`strDest`中，同时函数的返回值又是`strDest`。这样做并非多此一举，可以获得如下灵活性：
```
char str[20];
int length = strlen(strcpy(str, “Hello World”) );
```

### 13、不仅要检查输入参数的有效性，还要检查通过其它途径进入函数体内的变量的有效性。

例如全局变量、文件句柄等。

### 14、函数名与返回值类型在语义上不可冲突。

违反这条规则的典型代表就是C语言标准库函数`getchar`。几乎没有一部名著没有提到`getchar`函数，因为它实在太经典，太容易让人犯错误了。所以，每一个有经验的作者都会拿这个例子来警示他的读者，我这里也是如此：
```
char c;
c = getchar();
if(EOF == c)
{
   //...
}
```
按照getchar 名字的意思，应该将变量c 定义为char 类型。但是很不幸，getchar 函数的返回值却是int 类型，其原型为：
```
int getchar(void);
```
由于`c`是`char`类型的，取值范围是[-128,127],如果宏`EOF`的值在`char`的取值范围之外，`EOF`的值将无法全部保存到`c`内，会发生截断，将`EOF`值的低8位保存到`c`里。这样`if`语句有可能总是失败。这种潜在的危险，如果不是犯过一次错，肯怕很难发现。
