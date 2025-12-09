# Autofac


## 基础介绍


C# 依赖注入（Dependency Injection, DI）容器
`dotnet add package Autofac`


## 核心内容
```yaml
Autofac:
    ContainerBuilder:
        RegisterType():
            As():
            SingleInstance():
        Build():
    IContainer:
        BeginLifetimeScope():
            Resolve():
```