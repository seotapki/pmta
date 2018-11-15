

##### CentOS 关闭ipv6
```
vi /etc/sysctl.conf
net.ipv6.conf.all.disable_ipv6=1
net.ipv6.conf.default.disable_ipv6=1
net.ipv6.conf.lo.disable_ipv6=1
reboot
```

##### 安装MailWizz
```
安装LNMP 
lnmp vhost add  域名
```
##### 安装PMTA
```
rpm -Uvh PowerMTA*.rpm
\cp license /etc/pmta/license

\cp config /etc/pmta/config

mkdir -p /etc/pmta/dkim/
\cp pem/private.pem /etc/pmta/dkim/blingnova.blingnova.net.pem

#权限问题，所以放置在了Vhost目录下
mkdir -p /home/wwwroot/wizz.blingnova.net/tmpmail 
mkdir -p /home/wwwroot/wizz.blingnova.net/badmail
chown -R www /home/wwwroot
chgrp -R www /home/wwwroot


service pmta start
service pmta restart
```

```
DNS Record 添加
DKIM TXT记录
_dmarc
```

```
ip:888 访问管理页面
```
