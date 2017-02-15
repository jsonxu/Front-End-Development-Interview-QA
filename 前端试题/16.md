# For-Front-end-Engineer
整理了最近被问到的前端面试题目以及答案

![MacDown logo](https://img10.360buyimg.com/wympay/jfs/t3820/58/2200196988/439902/f753f08/58539afbN9c3422c1.png)

# 一、 HTML

### 常见Meta标签以及含义
    
 * 答：META标签分两大部分：HTTP标题信息(HTTP-EQUIV)和页面描述信息(NAME)。
  
    ★HTTP-EQUIV  ： HTTP-EQUIV类似于HTTP的头部协议，它回应给浏览器一些有用的信息，以帮助正确和精确地显示网页内容。常用的HTTP-EQUIV类型有：

　　1、Content-Type和Content-Language (显示字符集的设定)
　　说明：设定页面使用的字符集，用以说明主页制作所使用的文字已经语言，浏览器会根据此来调用相应的字符集显示page内容。

　　2、Refresh (刷新)
　　　说明：让网页多长时间（秒）刷新自己，或在多长时间后让网页自动链接到其它网页。

　　3、Expires (期限)
　　　说明：指定网页在缓存中的过期时间，一旦网页过期，必须到服务器上重新调阅。

　　4、Pragma (cach模式)
　　　说明：禁止浏览器从本地机的缓存中调阅页面内容。

　　5、Set-Cookie (cookie设定)
　　说明：浏览器访问某个页面时会将它存在缓存中，下次再次访问时就可从缓存中读取，以提高速度。当你希望访问者每次都刷新你广告的图标，或每次都刷新你的计数器，就要禁用缓存了。通常HTML文件没有必要禁用缓存，对于ASP等页面，就可以使用禁用缓存，因为每次看到的页面都是在服务器动态生成的，缓存就失去意义。如果网页过期，那么存盘的cookie将被删除。

　　6、Window-target (显示窗口的设定)
　　　说明：强制页面在当前窗口以独立页面显示。


　　7、Pics-label (网页RSAC等级评定)
　　　说明：在IE的Internet选项中有一项内容设置，可以防止浏览一些受限制的网站，而网站的限制级别就是通过该参数来设置的。

　　8、Page-Enter、Page-Exit (进入与退出)
　　　说明：这个是页面被载入和调出时的一些特效。

   9、Content-Script-Type (脚本相关)
　　　说明：这是近来W3C的规范，指明页面中脚本的类型。

    ★NAME变量 ： name是描述网页的，对应于Content（网页内容），以便于搜索引擎机器人查找、分类（目前几乎所有的搜索引擎都使用网上机器人自动查找meta值来给网页分类）：
    
    
   1、Keywords (关键字)
　　　说明：为搜索引擎提供的关键字列表

　　2、Description (简介)
　　　说明：Description用来告诉搜索引擎你的网站主要内容。

　　3、Robots (机器人向导)
　　　说明：Robots用来告诉搜索机器人哪些页面需要索引，哪些页面不需要索引。Content的参数有all、none、index、noindex、follow、nofollow。默认是all。

　　4、Author (作者)
　　　说明：标注网页的作者或制作组

　　5、Copyright (版权)
　　　说明：标注版权

　　6、Generator (编辑器)
　　　说明：编辑器的说明

　　7、revisit-after (重访)。

　　 ★Head中的其它一些用法

　　1、scheme (方案)
　　　说明：scheme can be used when name is used to specify how the value of content should　be interpreted.

　　2、Link (链接)
　　　说明：链接到文件

　　3、Base (基链接)
　　　说明：插入网页基链接属性
    
  原文链接：<http://www.cnblogs.com/esshs/articles/157588.html>
  
  
# 二、css

### （一）、那些css属性会引起浏览器重排？
  
 答：重排是指一种改变，可以理解为渲染树需要重新计算。下面是常见的触发重排的操作：

* 重新调整浏览器窗口大小
* 修改字体
* 添加、删除样式表
* 修改页面元素内容
* 激活CSS伪类，如a:hover
* 修改class的属性
* 修改DOM
* 计算offsetWidth和offsetHeight
* 设置style的属性

如何避免重排或者减少重排带来的性能问题。
  
* 修改元素的class属性，并且尽可能在DOM树中比较低的节点上
* 避免在内联样式中设置多重属性
* 将动画应用在absolute定位或者fixed的元素上
* 减少table布局
* 避免使用CSS表达式

### （二）、Sass和Less

1. Sass的常见语法
 * 答：参考慕课网的课程吧。挺好的 [Sass入门篇](http://www.imooc.com/learn/311) [Sass进阶篇](http://www.imooc.com/learn/436)
  
2. 使用预编译处理有什么好处？（可以使用css完成，为什么使用Sass？）
 * 答：

 
# 三、JavaScript
### （一）、基础知识之原型链
```
function P(){}

var p = new P();

p.prototype.constructor 指向？：指向函数本身，即 p 。

p.constructor 指？ ： 指向它的构造函数，即 P 。

p.[[proto]] 指？ ： 指向它的构造函数的原型，即 P.prototype 。
```
参考课程 [zepto设计和源码分析](http://www.imooc.com/learn/745)
  
### （二）、基础知识之继承

  1.请用js实现一个类P，包含成员变量a，成员变量b，成员函数sum，sum输出a与b的和，a，b默认值都为0。实现一个类M，M继承自P，在P的基础上增加成员变量c，成员函数sum变成输出a,b,c的和。

* 答

```
function P(a,b){
    this.a = a;
    this.b = b;
}

P.prototype.sum = function(){
    return this.a + this.b;
}

function M(a,b,c){

    if(arguments.length < 3){
        if(arguments.length === 2){
            this.a = arguments[0];
            this.b = 0;
            this.c = arguments[1];
        } else if(arguments.length === 1){
            this.a = 0;
            this.b = 0;
            this.c = a;
        } else {

        }
    } else {
        P.call(this,a,b);
        this.c = c;
    }
    
}

M.prototype = new P();

M.prototype.sum = function(c){
    return this.a + this.b + this.c;
}

var m = new M(3);
console.log( m.sum() );

```

### （三）、基础知识之this

* this指向

```
  function F(){this.a=1;}
  
  F(); //指向window对象
  
  new F(); //指向new出来的对象
```
  
* 改变this指向

  原生js的方法 bind call apply方法。
  
  Es6中的 => 函数中，this的指向不会改变。
  
### （四）、基础知识之setTimeout

* 下列代码会输出什么？
  
```
for (var i = 0; i < 3; ++i) {
    function(i){
      setTimeout(function(){
          console.log(i);   
      }, 0);
    } 
}
  
  
//输出 333
//因为setTimeout是异步执行，同时限制条件是 ++i，不是i++。
```

* 或者面试官会问，setTimeout的时间设置为0，会有什么结果？

### （五）、基础知识之闭包

如果要让上面的代码正常输出 0 1 2，怎么做？

```
for (var i = 0; i < 3; ++i) {
    (function(i){
      setTimeout(function(){
          console.log(i);
      }, 0);
    })(i) 
}
```

### （六）、基础知识原生选择器有哪些？按照性能高低排序？

* 答：(不必全部答出)
 
```
a. document.getElementById()
  
b. document.getElementsByClassName()
  
c. document.getElementsByTagName()
  
d. document.querySelector()
  
f. document.querySelectorAll()

// 性能高低排序 ： d > f > b > c > a （不太确定）
```
### （七）、自己实现一个Promise对象，你会怎么做？

* 答：介绍的文章也挺多的。Promise遵循Promises/A+规范。文章链接：[教你一步一步实现一个Promise](http://www.tuicool.com/articles/RzQRV3)

### （八）、ES6中 Set和Map的区别

* 答：
 
  Map : ES6 中两种新的数据结构集：Map 和 WeakMap。事实上每个对象都可以看作是一个 Map。
        一个对象由多个 key-val 对构成，在 Map 中，任何类型都可以作为对象的 key。
   
  Set : Set 对象是一组不重复的值，重复的值将被忽略，值类型可以是原始类型和引用类型。
  
  参考：[ES6 扫盲](https://github.com/metagrover/ES6-for-humans)


# 四、HTTP

###（一）、常见状态码

（介绍的文章太多了……列一下问的问题）

* 301 和 302的具体区别，都是重定向，返回一个新的链接，然后重新请求，差别在哪？

   答：301是永久性重定向，表示请求的资源已经分配到的新的URL。如果已经把资源对应的URL保存为书签了，应该重新保存。当指定资源路径最后忘了加 '/'，会出现301.
      
      302是临时性重定向，表示请求的资源已经被分配了新的url，希望用户本次使用新的url访问。已经移动的资源对应的url将来还有可能改变。
      
* 什么情况下会出现304？
* 400系列和500系列的区别？
* 如果出现500系列的问题，前端应该做什么？


###（二）、浏览器的缓存机制（与304状态码结合问）

参考腾讯文章 [web缓存机制系列](http://www.alloyteam.com/2012/03/web-cache-2-browser-cache/)


###（三）、HTTP HTTPS的区别。（非对称加密和对称加密的区别）


###（四）、从输入 URL 到页面加载完的过程中都发生了什么事情（越详细越好）？

答：

* 把URL分割成几个部分：协议、网络地址、资源路径。其中网络地址指示该连接网络上哪一台计算机，可以是域名或者IP地址，可以包括端口号；协议是从该计算机获取资源的方式，常见的是HTTP、FTP，不同协议有不同的通讯内容格式；资源路径指示从服务器上获取哪一项资源。
  例如：http://www.guokr.com/question/554991/
  协议部分：http
  网络地址：www.guokr.com
  资源路径：/question/554991/
  
* 如果地址不是一个IP地址，通过DNS（域名系统）将该地址解析成IP地址。IP地址对应着网络上一台计算机，DNS服务器本身也有IP，你的网络设置包含DNS服务器的IP。
  例如：www.guokr.com 不是一个IP，向DNS询问请求www.guokr.com 对应的IP，获得IP： 111.13.57.142。这个过程里，你的电脑直接询问的DNS服务器可能没有www.guokr.com 对应的IP，就会向它的上级服务器询问，上级服务器同样可能没有，就依此一层层向上找，最高可达根节点，找到或者全部找不到为止。
  
* 如果地址不包含端口号，根据协议的默认端口号确定一个。端口号之于计算机就像窗口号之于银行，一家银行有多个窗口，每个窗口都有个号码，不同窗口可以负责不同的服务。端口只是一个逻辑概念，和计算机硬件没有关系。
  例如：www.guokr.com 不包含端口号，http协议默认端口号是80。如果你输入的url是http://www.guokr.com:8080/ ，那表示不使用默认的端口号，而使用指定的端口号8080。
  
* 向2和3确定的IP和端口号发起网络连接。
  例如：向111.13.57.142的80端口发起连接
  
* 根据http协议要求，组织一个请求的数据包，里面包含大量请求信息，包括请求的资源路径、你的身份
  例如：用自然语言来表达这个数据包，大概就是：请求 /question/554991/ ，我的身份是xxxxxxx。
  
* 服务器响应请求，将数据返回给浏览器。数据可能是根据HTML协议组织的网页，里面包含页面的布局、文字。数据也可能是图片、脚本程序等。现在你可以用浏览器的“查看源代码”功能，感受一下服务器返回的是什么东东。如果资源路径指示的资源不存在，服务器就会返回著名的404错误。
  
* 如果（6）返回的是一个页面，根据页面里一些外链的URL，例如图片的地址，按照（1）－（6）再次获取。
  
* 开始根据资源的类型，将资源组织成屏幕上显示的图像，这个过程叫渲染，网页渲染是浏览器最复杂、最核心的功能。
* 将渲染好的页面图像显示出来，并开始响应用户的操作。

# 五、前端项目

### （一）、项目构建工具 gulp/webpack

1. gulp常用模块
 
答：

* gulp-rev: 给每个文件增加版本号，这个版本号是根据文件内容计算出的哈希码，用来解决浏览器自动缓存的问题
* gulp-useref: 代码压缩，合并多个文件

```
<!--build : css css/yourname.css-->
 //这里面是你的多个文件
<!--end build-->
```
* gulp-filter : 过滤器，筛选文件进行下一步
* gulp-uglify : 压缩js代码的模块
* gulp-csso : 压缩css代码插件
* gulp-watch : 监听文件改变，自动执行任务
* gulp-concat : 多个文件合并为一个文件
* gulp-responsive : 一个大图根据规则生成响应式图片

2.gulp压缩js的具体步骤：

答： 

* a. 新建一个 gulpfile.js 文件.
* b. 获取 gulp :   var gulp = require('gulp').
* c. 获取 gulp-uglify 组件
* d. 创建压缩任务

```
gulp.task('script', function() {

  // 1. 找到文件
  gulp.src('js/*.js')
  // 2. 压缩文件
    .pipe(uglify())
  // 3. 另存压缩后的文件
    .pipe(gulp.dest('dist/js'))
    
})
```

3.webpack压缩文件的具体步骤

4.gulp和grunt的工作原理

### （二）、项目优化方式：

* 答：雅虎军规 14条 

### （三）、CDN原理

* 答：与上题 一起参考课程：[雅虎军规](http://www.imooc.com/learn/50)

### （四）、除了雅虎军规，你还知道什么优化方式？

* 答：抱歉，这个我真的不知道。

### （五）、（或者问点实际的）你的项目中是如何实现权限控制的？

* 答： 在express框架中，使用session进行登陆检测。在用户登陆时，将前端传来的用户名和密码与数据库进行匹配，将匹配正确的用户的信息保存在服务端session中。在其他需要进行登陆检测的接口中，为其添加检测`req.session`的中间件，若`req.session`存在，则调用业务逻辑的处理，否则，返回错误信息，或重定向到登录页面。



# 六 2016新技术以及框架

### 一、jQuery

#### （一）项目是jQuery开发完成，那是如何解决组件化问题的。

* 答：CommonJS/AMD + 观察者模式。

请参考我的一篇文章：[Web组件开发基础](http://www.jianshu.com/p/85493e155651)

更详细的内容，请参考课程：[阿当大话西游之WEB组件](http://www.imooc.com/learn/99)

#### （二）你读过jQuery源码吗，你读的部分，源码是如何实现的。

* 答：没说的，去读源码吧。可以先读一下zepto，比较简单。


### 二、React

#### （一）React的生命周期

* 答：挂载（Mount） 更新（Update） 卸载（Unmount）以及各自期间的钩子函数，以及钩子函数的执行顺序。

  参考课程：[React入门](http://www.imooc.com/learn/504)
  

#### （二）Redux原理 （项目中如何解决不同组件通信的）

* 答：Rudex是组件顶层的状态管理器。

  请参考文章：[Redux 入门教程](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_one_basic_usages.html)
  
  或者这一篇：[理解 React，但不理解 Redux，该如何通俗易懂的理解 Redux](https://www.zhihu.com/question/41312576)
  
  
#### （三）React优化方式：

* 答：__*（待补充）*__


#### （四）问点具体的：
  
1. React比jQuery优势在哪？ __*（待补充）*__
2. React实现局部刷新，是用ComponentShouldUpdate这个方法。如果刷新区域比较多，那项目中会存在很多这个方法。你是如何解决要局部刷新需要使用无处不在的ComponentShouldUpdate方法这个问题的。 __*（待补充）*__


### 三、Node.js

#### （一）如何捕获Node.js中的异步错误？

* 答：具体文章：[nodejs的异步和错误处理](https://cnodejs.org/topic/56aad41a26d02fc6626bb369)
  
1. 回调函数
2. Promise返回错误
3. async await


#### （二）如何使用Node.js进行后端接口合并的？

* 答：我的项目中是使用 Promise 和 async 模块。

```
exports.initData = (req) => {
  return new Promise((resolve, reject) => {
    async.parallel(
      {
        permissions: (callback) => {
          //...       
        },
        specialList: (callback) => {
          //...
        },
        trustList: (callback) => {
          //...
        }
      },
      (err, results) => {
        if (err) {
          reject(err);
        } else {
          resolve(results);
        }
      })
  })
}
```

###（三）Node.js的基础知识：

* 答：参考课程：[进击Node.js基础（一）](http://www.imooc.com/learn/348)  [进击Node.js基础（二）](http://www.imooc.com/learn/637)


# 七 常见网络安全（推荐一本书：《web前端黑客技术揭秘》）

#### （一）你了解常见的网络攻击吗？
（相关文章太多了）

答：

* DDos：利用合法的请求大量占用服务器资源导致服务器瘫痪。
2. XSS：想尽一切办法在目标网站上执行你的恶意脚本，可以设置httpOnly来使客户端脚本无法读写cookie，这样可以有效防止XSS获取cookie。
3. CSRF：即跨站请求伪造。发送模拟请求来执行恶意意图。

#### （二）cookie安全机制
答：

* 设置cookie过期时间
2. httpOnly机制。

#### （三）cookie和session有什么区别

答：

* cookie数据存放在客户的浏览器上，session数据放在服务器上。
* cookie不是很安全，别人可以分析存放在本地的COOKIE并进行COOKIE欺骗考虑到安全应当使用session。
* session会在一定时间内保存在服务器上。当访问增多，会比较占用你服务器的性能考虑到减轻服务器性能方面，应当使用COOKIE。
* 单个cookie保存的数据不能超过4K，很多浏览器都限制一个站点最多保存20个cookie。
* 所以个人建议：
   将登陆信息等重要信息存放为SESSION
   其他信息如果需要保留，可以放在COOKIE中

#### （四）跨域

1. 跨域的常见方式
2. JSHOP原理
3. 从技术角度解释一下跨域的隐患。

对于以上三个问题，参见文章：[浏览器同源政策及其规避方法](http://www.ruanyifeng.com/blog/2016/04/same-origin-policy.html) 以及 [跨域资源共享 CORS 详解](http://www.ruanyifeng.com/blog/2016/04/cors.html) 两篇文章。


# 八 算法以及逻辑题

#### （一）数组去重

答：[js数组去重的4个方法](http://blog.csdn.net/chengxuyuan20100425/article/details/8497277)

#### （二）集中常见排序

答：我个人比较熟悉冒泡和快排

冒泡：

```
function bubbleSort(arr){
    for(var i = 0,len = arr.length;i < len; i++){
        for (var j = i + 1 ; j < len; j ++){
            if(arr[i] > arr[j]){
                var tem = arr[i];
                arr[i] = arr[j];
                arr[j] = tem;
            }
        }
    }
    console.log(arr);
    return arr;
} 

bubbleSort([14,11,3,321,22,32,2,3]);
```

快排：

```
function quickSort(arr){
    if(arr.length <= 1){
        return arr;
    }

    var resultArr = [];
    var leftArr = [];
    var rightArr = [];
    var centerNum = arr[0];

    for(var i = 1,len = arr.length;i < len ; i++){
        if( arr[i] < centerNum ){
            leftArr.push(arr[i]);
        } else {
            rightArr.push(arr[i]);
        }
    };
    
    resultArr = quickSort(leftArr).concat( [centerNum],quickSort(rightArr) );
    return resultArr;
}
    
quickSort([14,11,3,321,22,32,2,3]);
```

#### （三）现场出题，并说明时间复杂度。

1. 两个顺序排列的数组A和B，求B数组是否为A数组的子集。（数组内可能有重复数字）。
2. 写一个函数，把字符串里面的空格全部去掉，并返回删除的空格个数，不许开辟新空间，只能申请简单类型的自动变量。
……

关于时间复杂度和空间复杂度，请参考这两篇文章：

[算法的时间复杂度和空间复杂度](http://www.cnblogs.com/songQQ/archive/2009/10/20/1587122.html)  [算法的时间复杂度和空间复杂度-总结](http://blog.csdn.net/zolalad/article/details/11848739)

#### （四）现场出逻辑题

1. 一根不均匀的香，从头到尾烧完要一个小时。如何用烧香的方法确定半小时的时间？有两根这样的香，还可以确定哪些时间段。
2. 有一堆桃子和一群猴子。如果每个猴子分3个桃子，还剩下59个桃子。如果每个猴子分5个桃子，最后一个猴子的桃子不够5个。问几个猴子？几个桃子？
……

