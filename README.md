### js的组成部分:
      > ECMAScript (核心)
      > DOM( 文档对象模型)
      > BOM(浏览器对象模型)

    * 数据类型：
       1. 基本数据类型： Number（数字）、String(字符串)、Boolean(布尔)、Undefined(未定义)、Null(空)。

       2. 引用数据类型： Object(对象)
                      Object(对象)、Array(数组)、Function(函数)、Date(时间)、RegExp(正则表达式)

### 变量的命名法则：
         1. 严格区分大小写
         2. 只能由 字母、数字、下划线_ 、$组成
         3. 不可以数字开头
         4. 不可以是关键字、保留字
         5. 遵循驼峰命名法（除首单词外，其与单词首字符都要大写） var myBook=5;


         * 关键字：具有特殊含义的量
         * 保留字：将来可能成为关键字

### js里输出的几种方式：
         1. 控制台输出  console.log( )  console.dir()
         2. alert("123")  弹出
         3. document.write("666") 页面输出
         
### Number
     Number 类型： 整数    小数    NaN  (not a number)

      整数：  进制  （二进制、八进制、十进制、十六进制）

      二进制：0为前导 ，后导为0-1

      八进制：0为前导，后导0-7

      十六进制：0x前导，后导是0-9，A-F
      
      
       var a=071;
     var b=parseInt(71,8);//将71（八进制）转换成10进制
     console.log(b);

     var c=57;
     var d=c.toString(8);//将十进制转换成8进制
     console.log(d);
     console.log(0.2e5);//0.2*10^5=20000
     console.log(0.45e-4);// 0.45*10^-4 =0.000045

     NaN:其他数据类型转换成Number类型，转换失败返回NaN.

     Number();将任意数据类型转换成Number类型；
             1， true--->1   false---->0
             2,   10----->10
             3,   null--->0
             4, undefined--->NaN
             5,   <1>  如果字符串只包含数字 ，直接返回数字
                   <2> 如果有前导0，则0被忽略
                   <3> 空字符串 -----> 0
                    <4> 三种以外 转换成NaN.

       parseInt(); 字符取整
             1，不包含数字的值，都转换成NaN
             2,  <1> 整数直接输出
                 <2> 小数，输出整数部分
                 <3> 前导有0，则删除0
                 <4> 提取前面有效整数部分

       parseFloat(); 字符串取 整数和小数

     isNaN();   is not a number?    是 不是一个数？  true/false
     如果是一个数或者通过Number（）转换成一个数 则返回 false 否则返回true
     
   ### Boolean   有两个值  true  false


    typeof a  返回a的数据类型

    Boolean();将其他数据类型转换成Boolean类型
         数据类型     转换成false的值
    <1>  Number          0/NaN
    <2>  String           ""
    <3>  Undefined        undefined
    <4>  Null             null
    <5> Boolean           false

    Boolean()转换引用数据类型 都转换成true

，

   ### Undefined 只有一个值 undefined  , 只声明不赋值       var a;


   ### Null  只有一个值null, typeof null==object


    null==undefined

   ### String: 字符串必须被引号包裹

    String();把其他数据类型转换层字符串类型


    a.toString(); a不可以是null 和undefined


   字符串有length属性，表示字符串长度

   字符串可以通过下标获取相应的字符
   
  ### 一元运算：
    var b=a++: 加号在后面，先把a赋值给b,在对a进行 +1操作
    var a=100;
    var b=a++;// b=a; a=a+1
    console.log(a);//101
    console.log(b);//100


    var b=++a;加号在前面，先对a进行+1操作，再把a赋值给b
    var a=100;
    var b=++a;// a=a+1;  b=a;
    console.log(a);//101
    console.log(b);//101


   ### 算数运算：
    加法：
    1> 字符串加法就是拼接
    2> 如果不是Number 类型参加运算，首先调用Number方法转换成Number再进行运算
    3>任何数于NaN参加运算，结果都是NaN
       console.log(100+"hello"); //"100hello"
    减法：
    1> 如果不是Number 类型参加运算，首先调用Number方法转换成Number再进行运算
    2>任何数于NaN参加运算，结果都是NaN
    console.log("您的年龄是："-20);//NaN
    console.log(true-10);//-9  Number(true)
    console.log(null-false);//0
    console.log(undefined-null);//NaN
    console.log(undefined-"true");//NaN
    console.log(false-"0");//0
    console.log(""-NaN);//NaN
    console.log(null-"false"-NaN);//0-NaN-NaN=NaN
    乘法：
    1> 如果不是Number 类型参加运算，首先调用Number方法转换成Number再进行运算
    2>任何数于NaN参加运算，结果都是NaN
    除法：
    1> 如果不是Number 类型参加运算，首先调用Number方法转换成Number再进行运算
    2>任何数于NaN参加运算，结果都是NaN

    取余：
    1> 如果不是Number 类型参加运算，首先调用Number方法转换成Number再进行运算
    2>任何数于NaN参加运算，结果都是NaN
    var a=100%3;//1   把100除以3的余数赋值给a
    console.log(a)


   ### 关系运算：
    >、<、<=、>=、==、！=、===、！==

    1.两边都是Number ,直接比较大小
    2.有一边不是Number ,则转换成Number再进行比较
    console.log(null==0);//  false null不会调用Number转换
    console.log(null==undefined);//  true
    console.log(NaN==NaN);//  false
    3.两边都是字符串，比较首字符字符编码的大写
    4.任何值与NaN进行比较，都是false

    console.log("1"==1);//  true
    console.log("1"===1);//false
    console.log("1"!==1);//true
    console.log("1"!=1);//false




   ### 逻辑运算：
      逻辑与    条件1 && 条件2   ；  逻辑或：     条件1 || 条件2      逻辑非 ： ！条件

      逻辑与：
      先把第一个值转换成布尔值
    1.	第一个为true，则返回第二个值
    2.	第一个为false,则返回第一个值


    逻辑或：

    先把第一个值转换成布尔值
    1.第一个值为true,返回第一个值
    2.第一个值为false,返回第二个值

    逻辑非：！

      先对非号右边部分进行布尔转换，在取反

    逻辑非非：！！

     非号有边的部分，取反再取反


   ### 赋值运算：

     三元运算（三目运算）

    条件？ 语句1：语句2；
   if(5>4){alert("对")}else {alert("错")}

    5<4?alert("对"):alert("错");


    运算优先级；
     1. 一元运算 ：  ++  --   ！
     2.* / %
     3.+ -
     4.< <= > >=  == != === !==
     5. &&  ||
     6.=

