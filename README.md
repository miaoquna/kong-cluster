# kong-cluster

# 环境

1. docker
2. 熟悉docker-compose

# 安装

安装已提供了集成环境，可以使用 docker-compose 直接安装不再提供安装步骤

# 端口解释

默认情况下，Kong会侦听以下端口：

    8000 在其上侦听来自客户端的传入HTTP流量，并将其转发到您的上游服务。
    8443 Kong监听传入的HTTPS流量。此端口具有与端口类似的行为:8000，但它仅需要HTTPS流量。可以通过配置文件禁用此端口。
    8001 在其上的管理员API用于配置监听，公共配置接口的端口。
    8444 Admin API侦听HTTPS流量的位置。

# 快速使用

## 1、服务管理

    这是Kong用来指代它管理的上游API和微服务的名称。

### 1.1、通过接口添加服务

接口地址参考：https://docs.konghq.com/1.2.x/admin-api/#service-object

```
// 请求内容
curl -i -X POST \
--url http://localhost:8001/services/ \
--data 'name=example-service' \
--data 'url=http://mockbin.org'

// 响应内容
HTTP/1.1 201 Created
Content-Type: application/json
Connection: keep-alive

{
   "host":"mockbin.org",
   "created_at":1519130509,
   "connect_timeout":60000,
   "id":"92956672-f5ea-4e9a-b096-667bf55bc40c",
   "protocol":"http",
   "name":"example-service",
   "read_timeout":60000,
   "port":80,
   "path":null,
   "updated_at":1519130509,
   "retries":5,
   "write_timeout":60000
}
```

### 1.2、通过ｋｏｎｇａ－ｗｅｂ界面来管理

![Alternate text](doc/image/addservices.png)
![Alternate text](doc/image/addservices_1.png)

## 2、路由管理

    在开始向服务发出请求之前，您需要为其添加路由。 路由指定请求在到达Kong后如何（以及是否）发送到其服务。 单个服务可以有多个路由。

### 2.1、通过接口添加路由
```

```