---
title: "Shadowsocks配合polipo实现服务器科学上网"
date: 2021-03-07T17:13:53+08:00
archives: "2021"
tags: ["tool"]
author: Jam
---
# shadowsocks 配合 polipo 实现服务器科学上网

## shadowsocks

### 下载
> 参考：[GitHub - shadowsocks/shadowsocks-libev: Bug-fix-only libev port of shadowsocks. Future development moved to shadowsocks-rust](https://github.com/shadowsocks/shadowsocks-libev)  

``` Linux
apt install shadowsocks-libev
```

``` Mac
brew install shadowsocks-libev
```

### 配置
这里需要在shadowsocks-libev/config.json配置vpn节点的信息。

``` Linux
vim /etc/shadowsocks-libev/config.json
```

``` Mac
/usr/local/etc/shadowsocks-libev.json
```

### 启动
> 主力要注意ss-local 和ss-server是两种不同的启动模式：  
> ss-local 是配置shadowsocks去连VPN。  
> ss-server 是配置shadowsocks成为一个代理服务器。  
> 具体细节可以参考: man ss-local, man ss-server  

``` Linux
# 配置开机启动
sudo systemctl enable shadowsocks-libev-local@config

# 启动
sudo systemctl start shadowsocks-libev-local@config

# 查看状态
sudo systemctl status shadowsocks-libev-local@config
```

## polipo
shadowsocks的ss-local是基于socks5协议的代理服务，为了方便日常使用，可以通过polipo做一层转发，将socks5转成http和https以及ftp等协议。

### 下载
``` Linux
sudo apt install polipo
```

``` Mac
brew install polipo
```

### 配置
``` Linux
vim /etc/polipo/config

proxyAddress = "0.0.0.0"
socksParentProxy = "127.0.0.1:1080"
socksProxyType = socks5
proxyPort = 8123
```

### 启动
```
# 启动
sudo systemctl start polipo

# 查看状态
sudo systemctl status polipo
```


## 如何使用代理

### 直接使用

```
export http_proxy="http://127.0.0.1:8123"
export https_proxy="http://127.0.0.1:8123"
export ftp_proxy="http://127.0.0.1:8123"
```

### 配置zshrc
```
function setproxy(){
	export http_proxy=http://127.0.0.1:8123;
	export https_proxy=http://127.0.0.1:8123;
	export ftp_proxy=http://127.0.0.1:8123;
}
function unsetproxy(){
	unset http_proxy
	unset https_proxy
	unset ftp_proxy
}
```

## 测试
```
curl www.google.com
```
