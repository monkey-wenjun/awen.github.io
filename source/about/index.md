---
title: 关于本站 
date: 2017-06-12 17:44:20
type: "about"
---
本站创建于 2016 年 12 月 30 日，运行在阿里云主机上，此前也写过博客大半年，现在重新搭建博客，使用`typecho`，采用`typecho`的主要原因是因为其是`php`下唯一一个支持`markdown`写作的博客程序。


本站使用 `lnmp` 环境，运行在 `centos 6.x` 上，`web` 服务器使用的是 `nginx` + `php` + `mysql`，采用全站`https`的方式运行，证书使用的是 `Let's Encrypt`，采用该服务商的原因是因为其支持续签证书，写个计划任务放那就不用管证书的到期问题了。

本站开启了 `HTTP2` 协议。


            listen 443 ssl http2 default_server;
            server_name www.awen.me awen.me;
            index index.html index.htm index.php;
            root  /data/wwwroot;
            ssl on;
            ssl_certificate /etc/letsencrypt/live/awen.me/fullchain.pem;
            ssl_certificate_key /etc/letsencrypt/live/awen.me/privkey.pem;
            ssl_ciphers                EECDH+CHACHA20:EECDH+CHACHA20-draft:EECDH+AES128:RSA+AES128:EECDH+AES256:RSA+AES256:EECDH+3DES:RSA+3DES:!MD5;
            ssl_prefer_server_ciphers  on;
            ssl_protocols              TLSv1 TLSv1.1 TLSv1.2;
            ssl_session_cache          shared:SSL:50m;
            ssl_session_timeout        1d;
            ssl_session_tickets        on;
            resolver                   114.114.114.114 valid=300s;
            resolver_timeout           10s;
            if ($request_method !~ ^(GET|HEAD|POST|OPTIONS)$ ) {
                return           444;
             }
    
            if ($host != 'awen.me' ) {
                rewrite          ^/(.*)$  https://awen.me/$1 permanent;
             }
          add_header  Strict-Transport-Security  "max-age=31536000";
          add_header  X-Frame-Options  deny;
          add_header  X-Content-Type-Options  nosniff;




## 联系我

邮箱: <a href="mailto:wenjun.fang@fangwenjun.com">wenjun.fang@fangwenjun.com</a>








  [1]: https://file.fangwenjun.com/img/2017/03/291378460.jpg_800
  [2]: https://file.fangwenjun.com/img/2017/03/3144630769.jpg_800
