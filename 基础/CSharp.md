# C#

>
>
>

## 基础介绍

nuget包
(1)sln（解决方案）-> (n)csproj（项目）


vscode格式化C#代码，使用`.editorconfig`在根目录


常用环境变量
- NUGET_PACKAGES：nuget安装包默认缓存路径（默认:`\Users\~\.nuget\packages\`）



### 项目结构
```yaml
csproj:
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
    Program.cs: # 项目主程序
    xxx.csproj:
    xxx.sln:
```


#### appsettings.json
```yaml
appsettings.json:

```


### dotnet
```yaml
dotnet:
    --help: # -h
    --version: # 版本
    add:
        package: # 添加包
    build:
        -c:
            Release:
    clean:
    list:
        package:
    new: # 新建项目
        --list: # -l
        classlib:
        console: # 控制台程序
            -n: # 指定项目名
            -o:
        mvc:
        sln: # 解决方案
        tool-manifest: # 生成dotnet-tools.json
        webapi:
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
    publish:
    remove:
        package:
    restore: # 安装依赖
    run: # 运行项目
        --project:
    script: # 执行顶层csx脚本
    sdk:
        list:
    sln: # 解决方案
        add: # 添加项目引用
        remove:
    test:
    tool: # 工具包
        install:
            -g:
            --local:
        list:
    watch: 
    workload:
        install:
```


### sln
```yaml
sln:
    VisualStudioVersion:
    Project: # 引用项目
    Global:
```

项目解决方案



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



### nuget
```yaml
nuget:
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

.net 包（类似Java的Jar吧）



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
    ComponentModel: # 组件模型
        DataAnnotations:
            Schema:
                [Column]: # 数据库映射字段
            [DataType]:
            [Required]:
                ErrorMessage:    
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
    Dynamic: # 动态对象
    Environment: # 系统信息、环境变量
    Formats:
    GC:
    Globalization:
    IO: # 文件、目录、流的操作
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
            Exists():
            ReadAllLines():
            ReadAllText():
            Move():
            WriteAllText():
        MemoryMappedFiles:
        Pipes:
        StreamReader: # 流式文本读取
            ReadLine():
        StreamWriter: # 流式文本写入
            WriteLine():
    Linq: # LINQ 扩展方法
    Net: # 基础网络支持
        Http:
            Json:
        Mail:
        Sockets: # socket
            Socket:
                Accept():
                Bind():
                Close():
                Connect():
                Listen():
                Receive():
                Send():
        WebSockets:
    Reflection: # 反射
        Activator:
            CreateInstance(): # 动态创建对象
        FieldInfo: # 字段信息
            GetValue():
        MethodInfo: # 方法信息
            Name:
            Invoke(): # 调用方法
        PropertyInfo: # 属性信息
            Name:
            GetValue():
            SetValue():
        Type: # 类型
            GetCustomAttribute():
            GetCustomAttributes():
            GetField():
            GetMethods():
            GetProperties():
    Runtime: # 运行时
        CompilerServices:    
    Security: # 
        Claims: # 声明式身份
        Cryptography: # 加密、哈希、签名
        Principal: # 用户/身份验证
    Text: # Text文本
        Json: # Json
            JsonDocument: # json动态访问
                Parse():
            JsonSerializer:
                Deserialize: # json反序列化
                Serialize(): # json序列化
            JsonSerializerOptions: # 序列化配置
                PropertyNamingPolicy:
                WriteIndented:
        RegularExpressions: # 正则表达式
    Threading: # 多线程
        Task:
    Timers: # 定时器支持
    TimeSpan:
    Array:
        Copy(): # 拷贝
        CreateInstance():
        Reverse():
        Sort():
    Attribute: # 属性
    AttributeTargets: # 属性应用目标
        Class:
        Method:
    Console: # 控制台
        ForegroundColor:
        Clear():
        ReadLine(): # 读入一行
        WriteLine():
    Convert: # 类型转换
        ToInt32():
    DateTime: # 日期类
        Date:
        DayOfWeek:
        AddDays():
        AddMonths():
    Exception: # 异常类
        Message: # 异常信息
    Int32:
        MaxValue:
        Parse(): # 字符串转int
        ToString(): # 转字符串
    Math:
        Pow(): # 幂
    Object: # 基类
        Equals():
        GetType(): # 获取对象类型
        ToString():
    Random:
        Next():
    String:
        Length: # 长度
        Equals(): # 字符串比较
    StringBuilder: #可修改字符串
        Capacity: # 容量
        AppendLine(): # 添加字符串行
        Clear(): # 清空
        Insert(): # 插入
        Remove(): # 移除
        Replace(): # 字符串替换
    TimeSpan: # 时间
        Subtract():
    Type: # 类型
        Name:

Microsoft:
    AspNetCore:
    Extensions:
        Configuration: # 新式配置（JSON、环境变量等）
        DependencyInjection: # 内建依赖注入容器（DI）
```

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





### 数据类型
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
$"Method Description: {x.value}"

// 源串
@"
    person = { name = 'Alice', age = 30 }
"
```


字符串


#### enum

枚举类


#### struct

结构体

值类型





### 流程控制
```yaml
Control Flow:
    if:
    using: # 命名空间使用，上下文管理
    typeof(): # 获取Type类型 
```


#### Exception

throw抛出异常


#### Linq

类SQL查询集合

```
from 数据源
where 条件
select 查询字段

```

Linq主要包括三大部分：
- Linq To Objects
- Linq To XML
- Linq To SQL


延迟执行、立即执行











### 函数

访问修饰符：`public`、`protected`、`private`

默认函数参数、输出参数`out`、引用参数`ref`、可变参数`param`

具名传参



#### Override

函数重载
函数参数个数、类型不同、返回值


#### Delegate

函数委托
delegate：保存方法的引用类型


#### Event

事件函数
event








### 面向对象

命名空间：`namespace`，命名空间一般和项目名相同




类的访问修饰符：`public`、`internal`

静态属性、静态方法

构造方法、this指针

属性Properties：Getter、Setter

属性、方法访问修饰符：`public`、`protected`、`private`

常量属性：`const`、只读属性：`readonly`


构造方法：`this()`,`base()`


virtual虚方法：可被子类重写

继承父类、override重写

abstract抽象类、abstract抽象方法、virtual虚方法

interface接口


#### Getter/Setter

#### Extends

继承

#### Interface


接口


#### Attribute

属性

#### Reflection

反射

### 模块


#### NameSpace



### 测试



### 并发



### 扩展


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

## 设计模式




