# StackExchange.Redis


## 基础介绍


Nuget安装：
```bash
dotnet add package StackExchange.Redis
```


## 核心内容
```yaml
StackExchange.Redis:
    ConfigurationOptions: # 连接配置
        AbortOnConnectFail:
        DefaultDatabase: # 默认数据库
        EndPoints: # 连接端点
        Password: # 连接密码
    ConnectionMultiplexer: # 连接管理器
        IsConnected:
        Connect(): # 连接
        GetDatabase(): # 获取连接数据库
        GetServer():
        GetSubscriber(): # 获取发布/订阅
    IBatch:
    IDatabase: # 连接数据库（核心操作类）
        CreateBatch():
        GetSubscriber():
        CreateTransaction(): # 创建事务
        HashGet():
        HashSet():
        KeyDelete():
        KeyExists():
        ListLeftPush():
        SetAdd():
        SortedSetAdd():
        SortedSetRangeByScore():
        StringGet():
        StringSet():    
    IServer: # 管理命令
        Keys():
    ISubscriber: # 发布/订阅
        Publish():
        Subscribe():
    ITransaction: # 事务
        Execute():
        StringSetAsync():
```