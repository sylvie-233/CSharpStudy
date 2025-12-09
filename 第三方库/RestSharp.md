# RestSharp


## 基础介绍


一个强大的、简单易用的 HTTP 客户端库
`dotnet add package RestSharp`


## 核心内容
```yaml
RestSharp:
    RestClient: # http客户端
        Timeout:
        AddDefaultHeader():
        Execute():
            Content:
            IsSuccessful:
        ExecuteAsync():
        UseAfterResponse(): # 响应拦截器
        UseBeforeRequest(): # 请求拦截器
    RestClientOptions: # http客户端配置
        ConfigureMessageHandler:
            
    RestRequest: # http请求
```