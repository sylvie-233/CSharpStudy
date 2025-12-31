# YARP

## 基础介绍


Yet Another Reverse Proxy
微软官方的 .NET 高性能反向代理 / API 网关库
- API 网关
- 请求转发
- 负载均衡
- 统一鉴权
- 路由
- Header / Path 重写
- 限流、熔断（配合 Polly）


核心概念：
1. Route（路由规则）
2. Cluster（后端服务组）
3. Transform（请求 / 响应处理）


### appsettings.json
```yaml
appsettings.json:
    ReverseProxy:
        Routes: # 路由规则
            _routeId:
                ClusterId:
                Match:
                    Path:
                Transforms:
                    PathRemovePrefix:
                AuthorizationPolicy: # 认证策略
                RateLimiterPolicy: # 限流策略
        Clusters: # 后端服务集群
            _clusterId:
                LoadBalancingPolicy: # 负载均衡策略
                    RoundRobin:
                Destinations: # 后端服务地址
                    _destinationName:
                        Address:
```


## 核心内容
