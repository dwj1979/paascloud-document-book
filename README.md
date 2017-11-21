## paascloud 实战项目

### 项目介绍
```
spring cloud + vue 全家桶，SPA动静分离，由用户认证中心、主数据中心、订单中心、对接平台组成.
```
### 特殊说明


```
由于微服务的拆分受制于服务器，这里我做了微服务的合并，比如OAuth2的认证服务中心和用户中心合并，统一的one service服务中心和用户认证中心合并，支付中心和订单中心合并，其实这也是不得已而为之，只是做了业务微服务中心的合并，并没有将架构中的 注册中心 监控中心 服务发现中心进行合并，这里做一个解释，不喜勿喷
```


### 作者介绍
```
Spring Cloud 爱好者,现就任于鲜易供应链平台研发部.
```
### 传送门
- 博客 http://paascloud.net
- paascloud-admin: http://admin.paascloud.net
- paascloud-mall: http://mall.paascloud.ent
- paascloud-api: http://api.paascloud.xin
- paascloud-document: http://document.paascloud.xin
- github: https://github.com/paascloud

### 架构图

![项目架构图](/assets/PaasCloud架构图.png)