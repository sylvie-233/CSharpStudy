# NUnit


## 基础介绍

C# 测试框架
`dotnet add package NUnit`



## 核心内容
```yaml
NUnit:
    Framework:
        [Ignore]: # 暂时忽略该测试
        [OneTimeSetUp]: # 测试生命周期 
        [OneTimeTearDown]: # 测试生命周期
        [SetUp]: # 测试生命周期
        [TearDown]: # # 测试生命周期
        [TestFixture]: # 测试套件
        [Test]: # 测试方法属性
        [TestCase]: # 参数化测试
        [TestCaseSource]: # 
        Assert: # 断言
            AreEqual():
            IsNull():
            IsTrue():
            That():
            Throws():
```