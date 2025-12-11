# YamlDotNet


## 基础介绍

C# yaml文件解析库
`dotnet add package YamlDotNet`

## 核心内容
```yaml
YamlDotNet:
    Serialization:
        NamingConventions:
            CamelCaseNamingConvention:
                Instance:
        DeserializerBuilder: # 反序列化构造器
            Build():
                Deserialize():
            WithNamingConvention(): # 使用命名转换器
        SerializerBuilder: # 序列化构造器
            Build():
                Serialize():
            WithNamingConvention(): # 使用命名转换器
```