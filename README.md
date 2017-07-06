# shadowsocks-php-docker

来自 https://github.com/walkor/shadowsocks-php 的php版shadowsocks

默认镜像jialezi/shadowsocks-php （带有nginx-php5-ssh)

另有纯净版：jialezi/shadowsocks-php:tiny

### 默认环境变量

```
ENV s=127.0.0.1 （服务器地址）
ENV m=aes-256-cfb （加密算法）
ENV k=12345678 （密码）
ENV p=443 （服务器端口）
ENV c=1080 （客户端端口）
ENV n=50 （启动多少进程）
```
启动：
```
docker run -d -p 22:22 -p 80:80 -p 443:443 jialezi/shadowsocks-php

docker run -d -p 22:22 -p 80:80 -p 443:443 -e m=jialezi -e p 443 -e n=30 jialezi/shadowsocks-php
```
### nginx && php5.5

镜像附带nginx和php5.5

打开http://ip 可访问，默认为探针.

可自行挂载，网站文件默认位置：/usr/share/nginx/html

```
docker run  -d -p 22:22 -p 80:80 -p 443:443 -v /root/html:/usr/share/nginx/html jialezi/shadowsocks-php
```
### ssh

镜像启用ssh服务，

默认22端口

账户：root，密码：root
