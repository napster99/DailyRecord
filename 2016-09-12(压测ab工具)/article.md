# 压测ab工具介绍  (2016-09-12)

###nodejs <- keywords

[原文地址](http://www.jianshu.com/p/43d04d8baaf7/)
在学习ab工具之前，我们需了解几个关于压力测试的概念

吞吐率（Requests per second）
概念：服务器并发处理能力的量化描述，单位是reqs/s，指的是某个并发用户数下单位时间内处理的请求数。某个并发用户数下单位时间内能处理的最大请求数，称之为最大吞吐率。
计算公式：总请求数 / 处理完成这些请求数所花费的时间，即
Request per second = Complete requests / Time taken for tests

并发连接数（The number of concurrent connections）
概念：某个时刻服务器所接受的请求数目，简单的讲，就是一个会话。

并发用户数（The number of concurrent users，Concurrency Level）
概念：要注意区分这个概念和并发连接数之间的区别，一个用户可能同时会产生多个会话，也即连接数。

用户平均请求等待时间（Time per request）
计算公式：处理完成所有请求数所花费的时间/ （总请求数 / 并发用户数），即
Time per request = Time taken for tests /（ Complete requests / Concurrency Level）

服务器平均请求等待时间（Time per request: across all concurrent requests）
计算公式：处理完成所有请求数所花费的时间 / 总请求数，即
Time taken for / testsComplete requests
可以看到，它是吞吐率的倒数。
同时，它也=用户平均请求等待时间/并发用户数，即
Time per request / Concurrency Level

ab工具简介
ab全称为：apache bench

在官网上的解释如下：

ab是Apache超文本传输协议(HTTP)的性能测试工具。其设计意图是描绘当前所安装的Apache的执行性能，主要是显示你安装的Apache每秒可以处理多少个请求。
其他网站解释：

ab是apache自带的压力测试工具。ab非常实用，它不仅可以对apache服务器进行网站访问压力测试，也可以对或其它类型的服务器进行压力测试。比如nginx、tomcat、IIS等。
下载ab工具
进入apache官网 http://httpd.apache.org/ 下载apache即可

启动ab工具
以windows环境下，apache安装路径为C:\apache\Apache24\为例

打开终端，输入命令
cd  C:\apache\Apache24\bin
即可启动ab

开始测试
输入命令
ab -n 100 -c 10 http://test.com/
其中－n表示请求数，－c表示并发数

其余命令请参见 http://apache.jz123.cn/programs/ab.html

测试结果分析
上面的命令运行完毕后就出来测试报告了


完整测试报告
这段展示的是web服务器的信息，可以看到服务器采用的是nginx，域名是wan.bigertech.com，端口是80

服务器信息
这段是关于请求的文档的相关信息，所在位置“/”，文档的大小为338436 bytes（此为http响应的正文长度）

文档信息
这段展示了压力测试的几个重要指标

重要指标
Concurrency Level: 100
//并发请求数
Time taken for tests: 50.872 seconds
//整个测试持续的时间
Complete requests: 1000
//完成的请求数
Failed requests: 0
//失败的请求数

Total transferred: 13701482 bytes
//整个场景中的网络传输量
HTML transferred: 13197000 bytes
//整个场景中的HTML内容传输量

Requests per second: 19.66 [#/sec] (mean)
//吞吐率，大家最关心的指标之一，相当于 LR 中的每秒事务数，后面括号中的 mean 表示这是一个平均值
Time per request: 5087.180 [ms] (mean)
//用户平均请求等待时间，大家最关心的指标之二，相当于 LR 中的平均事务响应时间，后面括号中的 mean 表示这是一个平均值
Time per request: 50.872 [ms] (mean, across all concurrent requests)
//服务器平均请求处理时间，大家最关心的指标之三

Transfer rate: 263.02 [Kbytes/sec] received
//平均每秒网络上的流量，可以帮助排除是否存在网络流量过大导致响应时间延长的问题

这段表示网络上消耗的时间的分解

网络消耗时间
这段是每个请求处理时间的分布情况，50%的处理时间在4930ms内，66%的处理时间在5008ms内...，重要的是看90%的处理时间。

响应情况
关于登录的问题
有时候进行压力测试需要用户登录，怎么办？
请参考以下步骤：

先用账户和密码登录后，用开发者工具找到标识这个会话的Cookie值（Session ID）记下来
如果只用到一个Cookie，那么只需键入命令：
ab －n 100 －C key＝value http://test.com/

如果需要多个Cookie，就直接设Header：
ab -n 100 -H “Cookie: Key1=Value1; Key2=Value2” http://test.com/

总结
总的来说ab工具ab小巧简单，上手学习较快，可以提供需要的基本性能指标，但是没有图形化结果，不能监控。因此ab工具可以用作临时紧急任务和简单测试。
同类型的压力测试工具还有：webbench、siege、http_load等

文／橙子酱（简书作者）
原文链接：http://www.jianshu.com/p/43d04d8baaf7
著作权归作者所有，转载请联系作者获得授权，并标注“简书作者”。


