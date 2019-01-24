
AJAX的全称是Asynchronous JavaScript and XML（异步的 JavaScript 和 XML）。

ajax不是新的编程语言，而是一种使用现有标准的新方法。ajax是与服务器交换数据并更新部分网页的艺术，在不重新加载整个页面的情况下。

ajax是一种在无需重新加载整个网页的情况下，能够更新部分网页的技术。

ajax是一种用于创建快速动态网页的技术。通过在后台与服务器进行少量数据交换。ajax可以使网页实现异步更新。这意味着可以在不重新加载整个网页的情况下，对网页的某部分进行更新。而传统的网页（不使用ajax）如果需要更新内容，必须重载整个网页面。

| 表头 | 表头 | 表头 |
| --- | --- | --- |
|第一行|第一行|第一行|
|第二行|第二行|第二行|
|第三行|第三行|第三行|

```
　　ajax的优点：

　　1、最大的一点是页面无刷新，用户的体验非常好。
　　2、使用异步方式与服务器通信，具有更加迅速的响应能力。。
　　3、可以把以前一些服务器负担的工作转嫁到客户端，利用客户端闲置的能力来处理，减轻服务器和带宽的负担，节约空间和宽带租用成本。并且减轻服务器的负担，ajax的原则是“按需取数据”，可以最大程度的减少冗余请求，和响应对服务器造成的负担。
　　4、基于标准化的并被广泛支持的技术，不需要下载插件或者小程序。
　　5、ajax可使因特网应用程序更小、更快，更友好。


```

```

```
// https://www.cnblogs.com/zqzjs/p/4912623.html

        var xhr = null;
         //第一步 创建XMLHttpRequet对象
        xhr = new XMLHttpRequest()
    
         // 第二步: 调用 open(type,url,async)方法,  参数1：请求类型（get,post）;参数2：url   参数3：是否异步(true:异步，false:同步）
     
        xhr.open("GET","http://localhost:3000",true);
       
        // 第三步：调用send()方法  1个参数：作为请求主体发送的数据  ,   如果不需要，则必须传入null。
        xhr.send(null);
        //第四步：监听onreadystatechange事件，每次服务器相应数据都会触发该事件
        xhr.onreadystatechange = function(){
       //xhr.status    响应的HTTP状态码
       ```
       |HTTP状态码|状态字符串|说明|
       |_ _ _| _ _ _ | _ _ _|
       
        |200 |OK|服务器成功返回了页面|
       ```
       
       
       statusText    HTTP状态的说明
       //readyState
          if(xhr.readyState == 4 && xhr.status == 200){
            console.log(xhr.responseText);//responseText()     作为响应主体被返回的文本,还有一个responseXML
             }
          }
```

function ajax(options){
    var xhr = null;
    var params = formsParams(options.data);
    //创建对象
    if(window.XMLHttpRequest){
        xhr = new XMLHttpRequest()
    } else {
        xhr = new ActiveXObject("Microsoft.XMLHTTP");
    }
    // 连接
    if(options.type == "GET"){
        xhr.open(options.type,options.url + "?"+ params,options.async);
        xhr.send(null)
    } else if(options.type == "POST"){
        xhr.open(options.type,options.url,options.async);
        xhr.setRequestHeader("Content-Type","application/x-www-form-urlencoded");
        xhr.send(params);
    }
    xhr.onreadystatechange = function(){
        if(xhr.readyState == 4 && xhr.status == 200){
            options.success(xhr.responseText);
        }
    }
    function formsParams(data){
        var arr = [];
        for(var prop in data){
            arr.push(prop + "=" + data[prop]);
        }
        return arr.join("&");
    }
 
}
 
ajax({
    url : "a.php",  // url---->地址
    type : "POST",   // type ---> 请求方式
    async : true,   // async----> 同步：false，异步：true 
    data : {        //传入信息
        name : "张三",
        age : 18
    },
    success : function(data){   //返回接受信息
        console.log(data);
    }
})

```
