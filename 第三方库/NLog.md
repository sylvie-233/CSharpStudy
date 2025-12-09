# NLog


## 基础介绍

NLog 是一个灵活且强大的日志框架，支持多种日志目标（如文件、数据库、邮件等）和多种日志格式
`dotnet add package NLog`


### nlog.config
```yaml
<nlog>:
    <rules>: # 日志规则
        <logger>:
    <targets>: # 日志输出目标
        <target>:    
            xsi:type:
                AsyncWrapper:
                File:
                Mail:
            <commandText>:
            <connectionStringName>:
            <parameters>:
                <parameter>:
```

配置文件


## 核心内容
```yaml
NLog:
    Logger:
        Error():
        Info():
    LogManager:
```
