# AutoMapper


## 基础介绍

实体类字段映射库


## 核心内容
```yaml
AutoMapper:
    AutoMapperException:
    IMapper:
    IMappingExpression:
    IValueConverter: # 提供一个简单的转换功能
    IValueResolver: # 自定义映射过程中值转换的接口
    MapFrom:
    Mapper: # 执行对象映射
        Map(): # 实体映射
    MapperConfiguration: # 总的定义和配置映射规则。
        AddProfile():
        AssertConfigurationIsValid():
        CreateMapper():
    Profile: # 定义一组映射规则
        CreateMap(): # 
            ForMember():
    ResolutionContext:
```