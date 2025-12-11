# C#

>
>
> `net6全栈教程--c#高级：P38`

## 基础介绍

nuget包
(1)sln（解决方案）-> (n)csproj（项目）


.NET Framework 传统项目默认引入：
- System;
- System.Collections.Generic;
- System.Linq;
- System.Text;
- System.Threading.Tasks;


.NET 6+ 的默认引入：
- System
- System.Collections.Generic
- System.IO
- System.Linq
- System.Net.Http
- System.Threading
- System.Threading.Tasks
- System.Console（隐式可用）
- System.Text
- System.Globalization


- 环境变量NUGET_PACKAGES：nuget安装包默认缓存路径（默认:`\Users\~\.nuget\packages\`）
- dotnet build生成中间产物`bin/Debug/net7.0/`、dotnet publish生成最终产物`bin/Debug/net7.0/publish/`
- vscode格式化C#代码，使用`.editorconfig`在根目录
- `global using`Program.cs中全局导入，各个子命名空间都可用



### 项目结构
```yaml
项目结构:
    /.config:
        dotnet-tools.json: # tool工具声明
    /bin: # 构建二进制文件
        /Debug:
            /net9.0:
                xxx.deps.json: # 包依赖描述
                xxx.dll: # 核心二进制文件
                xxx.exe:
                xxx.pdb:
                xxx.runtimeconfig.json:
        /Release:
    /obj:
        /Debug:
        /Release:
        .csproj.nuget.dgspec.json:
        .csproj.nuget.g.props:
        .csproj.nuget.g.targets:
        project.assets.json:
        project.nuget.cache:
    Program.cs: # 项目主程序
    xxx.csproj: # 项目配置
    xxx.sln: # 项目解决方案
```




### sln
```yaml
sln:
    VisualStudioVersion:
    Project: # 引用项目
    Global:
```

项目解决方案（多项目管理）




#### csproj
```yaml
<Project>:
    SdK: # .NET SDK配置
        Microsoft.NET.Sdk: # 控制台/类库
        Microsoft.NET.Sdk.Razor: # Blazor
        Microsoft.NET.Sdk.Web: # ASP.NET Core
    <ItemGroup>: # 对象配置组
        <Compile>: # 编译行为
            Remove:
        <Content>:
            CopyToOutputDirectory:
            Include:
        <None>:
        <PackageReference>: # 包引用（本地包、第三方包）
            Include:
            Version:
    <PropertyGroup>: # 属性配置组
        Condition: # 条件配置
        <AssemblyName>: # 生成的 DLL/EXE 名
        <Authors>:
        <Company>:
        <DefineConstants>: # 自定义条件编译宏：如 DEBUG;TRACE
        <Description>:
        <GeneratePackageOnBuild>: # 生成pack
        <ImplicitUsings>: # 自动导入常用命名空间（仅 SDK 风格）
        <IsPackable>:
        <LangVersion>: # C# 语言版本，如 latest, preview, 10.0
        <Nullable>: # 启用 C# 的 nullable 引用类型检查
        <OutputType>: # 构建类型：Exe 或 Library
        <PackageId>: # 
        <PackageTags>:
        <PackAsTool>: # 打包成tool包
        <PlatformTarget>: # 指定 x86/x64/AnyCPU 等目标架构
        <RepositoryUrl>:
        <RootNamespace>:
        <TargetFramework>: # 目标框架(net8.0、net6.0、netstandard2.1)
        <ToolCommandName>: # tool 命令名
        <TreatWarningsAsErrors>: # 是否将所有警告当成错误处理
        <Version>:
```

项目配置



### dotnet
```yaml
dotnet:
    --help: # -h
    --list-runtimes: # 列出已安装的运行时版本
    --list-sdks: # 列出已安装的 SDK 版本
    --version: # 查看 .NET SDK 版本
    add:
        package: # 添加第三方包
        reference: # 添加project项目引用
    build: # 项目构建,编译项目或解决方案，生成可供调试和开发使用的中间输出（DLL/EXE）
        -c:
            Release:
    clean: # 项目构建清理 /bin /obj
    ef:
        database:
            update:
        migrations:
            add:
                -c:
    list:
        package: # 列出项目依赖
    new: # 新建项目
        --list: # -l
        classlib:
        console: # 控制台程序
            -n: # 指定项目名
            -o:
        install: # 安装项目模板
        mvc: # mvc项目
        sln: # 解决方案
        tool-manifest: # 生成dotnet-tools.json
        web: # 创建 ASP.NET Core Web 应用
        webapi: # webapi项目
        xunit:
    nuget: # Nuget包
        add: # 添加
            source: # 添加镜像源 (可使用本地地址)   
        list: # 查看
            source: # 查看镜像源
        locals:
            all:
                -l:
        push: # 发布
    pack: # 打包
        -c:
            Release:
    publish: # 发布项目，生成可以部署到生产环境的完整输出，包括依赖文件，必要时包含 .NET 运行时
        -c: # 指定Profile环境
        -r: # 指定运行时，例如：win-x64、linux-x64、osx-x64
        --self-contained: # 独立部署，包含 .NET 运行时
        /p:
            PublishSingleFile: # 打包成单个 exe 文件
    rebuild: # 重新构建clean + build
    remove:
        package: # 移除项目依赖
        reference: # 移除项目引用
    restore: # 安装依赖
    run: # 运行项目
        --project: # 指定运行项目 csproj
    script: # 执行顶层csx脚本
    sdk:
        list:
    sln: # 解决方案
        add: # 添加项目引用
        list: # 列出项目
        remove: # 移除项目引用
    test: # 运行测试
         --filter: # 测试过滤
            FullyQualifiedName:
    tool: # 命令行工具
        install: # 按照命令行工具
            -g:
            --local:
        list:
        uninstall:
        update:
    watch: # 文件监听
        run: # 热重载
    workload:
        install:
```







### nuget
```yaml
nuget package: # nuget包内部结构
    /build: # 构建自动导入
    /content: # 打包时项目的资源（添加到用户项目中）
    /package:
        /services:
            /metadata:
                /core-properties:
                    *.psmdcp:
    /lib:
        /net9.0:
            xxx.runtimeconfig.json:
            xxx.dll:
    /ref: # 编译期引用
        /net9.0:
    /tools: # 脚本工具
        /net9.0:
            xxx.runtimeconfig.json:
            xxx.dll:
    /_rels:
        .rels:
    xxx.nuspec: # 元数据
    [Content_Types].xml:
```

.net 第三方包



#### nuget.config


nuget包管理配置文件




#### nuspec
```yaml
<package>:
    <metadata>:
        <dependencies>: # nuget包依赖
            <group>:
                <dependency>:
                    id:
                    version:
        <authors>:
        <description>:
        <id>:
        <packageTypes>:
            <packageType>:
        <requireLicenseAcceptance>:
        <version>:
        
```


nuget包元数据xml


#### dotnet-tools.json
```yaml
dotnet-tools.json:
    tools: # 安装的tool
        version:
        commands:
    isRoot:
    version:
```


tool工具命令使用声明

#### PM
```yaml
PM:
    Add-PackageSource:
    Find-Package:   
    Get-Package:
    Get-PackageSource:
    Install-Package:
    Install-Product:
    New-Item:
    Remove-PackageSource:
    Restore-Package:
    Set-PackageSource:
    Scaffold-DbContext:
    Uninstall-Package:
    Update-Package:
```

vs控制台nuget包管理工具





## 核心内容
```yaml
System:
    AppDomain:
    Buffers: # 高性能内存池和缓冲区处理（Span、Memory）
    Collections: # 集合
        Concurrent: # 并发集合
        Generic: # 泛型集合
            ArrayList:
            Dictionary:
            HashSet:
            Hashtable:
            LinkedList:
            List:
            ObservableCollection:
            Queue:
            Stack:
    ComponentModel: # 组件模型
        DataAnnotations:
            Schema:
                [Column]: # 数据库映射字段
            [AttributeUsage]:
            [DataType]:
            [Required]: # 必填项
                ErrorMessage:    
            ValitaionAttribute:
        [Browsable]:
        [Category]:
        [DefaultValue]:
        [Description]: # 描述
        [NotifyParentProperty]:
        [ReadOnly]:
        BindingList:
        Component:
        EventDescriptorCollection:
        IEditableObject:
        INotifyPropertyChanged:
        PropertyDescriptor:
        PropertyDescriptorCollection:
        TypeConverter:
        TypeDescriptor:
    Configuration: # 旧式配置文件（app.config）访问
        ConfigurationManager:
            AppSettings:
    Data: # 数据集、表、行等 ADO.NET 基础类
        Common: # 通用数据库接口
        SqlClient:
    DateTime:
    Diagnostics: # 日志、调试、性能计数器、启动外部进程
        Process: # 进程对象
    Dynamic: # 动态对象
    Environment: # 系统信息、环境变量
    Formats:
    GC:
    Globalization:
    IO: # 文件、目录、流的操作
        BinaryReader:
        BinaryWriter:
        Compression:
        Directory: # 目录操作
            CreateDirectory():
            Delete():
            Exists():
            GetFiles():
        File: # 文件操作
            AppendAllText():
            Copy():
            Delete():
            Exists(): # 文件存在判断
            ReadAllLines(): # 文件内容读入（多行） 
            ReadAllText(): # 文件内容读入
            Move():
            WriteAllText(): # 文件内容写入
        FileStream: # 文件流
        MemoryMappedFiles:
        MemoryStream:
        Path:
        Pipes:
        StreamReader: # 流式文本读取
            ReadLine():
        StreamWriter: # 流式文本写入
            WriteLine():
    Linq: # LINQ 扩展方法
        Expressions: # 表达式树
            BinaryExpression:
            Expression:
            MemberExpression:
            MethodCallExpression:
            ParameterExpression:
    Net: # 基础网络支持
        Http:
            HttpClient: # http客户端
                GetAsync():
            HttpRequestMessage: # http请求消息
            HttpResponseMessage: # http响应消息
                Content:
                    ReadAsStringAsync():
            Json:
        Mail:
        Sockets: # socket
            Socket: # socket连接
                Accept(): # 接收连接 Socket
                Bind(): # 端口绑定
                Close():
                Connect():
                Listen(): # 监听端口
                Receive(): # 接收消息
                Send(): # 发送消息
        IpAddress:
        IpEndpoint:
        WebClient:
        WebSockets: # websocket
            CancellationToken:
            ClientWebSocket:
                State:
                CloseAsync():
                ConnectAsync():
                ReceiveAsync():
                SendAsync():
            WebSocketMessageType:
                Close:
            WebSocketState:
                Open:
    Reflection: # 反射
        Assembly: # 程序集（DLL/EXE）
            GetTypes():
            Load(): # 加载程序集
            LoadFrom():
        AssemblyName:   
        BindingFlags:
        CustomAttributeData:
        ConstructorInfo: # 构造函数
            GetParameters():
            Invoke():
        EventInfo:
        FieldInfo: # 字段信息
            GetValue():
            SetValue():
        MemberInfo:
        MethodInfo: # 方法信息
            Name:
            GetCustomAttributes(): # 获取方法上的自定义特性
            Invoke(): # 调用方法
        Module:
        ParameterInfo: # 方法参数
        PropertyInfo: # 属性信息
            Name:   
            GetValue():
            SetValue():
    Runtime: # 运行时
        CompilerServices:    
    Security: # 
        Claims: # 声明式身份
            ClaimsPrincipal:
                Identity:
        Cryptography: # 加密、哈希、签名
        Principal: # 用户/身份验证
    Text: # Text文本
        Json: # Json
            JsonDocument: # json动态访问
                Parse():
            JsonSerializer:
                Deserialize(): # json反序列化
                Serialize(): # json序列化
            JsonSerializerOptions: # 序列化配置
                PropertyNamingPolicy:
                WriteIndented:
        RegularExpressions: # 正则表达式
            RegExp: # 正则表达式
        Encoding: # 文本编码
            UTF8:
                GetBytes():
        StringBuilder:
    Threading: # 多线程并发
        Tasks:
            Parallel:
            Task: # 任务
                Factory:
                    StartNew():
                Delay(): # 异步延时
                Run(): # 运行任务
                Start():
            TaskCompletionSource:
            TaskScheduler:
        BlockingCollection:
        CancellationToken:
        ConcurrentDictionary:
        ConcurrentQueue:
        Monitor:
        Mutex:
        Semaphore:
        Thread: # 线程对象
            IsBackground: # 守护线程
            Priority: # 优先级
            Start():
        ThreadPool: # 线程池
    Xml:
        Serialization:
            XmlSerializer:
    Timers: # 定时器支持
    TimeSpan:
    Activator:
        CreateInstance(): # 动态创建对象
    ArgumentException:
    Array:
        Copy(): # 拷贝
        CreateInstance():
        Reverse():
        Sort():
    Attribute: # 属性
    AttributeTargets: # 属性应用目标
        Class:
        Method:
    Char:
    Console: # 控制台
        ForegroundColor:
        Clear():
        ReadKey():
        ReadLine(): # 读入一行
        WriteLine():
    Convert: # 类型转换
        ToInt32():
    DateTime: # 日期类
        Date:
        DayOfWeek:
        AddDays():
        AddMonths():
    DateTimeOffset:
    Exception: # 异常基类
        Message: # 异常信息
    Guid:
    Int32:
        MaxValue:
        Parse(): # 字符串转int
        ToString(): # 转字符串
    Math:
        Pow(): # 幂
    Object: # 对象基类
        Equals():
        GetType(): # 获取对象类型
        ToString():
    Random:
        Next():
    Stopwatch:
    String: # 字符串
        Length: # 长度
        Equals(): # 字符串比较
    StringBuilder: #可修改字符串
        Capacity: # 容量
        Append(): # 字符串追加
        AppendLine(): # 添加字符串行
        Clear(): # 清空
        Insert(): # 插入
        Remove(): # 移除
        Replace(): # 字符串替换
    TimeSpan: # 时间间隔
        Subtract():
    Tuple: # 元组
    Type: # 类型
        Name:
        GetConstructor(): # ConstructorInfo
        GetCustomAttribute(): # 获取自定义特性
        GetCustomAttributes():
        GetField(): # FieldInfo
        GetMethod(): # MethodInfo
        GetMethods():
        GetProperty(): # PropertyInfo
        GetProperties():
    Uri:
    ValueTuple: # 
```






### Data Types
```yaml
Data Types:
    bool:
    byte:
    int:
    long:
    float:
    double:
    decimal:
    char:
    string: # 字符串
    var: # 可变类型
    object: # 基类对象
```


可空类型：`type?`

模板字符串：`$"{xxx}"`

#### string
```cs
// 模板字符串
string str = $"Method Description: {x.value}";

// 源串
string str = @"
    person = { name = 'Alice', age = 30 }
";

// C# 11 Raw String Literal ：支持插值，一个$对应一个{}
string str = $"""
    Hello {name}
""";
```


字符串


#### enum
```cs
// 枚举定义
enum Status
{
    Pending = 1,
    Approved = 2,
    Rejected = 4
}
```

枚举类
C# 真正的 enum 不允许自定义构造函数


#### struct
```cs
// 结构体定义
struct Point
{
    public int X;
    public int Y;
}
```

结构体

值类型





### Control Flow
```yaml
Control Flow:
    for ...: # for循环
    foreach ... in ...: # for循环迭代遍历
    if ... else if ... else ...: # 条件判断
    as: # 类型强转
    is: # 类型判断
    switch: # 模式匹配
        case:
        default:
            break:
    using: # 命名空间使用，上下文管理
    var: # 自动类型推断
    typeof(): # 获取Type类型 
```


#### Exception
```cs
// try ... catch ... finally ... 异常捕获
try
{
    Console.WriteLine("尝试执行");
}
catch (Exception ex)
{
    Console.WriteLine("捕获异常");
}
finally
{
    Console.WriteLine("无论异常与否都会执行");
}
```

throw抛出异常


#### using
```cs
// 经典 using 用法，资源释放
using (FileStream fs = new FileStream("test.txt", FileMode.Open))
{
    // 使用 fs
    byte[] buffer = new byte[fs.Length];
    fs.Read(buffer, 0, buffer.Length);
}

// 简化写法
using FileStream fs = new FileStream("test.txt", FileMode.Open);

// 异步资源释放 IAsyncDisposable
await using var res = new MyAsyncResource();
```

资源释放、用于处理 实现了 IDisposable 接口的对象
异步资源释放 IAsyncDisposable


#### IEnumerable

可迭代对象
IEnumerable 只负责 提供枚举器（IEnumerator）


##### IEnumerator

IEnumerator 负责 实际遍历元素


##### yield
```cs
public IEnumerable<int> GetNumbers()
{
    yield return 1;
    yield return 2;
}
```

生成器返回


##### IAsyncEnumerable

异步迭代器





#### Linq
```yaml
linq:
    Chunk(): # 数据分块
    Any():
    Where():
    GroupBy(): # 分组
    OrderBy(): # 排序
        ThenBy():
    Distinct():
    Skip():
    Take():
    All():
    Single():
    SingleOrDefault():
    FirstOrDefault():
    Select(): # 字段选择
    ---
    from ... in ...: # 数据选择
        join ... in ...:
        on ... equals:
        into ...:
    where ...: # 条件过滤
    orderby ...: # 排序
        descending:
    select: # 字段选择
```

类SQL查询集合

Linq主要包括三大部分：
- Linq To Objects
- Linq To XML
- Linq To SQL


延迟执行、立即执行


##### Expression

表达式树








### Function

访问修饰符：`public`、`protected`、`private`

默认函数参数、输出参数`out`、引用参数`ref`、可变参数`param`

具名传参

#### Override

函数重载
函数参数个数、类型不同、返回值


#### Lambda
```cs
// 有返回值
Func<int, int> square = x => x * x;

// 无返回值
Action<string> show = s => Console.WriteLine(s);
```

匿名函数


##### Func

`Func<T>`：有返回值

##### Action

`Action<T>`：无返回值


##### Event

事件函数event
多播委托


#### Delegate

函数委托
delegate：保存方法的引用类型，可以new
常用lambda表达式一起使用





#### Generic

泛型函数


#### Extension

扩展函数


#### Async
```cs
// 无返回值
async Task MyAsync()
{
    await Task.Delay(1000);
}

// 有返回值
async Task<int> ComputeAsync()
{
    await Task.Delay(1000);
    return 42;
}
int result = await ComputeAsync();

// 异步事件处理
async void Button_Click(object sender, EventArgs e)
{
    await Task.Delay(500);
    Console.WriteLine("按钮点击事件完成");
}
```

异步函数

异步方法可以返回：
- Task：无返回值
- `Task<T>`：返回值类型 T
- ValueTask / `ValueTask<T>`：轻量型异步任务
- void：仅用于事件处理，不推荐一般使用


##### Task

异步结果封装

##### Parallel

并行执行 for/foreach




### Class


类的访问修饰符：
- public: 任何地方都能访问
- internal: 仅限同一程序集内部访问
- protected: 仅限自身类和子类访问
- private: 仅限类内部访问


构造方法：`this()`,`base()`



#### Getter/Setter

常量属性：`const`、只读属性：`readonly`

#### Extends

继承父类、override重写


#### Abstract

abstract抽象类、abstract抽象方法、virtual虚方法
virtual虚方法：可被子类重写


#### Interface

interface接口


#### Generic
```cs
// 泛型类定义
public class Repository<T> where T : class, new()
{
    private List<T> items = new();

    public void Add(T item) => items.Add(item);

    public IEnumerable<T> All() => items;
}

// 泛型约束
class Repository<T> where T : class
```

泛型类


##### Contravariance
```cs
// 逆变 in（T 只输入，不输出）
public interface IWriter<in T>
{
    void Write(T data);
}
```

逆变 in

##### Covariance
```cs
// 协变 out（T 只输出，不输入）
public interface IReadOnly<out T>
{
    T Get();
}
```

斜变 out


#### Record

简化data class数据类，自带Constructor、Getter、Setter



#### Partial

一个类的定义可以拆开写在多个文件里


#### Attribute
```cs
// 自定义特性
[AttributeUsage(AttributeTargets.Class | AttributeTargets.Method,
                AllowMultiple = false,
                Inherited = true)]
public class MyInfoAttribute : Attribute
{
    public int Level { get; }
    public string Name { get; set; }

    public MyInfoAttribute(int level)
    {
        Level = level;
    }
}

// 使用自定义特性
[MyInfo(3, Name = "Admin")]
class UserController {}

// 反射读取自定义特性
var attrs = typeof(UserController)
    .GetCustomAttributes(typeof(MyInfoAttribute), inherit:true);
foreach (MyInfoAttribute attr in attrs)
{
    Console.WriteLine(attr.Level);
}
```


属性、元信息
常与反射一起使用

##### AttributeUsage

元特性，用于定义属性可在哪些地方使用



#### Reflection

反射

##### Assembly

程序集


### Module


#### NameSpace

命名空间：`namespace`，命名空间一般和项目名相同


### Test



### Concurrency

并发编程


#### Thread

线程

##### ThreadState

线程状态

##### ThreadPool

线程池

##### ExecutionContext

线程执行上下文



#### BlockingCollection



##### ConcurrentDictionary

##### ConcurrentQueue


#### Channel

通道


#### Mutex

互斥锁

##### Monitor
```dart
// 基础使用
object locker = new object();

Monitor.Enter(locker);
try
{
    // 临界区
    Console.WriteLine("Working...");
}
finally
{
    Monitor.Exit(locker);
}

// lock语法糖
lock(locker)
{
    // 临界区
    Console.WriteLine("Working...");
}
```

低级锁 API（Pulse/Wait）
lock语法糖


##### SpinLock

自旋锁



#### Interlocked

原子操作


#### Semaphore

信号量




#### Barrier

线程屏障


#### CountdownEvent

倒计时器，所有线程完成后统一继续


##### ManualResetEvent







### Extension

扩展知识点


#### csx

CSharp脚本文件



默认导入的NameSpace命名空间：
```cs
using System;
using System.IO;
using System.Collections.Generic;
using System.Console;
using System.Linq;
using System.Threading.Tasks;
```


引用csx脚本
```cs
#load "utils.csx"
```


引用nuget包
```cs
#r "nuget: Newtonsoft.Json, 13.0.1"
using Newtonsoft.Json;
```


引用dll文件
```cs
#r @"C:\path\to\MyLib.dll"

using MyLibNamespace;
```


#### CLR

Microsoft .NET 平台中的 运行时环境。
负责管理代码的执行、内存分配、垃圾回收、安全性、异常处理等任务

#### CLI

##### CLS
##### CTS
##### VES

## 设计模式




