# powershell

## 基础介绍

`.ps1`：powershell脚本文件
`.psm1`：powershell模块文件
`.psd1`：powershell模块清单文件


PowerShell 是建立在 .NET 之上的脚本语言，几乎所有东西都是 .NET 对象。你可以直接 调用 .NET 类、方法、属性、枚举、事件、委托 等等，就像写 C# 一样


`ExecutionPolicy`执行策略：
- Restricted
- RemoteSigned

`$ENV:PSModulePath`模块搜索路径：
- C:\Users\Sylvie233\Documents\PowerShell\Modules：用户模块路径
- C:\Program Files\PowerShell\Modules：全局模块路径
- C:\Windows\system32\WindowsPowerShell\v1.0\Modules：应用安装模块路径


一切皆对象，底层基于 .NET 平台
CmdLet、Function、Alias、Variable
- Commands: 执行单元
    1. Cmdlet: 最小的执行单元，由 .NET 类实现
    2. Function
    3. Workflow
    4. ExternalCommand
    5. Alias: 别名
- Variable：变量
    - PSObject
- ScriptBlock：一段 PowerShell 脚本代码（System.Management.Automation.ScriptBlock），可以动态调用
- Process: 进程对象
- Provider：提供程序,把不同的数据源抽象成类似文件系统的导航方式
- Service：主要是 Windows 服务对象
- Job/Runspace：后台任务
- Module：模块


PS核心数据对象
1. PSObject
2. PSCustomObject
3. ErrorRecord



- PS命令不区分大小写
- 支持变量类型声明：`[type]var = value`



## 核心内容
```yaml
powershell:
    System:
        Collections:
            ArrayList:
                Add():
                AddRange():
                Remove():
                RemoveAt():
                RemoveRange():
        Diagnostics:
        IO:
        Net:
        Security:
            Cryptography:
        Text:
        Threading:
        Array:
            Count: # 数量
            IsFixedSize: # 固定大小
            ForEach(): # 循环遍历
                $_:
        DateTime: # 日期时间
        HashTable:
            Keys:
            Values:
            Add():
            ContainsKey():
            ContainsValue():
            Remove():
        Int32:
        Object:
            GetType(): # 获取类型
        String: # 字符串类型
            Length:
            Trim():
        ValueType:
    Add-Content: # 追加内容
    Add-Member: # 添加成员
        -InputObject:
        -MemberType:
            NoteProperty:
        -Name:
        -Value:
    Clear-Host: # 清屏
    Copy-Item: # 拷贝内容
    ForEach-Object: # 对象遍历
        -Process:
    Get-Alias: # 获取别名
    Get-ChildItem: # 获取子元素，可用于查看目录下内容，别名idr
    Get-Command:
        -Name:
    Get-ComputerInfo:
    Get-Content: # 获取文本内容
    Get-Date:
    Get-ExecutionPolicy:
    Get-Help: # 查看命令帮助文档
    Get-History: # 查看命令历史
    Get-Location: # 获取当前路径
    Get-Member: # 获取对象成员属性、方法
        -InputObject:
        -MemberType:
    Get-NetIPAddress:
    Get-NetTCPConnection:
    Get-Process: # 获取进程对象
    Get-Service: # 获取所有服务(后台进程)
    Get-Verb:
    Import-Module: # 导入模块
        -Name: # 导入指定的psd1文件
        -Verbose: # 显示命令执行细节
    Invoke-WebRequest: # 发起网络请求
        -OutFile:
        -Uri:
    Measure-Command: # 运行时间
    Move-Item: # 移动元素
    New-Item: # 新建元素
        -ItemType: # 元素类型 
            Directory: # 目录
            File: # 文件
        -Name:
        -Path: # 路径
        -Type:
            File:
    New-ModuleManifest: # 新建模块清单文件
    New-Object: # 新建对象
        PSObject:
            -Property:
    Read-Host: # 控制台读入
        -Prompt:
    Remove-Item: # 删除元素
    Set-Content: # 写入内容
    Set-ExecutionPolicy:
    Set-Location: # cd 修改当前工作目录
        -Path:
    Set-StrictMode: # 设置代码严格模式
        -Version:
    Sort-Object: # 对象排序
    Start-BitsTransfer: # 断点续传
    Start-Service:
    Start-Sleep: # 延时
        -Seconds:
    Stop-Service:
    Test-Connection: # 测试连接
    Test-Path: # 测试路径
        -Path:
    Where-Object: # 别名where
    Write-Host: # 控制台输出
    Write-Output:
    whoami:
```


### 数据类型
```yaml
DataTypes:
    bool:
    int:
    double:
    decimal:
    char:
    string:
    datetime:
    null:
    array:
    hashtable:
    list:
    dictionary:
    object:
    pscustomobject:
    --- # 特殊类型
    regex:
    scriptblock:
    securestring:
```

`$`：定义变量
`[Type]`：类型引用



#### String


#### Array
```ps1
# 定义数组
$arr = @(1, 2, 3)

$arr[0]
```

固定大小数组（可使用`+=`添加元素）
数组索引从0开始



#### Hashtable
```ps1
# 定义哈希表
$map = @{
    "Name" = "Sylvie233"
    "Age" = 24
}

$map["Name"]
```

#### Enum
```ps1
# 定义枚举
enum DaysOfWeek {
    Monday
    Tuesday
}

# 使用枚举
$today = [DaysOfWeek]::Monday
Write-Host $today 
```

枚举类

#### PSCustomObject

自定义对象



### 控制流程
```yaml
Control Flow:
    $env: # 环境变量
        PSModulePath:
    $false: # 布尔False
    $null: # 空对象
    $PSVersionTable: # PS版本信息
    $true: # 布尔True
    do ... until ...:
    do ... while ...:
    for ...:
    foreach ... in ...: # 循环遍历
    if ... elseif ... else:
        contains:
        -eq:
        -like:
        -lt:
        -match:
        -ne:
        -notlike:
        -replace:
        -split:
    switch ... default ...:
    try ... catch ... finally ...:
    while ...:
        break:
        continue:
```


#### 注释
```ps1
#   单行注释
s
<# 
    多行注释
#>
```


#### 异常处理


#### 管道



### 函数
```ps1
# 函数声明
function Greet-User {
    param (
        [string]$Name
    )
    Write-Host "Hello, $Name!"
}

# 函数调用
Greet-User -Name "John"
```

`function`：定义函数
`param()`：声明函数参数

支持形参默认值、


#### `[Parameter]`
```yaml
Parameter:
    Mandatory: # 必填参数
    ValueFromPipeline: # 接收管道输入
```
`[Parameter(Mandatory=$true)]`: 参数限定



#### 匿名函数


### 面向对象
```ps1
class Employer {
    [string]$Name
    [int]$Age

    Employer([string]$name, [int]$age) {
        $this.Name = $name
        $this.Age = $age
    }

    [void] SayHello() {
        Write-Host "Hello, my name is $($this.Name) and I am $($this.Age) years old."
    }
}

$employer = [Employer]::new("Jack", 28)
$employer.SayHello()
```


`class`：定义类
`new()`：实例化类对象
`$this`：自身实例引用


#### 继承
```ps1
class Employer: Employee {
    [string]$EmployeeID

    Employer([string]$name, [string]$employeeID) : base($name) {
        $this.EmployeeID = $employeeID
    }
}
```

`:`：类继承



### Service

windows服务



### Provider

把不同的数据源（文件系统、注册表、环境变量等）抽象成类似目录的导航接口


### Module
```ps1
New-ModuleManifest -Path "xxx.psd1" -RootModule "./xxx.psm1"

Import-Module -Name "xxx.psd1"

# 直接使用模块内函数
```

`.psm1`和`.ps1`效果一样
`Import-Module`：导入psm1模块文件

#### psd1
```yaml
psd1:
    Author: # 作者
    FunctionsToExport: # 导出的函数
    ModuleVersion:
    RootModule: # 模块文件位置
```
文件夹、清单文件、模块文件