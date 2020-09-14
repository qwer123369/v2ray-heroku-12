# V2Ray Heroku


## 概述

用于在 Heroku 上部署 V2Ray Websocket。

**Heroku 为我们提供了免费的容器服务，我们不应该滥用它。**

**可以部署两个以上的应用，实现[负载均衡](https://toutyrater.github.io/app/balance.html)，避免长时间大流量连接某一应用而被 Heroku 判定为滥用。**

**Heroku 的网络有时候并不稳定，部署前请三思。**

## 镜像

本镜像仅 6MB，比起其他用于 Heroku 的 V2Ray 镜像，不会因为大量占用资源而被封号。

[![Deploy](https://www.herokucdn.com/deploy/button.png)](https://dashboard.heroku.com/new?template=https%3A%2F%2Fgithub.com%2Fqwer123369%2Fv2ray-heroku-12)

## ENV 设定

### UUID

`UUID` > `一个 UUID，供用户连接时验证身份使用`。

## 注意

WebSocket 路径为 /。

AlterID 为 64。

V2Ray 将在部署时自动安装最新版本。

**出于安全考量，除非使用 CDN，否则请不要使用自定义域名，而使用 Heroku 分配的二级域名，以实现 V2Ray Websocket + TLS。**





项目注册地址，有功底懂项目的人可进行注册使用：点击进入(https://signup.heroku.com/)

申请vps地址：点击进入(https://dashboard.heroku.com/new?template=https%3A%2F%2Fgithub.com%2Fbclswl0827%2Fv2ray-heroku)

github项目地址：点击进入(https://github.com/bclswl0827/v2ray-heroku/blob/master/README.md)  https://github.com/xueliqq/v2ray-heroku/blob/master/README.md
 

开始：

如图所示：输入一个可用的用户名，点击deploy app进入下一步

https://wxf2088.xyz/wp-content/uploads/2020/09/QQ%E6%88%AA%E5%9B%BE20200909180314.png


接下来就是耐心等待约1-2分钟，部署v2ray安装程序

https://wxf2088.xyz/wp-content/uploads/2020/09/QQ%E6%88%AA%E5%9B%BE20200909180618.png

进入之后点击设置按钮，

https://wxf2088.xyz/wp-content/uploads/2020/09/QQ%E6%88%AA%E5%9B%BE20200909180716.png

点击Reveal config vars查看自己的v2ray的uuid

https://wxf2088.xyz/wp-content/uploads/2020/09/QQ%E6%88%AA%E5%9B%BE20200909180752.png

点击右上角OPEN app找到我们的ip地址，也就是分配给我们的域名：

https://wxf2088.xyz/wp-content/uploads/2020/09/QQ%E6%88%AA%E5%9B%BE20200909181222.png

搭建完成，接下来就把我们的这些信息导入我们的v2ray客户端

https://wxf2088.xyz/wp-content/uploads/2020/09/QQ%E6%88%AA%E5%9B%BE20200909181440.png

按照以上格式填写就可以正常使用！

使用cloudflare加速

https://www.cloudflare.com/

登陆Cloudflare官网点击workers--创建--复制脚本--修改对应域名

 addEventListener(
  "fetch",event => {
     let url=new URL(event.request.url);
     url.hostname="应用名称.herokuapp.com";
     let request=new Request(url,event.request);
     event. respondWith(
       fetch(request)
     )
  }
)


 addEventListener(
  "fetch",event => {
     let url=new URL(event.request.url);
     url.hostname="应用名称.herokuapp.com";
     let request=new Request(url,event.request);
     event. respondWith(
       fetch(request)
     )
  }
)
自动筛选ip程序脚本：点击下载(https://www.goyywp.xyz/uploads/kexueshangwang/better-cloudflare-ip-win32.zip)

自动筛选ip最准确的方法是关闭代理，网线直连去测试，否则容易不准确！

也可以手动筛选cloud flare支持各宽带的ip段，*号代表1-255之间任意数字

CloudFlare 百度云合作 ip：
 
162.159.208.4-162.159.208.103
 
162.159.209.4-162.159.209.103
 
162.159.210.4-162.159.210.103
 
162.159.211.4-162.159.211.103
 
各线路推荐列表：
电信：推荐走圣何塞，例：104.16.160.* 或者上面的百度云合作 ip。
移动：推荐走移动香港，例：172.64.32.*、141.101.115.* 或者 104.23.240.0-104.23.243.254。
联通：没发布什么好线路，可走圣何塞。例：104.16.160.* 或者 104.23.240.0-104.23.243.254。
也可以试一下走亚特兰大 108.162.236.*（日前不可用。） 。

CloudFlare 百度云合作 ip：
 
162.159.208.4-162.159.208.103
 
162.159.209.4-162.159.209.103
 
162.159.210.4-162.159.210.103
 
162.159.211.4-162.159.211.103
 
各线路推荐列表：
电信：推荐走圣何塞，例：104.16.160.* 或者上面的百度云合作 ip。
移动：推荐走移动香港，例：172.64.32.*、141.101.115.* 或者 104.23.240.0-104.23.243.254。
联通：没发布什么好线路，可走圣何塞。例：104.16.160.* 或者 104.23.240.0-104.23.243.254。
也可以试一下走亚特兰大 108.162.236.*（日前不可用。） 。
负载均衡配置文件：点击下载(https://www.goyywp.xyz/uploads/v2ray%E5%AE%A2%E6%88%B7%E7%AB%AF%E8%B4%9F%E8%BD%BD%E5%9D%87%E8%A1%A1%E9%85%8D%E7%BD%AE.zip)
教程完毕！
