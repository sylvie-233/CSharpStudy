# Xunit


## 基础介绍

单元测试框架


## 核心内容
```yaml
Xunit:
    [Fact]: # 标记测试方法，不接受任何参数
        Skip: # 跳过测试
    [InlineData]: # 供测试数据
    [MemberData]: # 用于参数化测试，从静态方法或属性中提供测试数据
    [Theory]: # 标记测试方法，该方法支持参数化测试
    [Trait]: # 测试元数据
    [TestCaseOrderer]: # 指定测试方法的执行顺序
    Assert:
        Equal():
        False():
        NotNull():
        Null():
        Throws():
        True():
    IClassFixture: # 在测试类的生命周期内共享一个实例
    ICollectionFixture: # 用于跨类共享
    IDisposable:
        Dispose(): # 测试清理
```