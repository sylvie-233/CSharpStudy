# Xunit


## 基础介绍

现代 .NET 单元测试框架
ASP.NET Core 官方模板默认选择


dotnet安装：
```shell
dotnet add package xunit # 测试框架本体（Fact / Theory / Assert）
dotnet add package xunit.runner.visualstudio # 让 VS / Rider 发现 & 运行测试
dotnet add package Microsoft.NET.Test.Sdk # dotnet test 的“桥梁”
```

### dotnet test
```yaml
dotnet test:
    -v:
    --filter:
        FullyQualifiedName:
```

测试运行命令


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
    Assert: # 断言
        Equal():
        False():
        NotNull():
        Null(): 
        Throws(): # 异常断言
        True():
    IClassFixture: # 在测试类的生命周期内共享一个实例
    ICollectionFixture: # 用于跨类共享
    IDisposable:
        Dispose(): # 测试清理
```

### Assert

断言



### Fact
```cs
// 基础测试
public class CalculatorTests
{
    [Fact]
    public void Add_TwoNumbers_ReturnsSum()
    {
        var calc = new Calculator();

        var result = calc.Add(1, 2);

        Assert.Equal(3, result);
    }
}
```

测试方法标注

#### Trait

测试方法标签分类



#### Theory

参数化测试



##### InlineData
```cs
[Theory]
[InlineData(1, 2, 3)]
[InlineData(0, 0, 0)]
[InlineData(-1, 1, 0)]
public void Add_MultipleCases(
    int a, int b, int expected)
{
    var calc = new Calculator();

    var result = calc.Add(a, b);

    Assert.Equal(expected, result);
}
```

内敛数据

##### MemberData
```cs
public static IEnumerable<object[]> AddCases =>
    new[]
    {
        new object[] { 1, 2, 3 },
        new object[] { 2, 3, 5 }
    };

[Theory]
[MemberData(nameof(AddCases))]
public void Add_WithMemberData(int a, int b, int expected)
{
    Assert.Equal(expected, new Calculator().Add(a, b));
}
```



成员数据



### Fixture

测试共享上下文



#### IClassFixture
```cs
public class DbFixture
{
    public DbFixture()
    {
        // 初始化一次
    }
}

public class UserTests : IClassFixture<DbFixture>
{
    public UserTests(DbFixture fixture)
    {
    }
}
```

同一个测试类共享


#### CollectionFixture
```cs
[CollectionDefinition("Database")]
public class DbCollection : ICollectionFixture<DbFixture> { }

[Collection("Database")]
public class UserTests { }

[Collection("Database")]
public class OrderTests { }
```

多个类共享





### Mock

