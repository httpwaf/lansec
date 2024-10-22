# lansec

## 一 、介绍
lansec本质是局域网逻辑网关隔离系统，减少局域网99.9%以上的0day漏洞的远程利用，拦截木马通信和保障局域网数据安全。

## 二 、局域网防御非常重要
大多内网渗透都是通过利用终端软件漏洞如视频、社交、浏览器、电子邮件、输入法等在局域网的电脑电脑植入后门，从而入侵内网。[**查看部分2024公开的终端软件高危漏洞和攻击手段**](./exploit.md)
政府军事等重要部门都是物理隔离防止0day利用，由于云技术的迅速发展，企业研发、运营、客服、财务等都必须联网，部署逻辑隔离系统非常有必要。

## 三、系统内核要求
要求内核版本大于3.10，推荐2020年以后的linux发行版本：
* Ubuntu 16.04+
* Fedora 31+
* RHEL 7.0+
* Debian 10+
* Rocky Linux 9.0+
* ...

```console
$ wget http://101.42.31.94/lansec.tar.gz
$ mkdir /lansec/ && tar -zxvf lansec.tar.gz -C /lansec/ && chmod 777 /lansec/bin/* && /lansec/bin/lansec daemon
$ 1. Kill all of  processes...........................
  2. Init  ok.........................................
  3. System is running................................
```
成功运行后，可以用浏览器登陆web管理口是5678

* 停止运行/lansec/bin/lansec stop
* 卸载 rm /lansec/ -rf
## 四、两种运行模式
#### 1、单网卡软件模式
局域网任何一台Linux（包括虚拟机）安装一台，即可对整个局域网进行防御。典型的安装步骤是：
* 1、在Windows上安装Vmware虚拟机，然后安装Linux操作系统，把物理网卡设置为桥接模式（必须是有线网卡，不能是无线网卡）。保证Linux、Windows、路由器在同一个IP网段。
* 2、在Linux上安装Lansec。
* 3、需要防护的Windows上运行ncpa.cpl命令，去掉IPv6协议，再把IPv4的网关指向lansec的IP地址如192.168.1.8，配置好DNS即可，如下图：
<img height="900" width="820" src="https://github.com/ebpf-security/ebpf-security.github.io/blob/main/img/lan.png"></img></a>
#### 2、双网卡硬件模式
硬件模式终端电脑不需要任何设置，支持IPv6，硬件隔离比软件隔离更安全。
<img height="307" width="512" src="https://github.com/ebpf-security/ebpf-security.github.io/blob/main/img/gateway.png"></img></a>
 	
 	
## 五、商业版演示地址

演示地址 [http://101.42.31.94:9998/](http://101.42.31.94:9998/)

## 六、源码部署和技术白皮书微信号httpwaf

![](https://gitee.com/httpwaf/httpwaf/raw/master/img/wechat.png)
