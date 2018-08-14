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

### BOM对象有哪些，列举window对象？

```
1、window对象 ，是JS的最顶层对象，其他的BOM对象都是window对象的属性；

2、document对象，文档对象；

3、location对象，浏览器当前URL信息；

4、navigator对象，浏览器本身信息；

5、screen对象，客户端屏幕信息；

6、history对象，浏览器访问历史信息

```
#           BOM概念：browser object model

常用对象

### Window：窗口，浏览器的窗口
```
我们定义的全局变量和全局函数都是window对象的属性和方法。

var a = 1;
function test(){
    var a = 2;
    alert(a);
    alert(window.a);
}

全局变量是window的属性

全局函数是window的方法

窗口body的宽度：window.innerWidth

窗口body的宽度：window.innerHeight

常用的方法：open：打开一个新的窗口。要传入三个参数（第一个：将要打开浏览器的路径；第二个：打开的方式；第三个：对于新打开的浏览器的描述（宽和高等））

myWindow =window.open("http://www.baidu.com","_blank","width = 200,height = 300");

close：关闭一个窗口。

mywindow.close();

moveTo：移动一个窗口。以窗口的左上角为坐标起点，但是新窗口的路径要为空（一般很少用）

focus：使窗口获得焦点

functionremoveWin(){
    //一个窗口的左上角为移动窗口的坐标
    myWindow.moveTo(200,200);
    myWindow.focus();//窗口获得焦点
}

resizeTo：改变新窗口的大小，但是新窗口的路径要为空

functionresizeWin(){
    myWindow.resizeTo(1000,5000);
    myWindow.focus();
}
```
### screen：屏幕 
```
也是window的一个对象，在使用的时候可以用window.screen，也可以把window省略掉。
屏幕的常用属性：宽、高；可用宽、可用高（可用高不包括任务栏）

varscrWidth = window.screen.width;
var scrHeight =screen.height;//window可省略
document.write("屏幕的宽："+ scrWidth + "屏幕的高："+ scrHeight + "</br>");
var scrAvaWidth =screen.availWidth;
var scrAvaHeight =screen.availHeight;
document.write("屏幕的宽："+ scrAvaWidth +"屏幕的高：" + scrAvaHeight +"</br>");
```
### location：地址
```
常用属性：href：完整路径；port：端口号；pathname：路径名；protocol：协议。

varhref = location.href;
document.write("完整的路径:"+ href + "</br>");
var port =location.port;
document.write("端口号:"+ port + "</br>");
var path =location.pathname;
document.write("路径名:"+ path + "</br>");
var pro =location.protocol;
document.write("协议:"+ pro + "</br>");

常用方法：

打开一个新的路径（窗口）

location.assign("http://www.runoob.com");

刷新：普通刷新和强制刷新

//普通刷新
function reloadDoc(){
    location.reload();//如果传值为true，那么就是强制刷新
}
```
### history：历史记录
```
记录当前窗口的历史，可以进行页面的转换

back：返回上一页

forward：进入下一页

<body>
<button onclick="goBack()">返回上一页</button>
<button onclick="goForward()">进入下一页</button>
<button onclick="newDoc()">新的页面</button>
</body>
<script>
    functiongoBack(){
        history.back();
    }
    functiongoForward(){
        history.forward();
    }
    functionnewDoc(){
        location.assign("http://www.runoob.com");
    }
</script>

go：进入确定的哪一页（-1时是返回上一个页面，1为下一个页面）

history.back();

history.forward();

history.go(-1);             
```               
# Math对象 
```
 Math.max();获取参数中最大的一个
 var a=Math.max(1,2,3,4)
 alert(a)4
 Math.min();获取参数中最小的一个
 var a=Math.min(1,2,3,4)
 alert(a)1
 Math.ceil();向上取整
 var a=Math.ceil(0.1);
 alert(a)  1
 Math.floor();向下取整
 var a=Math.floor(9.99);
 alert(a) 9
 Math.round()；四舍五入
 var a=Math.round(0.49);
 alert(a)
 Math.random();随机数 [0,1)

  Math.random()*(m-n)+n

  Math.abs():取绝对值
  Math.PI  圆周率
```          
# 定时器
```
 超时定时器  间歇定时器

    间歇性   
    var num=0;
    var a=setInterval(function(){
        num++;
        if(num==5){
            clearInterval(a);
            //定时器 关闭后  一定要销毁 （提高性能）
            a=null;
        }
        console.log('hello world')
    },1000);


   超时定时器

   var b=setTimeout(function(){
       console.log('hello world')
   },1000)

   clearTimeout(b);

   b=null;
```

# 日期
```
var times=new Date();
    console.log(times);
    //获取日期对象中的年份
    var year=times.getFullYear();
    console.log(year);
    //获取日期对象中的月份  0-11  
    var month=times.getMonth()+1;
    console.log(month);
    //获取日期对象中的日  
    var day=times.getDate();
    console.log(day);
    var hour=times.getHours();
    console.log(hour);
    //获取日期对象中的分钟
    var minute=times.getMinutes();
    console.log(minute);
    //获取日期对象中的秒
    var second=times.getSeconds();
```

# DOM

```
// 获取元素  四种方式   id  class   name   tagname

//id   单个元素
var oBox=document.getElementById('box');

//   class   获取到多个元素  [ul.list]

var oList=document.getElementsByClassName('list');

//  name    不常用  一般来获取form表单元素 [input]
var oTxt=document.getElementsByName('user');

//tagname(标签名)   获取到一组元素 [div,div,div]
var oDiv=document.getElementsByTagName('div');


// 获取元素的内容  (包括标签)
  var text=oBox.innerHTML;
  var t=oBox.innerText; // 只获取文本 不包含标签
  
  setAttribute('align','center');//设置属性和值
  setAttribute('bbb','ccc');//设置自定义的属性和值
  removeAttribute('style');//移除属性
  
  1.node节点属性
节点可以分为元素节点、属性节点和文本节点，而这些节点又有三个非常有用的属性，分别为：nodeName、nodeType和nodeValue=

节点类型	nodeName	nodeType	nodeValue
元素	SPAN	         1	         null
属性	属性名称id	2	     属性值box
文本	#text          3	       文本内容(不包含html)
注释	#comment	   8	       注释的内容

  属性	说明
childNodes	获取当前元素节点的所有子节点
children  // 获取所有的非空白节点
firstChild	获取当前元素节点的第一个子节点  相当于childNodes[0]
firstElementChild   获取第一个元素
lastChild	获取当前元素节点的最后一个子节点  相当于childNodes[box.childNodes.length - 1]
lastElementChild  获取最后一个元素节点
parentNode	获取当前节点的父节点
previousSibling	获取当前节点的前一个同级节点  previousElementSibling
nextSibling	获取当前节点的后一个同级节点       nextElementSibling
attributes	获取当前元素节点的所有属性节点集合
getAttributeNode('id') 获取单个属性节点
```
# DOM不单单可以查找节点，也可以创建节点、复制节点、插入节点、删除节点和替换节点。

```
方法	说明
write()	     这个方法可以把任意字符串插入到文档中
createElement()	创建一个元素节点
appendChild()	将新节点追加到子节点列表的末尾
createTextNode()	创建一个文件节点
insertBefore()	将新节点插入在前面
repalceChild()	将新节点替换旧节点
cloneNode()	      复制节点
removeChild()	移除节点



1.write()方法
write()方法可以把任意字符串插入到文档中去。
document.write('<p>这是一个段落！</p>')'	;	//输出任意字符串

2.createElement()方法
createElement()方法可以创建一个元素节点。
document.createElement('p');					//创建一个元素节点

3.appendChild()方法
appendChild()方法讲一个新节点添加到某个节点的子节点列表的末尾上。
	var box = document.getElementById('box');		//获取某一个元素节点
	var p = document.createElement('p');			//创建一个新元素节点<p>
	box.appendChild(p);						//把新元素节点<p>添加子节点末尾

4.createTextNode()方法
createTextNode()方法创建一个文本节点。
	var text = document.createTextNode('段落');		//创建一个文本节点
	p.appendChild(text);						//将文本节点添加到子节点末尾
5.insertBefore()方法
insertBefore()方法可以把节点创建到指定节点的前面。
box.parentNode.insertBefore(p, box);			//把<div>之前创建一个节点
PS：insertBefore()方法可以给当前元素的前面创建一个节点，但却没有提供给当前元素的后面创建一个节点。那么，我们可以用已有的知识创建一个insertAfter()函数。
function insertAfter(newElement, targetElement) {
//得到父节点
	var parent = targetElement.parentNode;		
//如果最后一个子节点是当前元素，那么直接添加即可	
	if (parent.lastChild === targetElement) {
		parent.appendChild(newElement);
	} else {
//否则，在当前节点的下一个节点之前添加
		parent.insertBefore(newElement, targetElement.nextSibling);
	}
}
PS：createElement在创建一般元素节点的时候，浏览器的兼容性都还比较好。但在几个特殊标签上，比如iframe、input中的radio和checkbox、button元素中，可能会在IE6,7以下的浏览器存在一些不兼容。
	var input = null;
	if (BrowserDetect.browser == 'Internet Explorer' && BrowserDetect.version <= 7) {
//判断IE6,7，使用字符串的方式
		input = document.createElement("<input type=\"radio\" name=\"sex\">");
	} else {
//标准浏览器，使用标准方式
		input = document.createElement('input');
		input.setAttribute('type', 'radio');
		input.setAttribute('name', 'sex');
	}
	document.getElementsByTagName('body')[0].appendChild(input);

6.repalceChild()方法
replaceChild()方法可以把节点替换成指定的节点。
box.parentNode.replaceChild(p,box);			//把<div>换成了<p>

7.cloneNode()方法
cloneNode()方法可以把子节点复制出来。
	var box = document.getElementById('box');		
	var clone = box.firstChild.cloneNode(true);		//获取第一个子节点，true表示复制内容
	box.appendChild(clone);						//添加到子节点列表末尾
8.removeChild()方法
removeChild()方法可以把
box.parentNode.removeChild(box);			//删除指定节点
```
# 事件
```

一、事件流的定义


页面触发一个事件时，会按照一定的顺序来响应事件，事件的响应过程为事件流
就我个人理解就是网页对点击事件的排序顺序就是事件流


二、事件流的分类


1、冒泡型的事件流（任何一款浏览器都支持）


从明确事件源到不明确的事件源依次向上响应。


2、捕获型的事件流（从IE8及以下版本支持）


从不确定事件源到确定事件源依次向下响应。


对象。addEventListener（事件，事件处理程序，false）


	false：冒泡型事件流


	true：捕获型事件流


三、阻止事件流（适合用于冒泡型）


		ie：事件对象.cancelBubble=true；


		FF：事件对象.stopPropagation（）；


阻止浏览器的默认行为


	IE：e.returnValue=false；

	FF：e.preventDefault（）；

阻止事件的默认行为：

return false

四、事件委派（事件委托）

把子容器要绑定到事件，委托给共同的父容器，执行时再交给子容器。

	FF：e.target 获取目标事件源

	IE：e.srcElement

运用冒泡型的事件流实现了


子元素比较多，而且事件相同的情况下，使用



Event对象的一些兼容性写法
获得event对象兼容性写法 
event || (event = window.event);
获得target兼容型写法 
event.target||event.srcElement
阻止浏览器默认行为兼容性写法 
event.preventDefault ? event.preventDefault() : (event.returnValue = false);
阻止冒泡写法 
event.stopPropagation ? event.stopPropagation() : (event.cancelBubble = true);
```



# 事件对象属性

```
  x   x坐标    距左边界的距离       IE中距父级容器左边界的距离


            y   y坐标    距上边界的距离       IE中距父级容器上边界的距离


            clientX      距左边界的距离


            clientY      距上边界的距离


            screenX      距屏幕左边界的距离


            screenY      距屏幕上边界的距离


            pageX        距左边界的距离       IE8不支持


            pageY        距上边界的距离       IE8不支持

```
                  

