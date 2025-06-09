# Log4net



## 基础介绍

一个流行的 .NET 日志记录框架
`dotnet add package log4net`



### log4net.config
```yaml
<log4net>:
    <appender>:
        <layout>:
            <param>:
        <param>:
    <root>:
        <appender-ref>:
        <level>:
```

日志配置文件



## 核心内容
```yaml
log4net:
    Config:
        XmlConfigurator:
            Configure():
    ILog:
        Debug():
        Error():
        Info():
    LogManager:
```