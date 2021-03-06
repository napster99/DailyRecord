# HTML5 预加载标签  (2016-06-16)

###prefetch <- keywords

[原文地址](http://www.jianshu.com/p/7f58ddfc1392/)

DNS Prefetch 已经被下面的浏览器支持
Firefox: 3.5+
Chrome: Supported
Safari 5+
Opera: Unknown
IE: 9 (called “Pre-resolution” on blogs.msdn.com)

###what ? 
prefetch 即预加载，在用户需要前我们就将所需的资源加载完毕。

chrome 的预加载技术,输入浏览器地址的时候，chrome已经预加载了该网址的内容， 还没得到证实，不过chrome的预连接、预加载与预渲染都很厉害的。

**文件夹里的这篇文章有详细介绍这类。**

####DNS prefetch
当我们访问一个网站的时候，需要将域名转化为对应的IP地址，这是一个非常耗时的过程。
那我们如何解决呢？？？

不得不说meta标签里面的http-equiv字段，value哪有哪些取值呢？
######它是什么？
http-equiv顾名思义，相当于http的文件头作用，它可以向浏览器传回一些有用的信息，以帮助正确和精确地显示网页内容，与之对应的属性值为content，content中的内容其实就是各个参数的变量值。   
```
meat标签的http-equiv属性语法格式是：＜meta http-equiv="参数" content="参数变量值"＞ ；其中http-equiv属性主要有以下几种参数：
```

* Expires（期限）
说明：可以用于设定网页的到期时间。一旦网页过期，必须到服务器上重新传输。
用法：＜meta http-equiv="expires" content="Wed, 20 Jun 2007 22:33:00 GMT"＞  
注意：必须使用GMT的时间格式。 
* Pragma(cache模式) 
说明：禁止浏览器从本地计算机的缓存中访问页面内容。
用法：＜meta http-equiv="Pragma" content="no-cache"＞ 
注意：这样设定，访问者将无法脱机浏览。
* Refresh(刷新)
说明：自动刷新并指向新页面。 
用法：＜meta http-equiv="Refresh" content="2；URL=http://www.net.cn/"＞  
注意：其中的2是指停留2秒钟后自动刷新到URL网址。 
* Set-Cookie(cookie设定) 
说明：如果网页过期，那么存盘的cookie将被删除。 
用法：<meta http-equiv="Set-Cookie" content="cookievalue=xxx;expires=Friday,12-Jan-200118:18:18GMT；path=/">
注意：必须使用GMT的时间格式。
* Window-target(显示窗口的设定) 
说明：强制页面在当前窗口以独立页面显示。 
用法：＜meta http-equiv="Window-target" content="_top"＞ 
注意：用来防止别人在框架里调用自己的页面。 **(在iframe里无效？？)**
* content-Type(显示字符集的设定) 
说明：设定页面使用的字符集。
用法：＜meta http-equiv="content-Type" content="text/html; charset=gb2312"＞  
* Pics-label(网页等级评定) 
说明：在IE的internet选项中有一项内容设置，可以防止浏览一些受限制的网站，而网站的限制级别就是通过meta属性来设置的。
用法：＜meta http-equiv="Pics-label" contect=""＞
* Page_Enter、Page_Exit 
说明：设定进入页面时的特殊效果
用法：＜meta http-equiv="Page-Enter"    contect="revealTrans(duration=1.0,transtion=    12)"＞   
     ＜meta http-equiv="Page-Exit"    contect="revealTrans(duration=1.0,transtion=    12)"＞   
      Duration的值为网页动态过渡的时间，单位为秒。  
      Transition是过渡方式，它的值为0到23，分别对应24种过渡方式。如下表：  
      0    盒状收缩    1    盒状放射  
      2    圆形收缩    3    圆形放射  
      4    由下往上    5    由上往下  
      6    从左至右    7    从右至左  
      8    垂直百叶窗    9    水平百叶窗  
      10    水平格状百叶窗    11垂直格状百叶窗  
      12    随意溶解    13从左右两端向中间展开  
      14从中间向左右两端展开    15从上下两端向中间展开  
      16从中间向上下两端展开    17    从右上角向左下角展开  
      18    从右下角向左上角展开    19    从左上角向右下角展开  
      20    从左下角向右上角展开    21    水平线状展开  
      22    垂直线状展开    23    随机产生一种过渡方式  
* 清除缓存（再访问这个网站要重新下载！） 
用法：＜meta http-equiv="cache-control" content="no-cache"＞
* 关键字,给搜索引擎用的 
用法：＜meta http-equiv="keywords" content="keyword1,keyword2,keyword3"＞  
* 页面描述 
用法：＜meta http-equiv="description" content="This is my page"＞

以上就是取值了，有点小多

```
<meta http-equiv='x-dns-prefetch-control' content='on'>
<link rel='dns-prefetch' href='http://g-ecx.images-amazon.com'>
<link rel='dns-prefetch' href='http://z-ecx.images-amazon.com'>
<link rel='dns-prefetch' href='http://ecx.images-amazon.com'>
<link rel='dns-prefetch' href='http://completion.amazon.com'>
<link rel='dns-prefetch' href='http://fls-na.amazon.com'>
```

####应用场景1：
我们的资源存在在不同的 CDN 中，那提前声明好这些资源的域名，就可以节省请求发生时产生的域名解析的时间。
####应用场景2：
如果我们知道用户接下来的操作一定会发起一起资源的请求，那就可以将这个资源进行 DNS-Prefetch，加强用户体验。


##Resource prefetch
在 Chrome 下，我们可以用 link标签声明特定文件的预加载：

```
<link rel='subresource' href='critical.js'>
<link rel='subresource' href='main.css'>
<link rel='prefetch' href='secondary.js'>
```
在 Firefox 中或用 meta 标签声明：
```<meta http-equiv="Link" content="<critical.js>; rel=prefetch">```

rel='subresource' 表示当前页面必须加载的资源，应该放到页面最顶端先加载，有最高的优先级。

rel='prefetch' 表示当 subresource 所有资源都加载完后，开始预加载这里指定的资源，有最低的优先级。

注意：只有可缓存的资源才进行预加载，否则浪费资源！

文／赖小赖小赖（简书作者）
原文链接：http://www.jianshu.com/p/7f58ddfc1392
著作权归作者所有，转载请联系作者获得授权，并标注“简书作者”。


##Pre render
前面说到的预解析DNS、预加载资源已经够强悍了有木有，可还有更厉害的预渲染（Pre-rendering）！
```<link rel='prerender' href='http://www.pagetoprerender.com'>```

##不是所有的资源都可以预加载
当资源为以下列表中的资源时，将阻止预渲染操作：

URL 中包含下载资源
页面中包含音频、视频
POST、PUT 和 DELETE 操作的 ajax 请求
HTTP 认证(Authentication)
HTTPS 页面
含恶意软件的页面
弹窗页面
占用资源很多的页面
打开了 chrome developer tools 开发工具
##手动触发预渲染操作
在 head 中强势插入 link[rel='prerender'] 即可：

var hint =document.createElement("link")
hint.setAttribute(“rel”,”prerender”)
hint.setAttribute(“href”,”next-page.html”)
document.getElementsByTagName(“head”)[0].appendChild(hint)
##兼容性
这么好用的特性，当然要考虑各浏览器的兼容程度了(哭：

IE9 支持 DNS pre-fetching 但管它叫 prefetch。

IE10+ 中 dns-prefetch 和 prefetch 是等价的。

其他方面的测试，目前还没有很好的方案，暂且只能通过查看浏览器是否缓存来测试。

在 Chrome 中打开了 chrome developer tools 开发工具会阻止页面的预渲染，所以我们看不到这个过程，但可以在 chrome://cache/ 或 chrome://net-internals/#prerender 中查看。

Firefox 可以在 about:cache 中查看。

警告
这些特定还是实验性质的，将来可能改变。

权利越大，责任越大，不要滥用！

参考链接
[html5-prefetch](https://medium.com/@luisvieira_gmr/html5-prefetch-1e54f6dda15d/)
[MDN Controlling DNS prefetching](https://developer.mozilla.org/en-US/docs/Web/HTTP/Controlling_DNS_prefetching/)
[MDN Link prefetching FAQ](https://developer.mozilla.org/en-US/docs/Web/HTTP/Link_prefetching_FAQ/)

