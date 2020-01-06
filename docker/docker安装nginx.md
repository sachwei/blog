一、docker pull nginx

二、 docker run -p 80:80 --name mynginx -v $PWD/www:/www -v $PWD/conf/nginx.conf:/etc/nginx/nginx.conf -v $PWD/logs:/wwwlogs -d nginx

出现如下错误提示

```

```

解决步骤：

1、先使用 docker rm myginx删除mynginx容器

2、先不挂载nginx.conf配置文件，docker run -p 80:80 --name mynginx -v $PWD/www:/www -v $PWD/logs:/wwwlogs -d nginx

3、然后使用如下命令进入交互式终端，docker exec -it mynginx /bin/bash

4、然后使用如下命令找到nginx.conf 配置文件

![img](https://images2018.cnblogs.com/blog/1227232/201809/1227232-20180903163646911-1849329149.png)

5、使用exit退出交互终端

6、拷贝nginx.conf到本机

![img](https://images2018.cnblogs.com/blog/1227232/201809/1227232-20180903163845281-1027568362.png)

docker cp 5e2c5ca10074:/etc/nginx/nginx.conf $PWD/conf/nginx.conf

7、此时已经成功配置使用ip+80端口即可访问。但是在修改/root/conf/nginx.conf文件实现负载均衡的时候不起作用。你就发现还没完成任务需要使用docker rm mynginx重新删除nginx容器，再次使用第一次使用的命令重新新建nginx容器

docker run -p 80:80 --name mynginx -v /data/nginx/html:/usr/share/nginx/html -v /data/nginx/conf:/etc/nginx -v /data/nginx/logs:/var/log/nginx -d nginx



docker run \
    --name mynginx \
    -p 80:80 \
    -v /data/nginx/www:/usr/share/nginx/html \
    -v /data/nginx/conf/nginx.conf:/etc/nginx/nginx.conf \
    -v /data/nginx/logs:/var/log/nginx \
    -v /data/nginx/conf.d:/etc/nginx/conf.d \
    -d nginx



8、成功开启nginx服务。使用ip+80端口成功访问，修改/root/conf/nginx.conf配置文件即可生效。


    server {
            listen       80 default_server;
            listen       [::]:80 default_server;
            server_name  118.24.112.95;
            root         /usr/share/nginx/html;
    
            # Load configuration files for the default server block.
            include /etc/nginx/default.d/*.conf;
    
            location / {
            	proxy_pass http://myblog; 
            }
    
            error_page 404 /404.html;
                location = /40x.html {
            }
    
            error_page 500 502 503 504 /50x.html;
                location = /50x.html {
            }
        }
    
        upstream myblog{
        	server 118.24.112.95:80 weight=5;
        }

