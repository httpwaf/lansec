# lansec

## 一 、介绍
lansec是一款开源的办公局域网流量安全系统，用于监控上网行为和境外流量，及时发现内网数据泄露，也可定制需求。

## 二 、局域网防御非常重要
大多境外组织通过渗透局域网拿到内部数据，因而监控员工上网行为和主机终端是否被境外组织控制非常有必要。

## 三、系统内核要求
要求内核版本大于3.10，推荐2020年以后的linux发行版本：
* Ubuntu 16.04+
* Fedora 31+
* RHEL 7.0+
* Debian 10+
* Rocky Linux 9.0+
* ...

```console
$ wget http://39.106.251.213/lansec.tar.gz
$ mkdir /lansec/ && tar -zxvf lansec.tar.gz -C /lansec/ && chmod 777 /lansec/bin/* && /lansec/bin/lansec daemon
$ 1. Kill all of  processes...........................
  2. Init  ok.........................................
  3. System is running................................
```
成功运行后，可以用浏览器登陆web管理口是5678

* 停止运行/lansec/bin/lansec stop
* 卸载 rm /lansec/ -rf
## 四、两种运行模式
#### 1、单网卡旁路镜像模式
局域网Linux（包括虚拟机）安装一台，即可监控整个局域网流量。步骤是：
* 1、在局域网核心交换机上设置端口镜像。
* 2、将Lansec的网卡接入镜像口。
* 3、如果是虚拟机安装Lansec，虚拟机网卡桥接模式即可。
#### 2、双网卡串接模式
串接模式可以白名单设置只允许的上网域名和IP，更安全。
<img height="307" width="512" src="https://github.com/ebpf-security/ebpf-security.github.io/blob/main/img/gateway.png"></img></a>
 	
 	
## 五、商业版演示地址

大屏演示首次加载组件需要10秒，地址 [http://39.106.251.213/lansec.html](http://39.106.251.213/lansec.html)

## 六、源码部署和技术白皮书微信号httpwaf

![](https://gitee.com/httpwaf/httpwaf/raw/master/img/wechat.png)
