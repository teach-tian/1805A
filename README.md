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
