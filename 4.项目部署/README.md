# 项目部署
## 开发环境部署
1. 配置域名
2. 配置nginx
3. 微服务启动顺序
4. 执行mysql脚本(root 123456 redis 123456)
### 配置host
```
# 以下是微服务和ip映射
127.0.0.1 paascloud-discovery
127.0.0.1 paascloud-eureka
127.0.0.1 paascloud-gateway
127.0.0.1 paascloud-monitor
127.0.0.1 paascloud-zipkin
127.0.0.1 paascloud-provider-uac
127.0.0.1 paascloud-provider-mdc
127.0.0.1 paascloud-provider-omc
127.0.0.1 paascloud-provider-opc
# 以下Mysql Redis Mq映射
192.168.241.21 paascloud-db-mysql
192.168.241.21 paascloud-db-redis
192.168.241.21 paascloud-mq-rabbit
192.168.241.21 paascloud-mq-rocket
# 以下是域名映射
127.0.0.1 dev-login.paascloud.net
127.0.0.1 dev-admin.paascloud.net
127.0.0.1 dev-mall.paascloud.net
# 以下是后端接口映射
127.0.0.1 dev-api.paascloud.net

```

### host解释说明

- 请不要修改127.0.0.1 的服务名(代码里写死了)
- 可以修改 服务名映射的ip地址
- 二级域名可以随意指定
- 请不要修改一级域名(会影响SSO)
- api域名可根据实际的nginx转发规则自行修改
### nginx配置

```
    server {
        listen       80;
        server_name  dev-admin.paascloud.net;
        location / {
            proxy_pass http://localhost:7020;
        }
    
        error_page   500 502 503 504  /50x.html;
        location = /50x.html {
            root   html;
        }
    }
    server {
        listen       80;
        server_name  dev-login.paascloud.net;
        location / {
            proxy_pass http://localhost:7010;
        }
        
        error_page   500 502 503 504  /50x.html;
        location = /50x.html {
            root   html;
        }
    }
    server {
        listen       80;
        server_name  dev-mall.paascloud.net;
        location / {
            proxy_pass http://localhost:7030;
        }

        error_page   500 502 503 504  /50x.html;
        location = /50x.html {
            root   html;
        }
    }
    server {
	listen       80;
	server_name  dev-api.paascloud.net;
	location ~ {
		proxy_pass   http://localhost:7979;
	}
	error_page   500 502 503 504  /50x.html;
	location = /50x.html {
		root   html;
	}
    }
```

## 微服务启动顺序
1. paascloud-eureka
2. paascloud-discovery
3. paascloud-provider-uac
4. paascloud-gateway
5. 剩下微服务无启动数序要求
## 生产环境部署