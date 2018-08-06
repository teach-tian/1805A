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
     
### 语句：
     if判断语句
      1.单支判断语句  if（添加）语句；
    var box=100;
    if(box>50) {alert("box大于50");alert("hello world")};

     2.双支条件判断语句：
    if(box>50) {alert("box大于50");}else {alert("box不大于50")}

    3.多支条件判断语句：
    var num=75;
    if(num>=90)
    { alert("A级")}
    else if(num>=80)
    {alert("B级")}
    else if(num>=70)
    {alert("C级")}
    else if(num>=60)
    {alert("D级")}
    else {alert("不及格")}

## switch判断语句
    switch(值){
     case 1:
     语句1；
     break;
     case 2:
     语句2；
     break;
     case 3:
     语句3；
     break;
     default:
     语句4；
    }

    while循环语句：  先判断，后执行
    while(循环条件){
       循环语句
    }


    先执行，后判断
    do{
    循环语句
    }while(循环条件)

    for(){}

    */

  //  1+2+3+...+100=?
  var sum=0;
   for(var i=1;i<=100;i++){
       sum+=a;
   }
   console.log(sum);
    console.log(i);//101
// 第一步： var i=1;
    //第二步：i<=100；   如果返回false 循环终止
    //第三步：sum+=a;
    //第四步：i++；  跌代语句
    //第五步：重复二到四步

    // for循环 写出 56---1024  所有整数的和
    var sum=0;

    for(var a=56;a<=1024;a++){
        sum+=a;
    }
    console.log(sum);
  ### 数组方法
    
      1.push() 数组后面添加一项或者多项   方法返回新数组的长度
               参数：一个或多个
      2.pop() 数组的后面删除一项  ， 方法返回最后一项
               参数：0个
      3.unshift()  数组前面添加一项或多项， 方法返回新数组的长度
              参数：一个或多个
      4.shift()数组前面删除一项， 返回第一项
             参数：0个

       5. sort() 数组排序

           参数：function(a,b){return a-b}
           升序：function(a,b){return a-b}
           降序：function(a,b){return b-a}
           
      var arr=['刘子豪','陈浩然','刘博','李永林']

             arr.sort(function (a,b) {return a-b})
             arr.sort(function (a,b) {return b.localeCompare(a)})
             console.log(arr);
             
      6.reverse() 将数组倒叙排列  方法的返回时反正后的数组
              没有参数

      7.concat() 数组的连接    方法返回拼接后的新数组
             原数组不发生改变

      8.slice（） 从原数组中获取子数组
            方法返回 获取到的子数组     原数组不发生改变
        两个参数：
        参数一：开始获取到的位置
        参数二：结束获取的位置（可以）
        9.splice()   数组的增删改查
        方法的返回：删除的项组成的数组
        一个参数：开始删除的位置   表示删除
        二个参数：
                参数一：开始删除的位置
                参数二：删除的个数
        三个参数：表示替换
              参数一：开始删除的位置
              参数二：删除的个数
              参数三：替换的内容
         三个参数以上都表示替换


         10.join()将数组转换成字符串
                  var arr=['刘子豪','陈浩然','刘博','李永林']
                  var a=arr.join("+");
                  console.log(a,arr);
                  
                  
   ### String方法
      
      ```
              charAt()；     查找指定索引对应的字符
              charCodeAt();  查找指定索引对应的Unicode编码
              concat();      字符串拼接  ps:（参数多个）
              var str="hello world";
              var str1="lover";
              var b=str.concat(str1);  //str+str1 
              indexOf();     查找指定字符对应的索引
               ps: 两个参数，第一个参数是要查找的字符
                             第二个参数是开始查找的位置
                    查找不到返回-1
               lastIndexOf()；查找指定字符对应的索引（从后往前）

               substr(); 从原字符串中获取子串
               ps:两个参数 ，第一个参数开始获取的索引
                             第二个参数获取的个数(不传默认获取到最后)

               substring();从原字符串中获取子串
               ps:两个参数 ， 第一个参数开始获取的索引
                              第二个参数结束时的索引(不包括第二个参数)
                slice();从原字符串中获取子串
                ps:两个参数 ， 第一个参数开始获取的索引
                              第二个参数结束时的索引(不包括第二个参数)
                toUpperCase();  小写转换成大写           
                toLowerCase();  大写转换成小写
                split();将字符串以指定字符分割成数组
                var str="hello world!";
                var b=str.split("o");//["hell", "w", "rld!"]
                var str="a";
            var b="b";
            var c=b.localeCompare(b);    //比目标字符小返回 -1
                                         //比目标字符大返回1
            console.log(c);              //和目标字符串相等返回0                 
                  
                  
```
                  
                  
                  
                  
                  
                  
                  
                  
                  
                  
                  
                  
                  
                  
                  
                  
                  
                  
                  
                  
                  
                  
                  
                  
                  

