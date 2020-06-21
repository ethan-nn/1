---
attachments: [Clipboard_2020-06-21-14-59-57.png, Clipboard_2020-06-21-18-36-57.png, Clipboard_2020-06-21-18-36-59.png, Clipboard_2020-06-21-18-37-03.png, Clipboard_2020-06-21-18-39-06.png, Clipboard_2020-06-21-18-40-44.png, Clipboard_2020-06-21-18-41-13.png, Clipboard_2020-06-21-18-42-11.png]
tags: [home network]
title: openwrt smartdns
created: '2020-06-21T06:52:07.374Z'
modified: '2020-06-21T10:44:04.601Z'
---

# openwrt smartdns
[SmartDNS](https://github.com/pymumu/smartdns)是一个运行在本地的DNS服务器，SmartDNS接受本地客户端的DNS查询请求，从多个上游DNS服务器获取DNS查询结果，并将访问速度最快的结果返回给客户端，提高网络访问速度。 同时支持指定特定域名IP地址，并高性匹配，达到过滤广告的效果。
与dnsmasq的all-servers不同，smartdns返回的是访问速度最快的解析结果。 (详细差异请看FAQ)
支持树莓派，openwrt，华硕路由器，windows等设备。
## 环境
- pve 虚拟机原版安装 x86_64
- OpenWrt 19.07.3 r11063-85e04e9f46 / LuCI openwrt-19.07 branch git-20.136.49537-fb2f363
## 安装
### 下载软件
- [luci-app-smartdns.1.2020.05.04-0005.all-luci-all.ipk](https://github-production-release-asset-2e65be.s3.amazonaws.com/130578889/10883d00-8d9c-11ea-9fd9-8b5cc9f5e810?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAIWNJYAX4CSVEH53A%2F20200621%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20200621T064230Z&X-Amz-Expires=300&X-Amz-Signature=5c573017da757e27b53aff84bba0dd6d9a2a4a7e9dacab3f86f3cea9357a1c41&X-Amz-SignedHeaders=host&actor_id=27984436&repo_id=130578889&response-content-disposition=attachment%3B%20filename%3Dluci-app-smartdns.1.2020.05.04-0005.all-luci-all.ipk&response-content-type=application%2Foctet-stream)
- [smartdns.1.2020.05.04-0005.x86_64-openwrt-all.ipk](https://github-production-release-asset-2e65be.s3.amazonaws.com/130578889/2138b300-8d9c-11ea-9171-1e8ea7b029f9?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAIWNJYAX4CSVEH53A%2F20200621%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20200621T064526Z&X-Amz-Expires=300&X-Amz-Signature=9b30204869869ea790bcc38890bb4e07b53d9242c33e80883b9a53406a5da80e&X-Amz-SignedHeaders=host&actor_id=27984436&repo_id=130578889&response-content-disposition=attachment%3B%20filename%3Dsmartdns.1.2020.05.04-0005.x86_64-openwrt-all.ipk&response-content-type=application%2Foctet-stream)
### scp 将软件包上传到openwrt
```bash
opkg install smartdns.1.2020.05.04-0005.x86_64-openwrt-all.ipk
opkg install luci-app-smartdns.1.2020.05.04-0005.all-luci-all.ipk
```
## 重启
每次安装完软件，刷新刷不出来，我重启一下就ok
![](@attachment/Clipboard_2020-06-21-14-59-57.png)
## 配置
1. 配置smartdns
![](@attachment/Clipboard_2020-06-21-18-37-03.png)
2. 配置dhcp/dns
网络-->dhcp/dns
![](@attachment/Clipboard_2020-06-21-18-39-06.png)
3. 配置lan
![](@attachment/Clipboard_2020-06-21-18-41-13.png)
## 验证，看一下系统日志，貌似打开网页挺快的。没多大感觉，以前就挺快的，呵呵。
![](@attachment/Clipboard_2020-06-21-18-42-11.png)


 

