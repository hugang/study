# Nginx

> Http正向和反向代理服务器，负载均衡，占用资源少，并发能力强
> 
> 正向代理
>   比如要访问youtube，但是不能直接访问，只能先找个翻墙软件，通过翻墙软件才能访问youtube
> 反向代理
>   有很多用户访问youtube，但是youtube悄悄地把这些请求分发到了后台地某一台服务器处理

## 安装

```shell
# 安装依赖包
yum install pcre pcre-devel zlib zlib-devel
# 安装编译工具
yum install gcc gcc-c++ autoconf automake make
# 下载源代码
curl -O https://nginx.org/download/nginx-1.18.0.tar.gz
# 解压源代码
tar xvf nginx-1.18.0.tar.gz 
cd nginx-1.18.0
# 配置
./configure --prefix=/usr/local/nginx
# 编译并且安装
make && make install
# 启动
/usr/local/nginx/sbin/nginx -g 'pid /run/nginx.pid; error_log stderr;'
# 开启防火墙访问权限
firewall-cmd --add-service=http --zone=public --permanent
firewall-cmd --reload

```