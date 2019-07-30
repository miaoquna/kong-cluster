# kong-cluster

# 环境

1. docker
2. 熟悉docker-compose

# 安装

安装已提供了集成环境，可以使用 docker-compose 直接安装不再提供安装步骤

# 端口解释

默认情况下，Kong会侦听以下端口：
:8000 在其上侦听来自客户端的传入HTTP流量，并将其转发到您的上游服务。
:8443 Kong监听传入的HTTPS流量。此端口具有与端口类似的行为:8000，但它仅需要HTTPS流量。可以通过配置文件禁用此端口。
:8001 在其上的管理员API用于配置监听，公共配置接口的端口。
:8444 Admin API侦听HTTPS流量的位置。

# 快速使用

## 服务

    这就是Kong用来指代它管理的上游API和微服务的名称。

### 通过命令行添加
    curl -i -X POST \
  --url http://localhost:8001/services/ \
  --data 'name=example-service' \
  --data 'url=http://mockbin.org'