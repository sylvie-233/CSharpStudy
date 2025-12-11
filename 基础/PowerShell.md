# powershell

## 基础介绍

`.ps1`：powershell脚本文件
`.psd1`：powershell模块清单文件
`.psm1`：powershell模块文件


PowerShell 是建立在 .NET 之上的脚本语言，几乎所有东西都是 .NET 对象。你可以直接 调用 .NET 类、方法、属性、枚举、事件、委托 等等，就像写 C# 一样


`ExecutionPolicy`执行策略：
- Restricted
- RemoteSigned

`$ENV:PSModulePath`模块搜索路径：
- C:\Users\Sylvie233\Documents\PowerShell\Modules：用户模块路径
- C:\Program Files\PowerShell\Modules：全局模块路径
- C:\Windows\system32\WindowsPowerShell\v1.0\Modules：应用安装模块路径


一切皆对象，底层基于 .NET 平台
- Commands: 执行单元（7大分类）
    1. Cmdlet: PowerShell 原生命令，动词-名词格式
    2. Function：PowerShell 函数（脚本定义的命令）
    3. Workflow：工作流命令（PowerShell 5 以前常用）
    4. Alias: 命令别名
    5. Application：外部程序 (.exe, .bat, .cmd)
    6. Script：.ps1 脚本文件
    7. Filter：类似函数的过滤器（少见）
- Variable：变量
    - PSObject
- ScriptBlock：一段 PowerShell 脚本代码（System.Management.Automation.ScriptBlock），可以动态调用
- Process: 进程对象
- Provider：提供程序,把不同的数据源抽象成类似文件系统的导航方式
- Service：主要是 Windows 服务对象
- Job/Runspace：后台任务
- Module：模块


- PS的 .Net Runtime 是随 PowerShell 一起打包的，不依赖系统全局安装
- PS命令不区分大小写
- 支持变量类型声明：`[type]var = value`
- `n 表示换行
- Import-Module导入模块后就可以使用模块中导出的变量、函数了



## 核心内容
```yaml
powershell:
    math:
        Round():
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
    ConvertTo-Json: # object转json
    Copy-Item: # 拷贝内容
    Expand-Archive: # 解压
        –Path:
        -Destination:
    Export-ModuleMember: # 导出模块程序
        -Function: # 导出函数
    ForEach-Object: # 对象遍历
        -Process:
    Format-Table:
        -AutoSize:
    Get-Alias: # 获取别名
    Get-ChildItem: # 获取子元素，可用于查看目录下内容，别名idr
    Get-CimInstance: # 获取系统信息
        -ClassName:
            Win32_BIOS:
            Win32_ComputerSystem:
                Name:
            Win32_LogicalDisk:
            Win32_OperatingSystem:
                Caption:
                OSArchitecture:
                Version:
            Win32_Processor:
                Name:
            Win32_NetworkAdapterConfiguration:
    Get-Command:
        -Module:
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
    Get-Module: # 获取模块信息
        -Name:
        ---
        Name:
        Version:
    Get-NetIPAddress: # 获取网络信息
    Get-NetTCPConnection:
    Get-Process: # 获取进程对象
    Get-PSRepository:
    Get-Service: # 获取所有服务(后台进程)
    Get-Verb:
    Import-Module: # 导入模块
        -Name: # 导入指定的psd1文件
        -Force:
        -Verbose: # 显示命令执行细节
    Install-Module: # 
        -Repository:
    Invoke-WebRequest: # 发起网络请求
        -OutFile:
        -Uri:
    Join-Path: # 路径合并
        -Path:
        -ChildPath:
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
    Register-PSRepository: # 添加pwsh模块仓库
    Remove-Item: # 删除元素
    Remove-Module: # 移除模块
        -ErrorAction:
        -Name:
    Select-Object: # object字段选择
    Set-Content: # 写入内容
    Set-ExecutionPolicy:
    Set-Location: # cd 修改当前工作目录
        -Path:
    Set-StrictMode: # 设置代码严格模式
        -Version:
    Sort-Object: # array对象排序
    Split-Path:
        -Parent: # 获取父目录
    Start-BitsTransfer: # 断点续传
    Start-Service:
    Start-Sleep: # 延时
        -Seconds:
    Stop-Process: # 关闭进程
        -Force:
        -Id:
        -Name:
    Stop-Service: # 
    Test-Connection: # 测试连接
    Test-Path: # 测试路径
        -Path: # 判断路径是否存在
    Where-Object: # array数组过滤
    Write-Host: # 控制台输出
        -ForegroundColor: # 设置前景色
    Write-Output:
    whoami:
```


### DataTypes
```yaml
DataTypes:
    bool:
    int:
    double:
    decimal:
    char:
    string:
        -f: # 字符串格式化
        -match: # 正则表达式匹配
        -replace: # 正则表达式替换
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
```ps1
# 普通字符串
$a = 'Hello $name'

# 模板字符串
$a = "Hello $name"

# 字符串格式化
$a = "{0} {1}" -f "Hello", "World"

# 多行字符串
$txt = @"
Line1
Line2 $name
"@
```


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
```ps1
# 定义PSCustomObject
$user = [PSCustomObject]@{
    Name = "Sylvie"
    Age  = 22
    Lang = "PowerShell"
}

# 添加属性
$user | Add-Member -NotePropertyName Email -NotePropertyValue "test@abc.com"
```

自定义对象、结构化数据对象



### ControlFlow
```yaml
Control Flow:
    &&: # 多个命令执行
    $?: # 上个命令是否执行成功
    $env: # 环境变量
        PSModulePath:
    $ErrorActionPreference: # 异常处理配置
        stop:
    $false: # 布尔False
    $MyInvocation: # ps1脚本调用上下文信息
        MyCommand:
            Name: #
    $null: # 空对象
    $PSScriptRoot: # 脚本执行所在目录
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


#### Comment
```ps1
#   单行注释
s
<# 
    多行注释
#>
```


#### Exception Handler


#### Pipeline

管道



### Function
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


#### Parameter
```ps1
function Get-HelloMessage {
    <#
    .SYNOPSIS
        获取问候消息
    .DESCRIPTION
        返回一个自定义的问候消息
    .PARAMETER Name
        要问候的人的名字
    .EXAMPLE
        Get-HelloMessage -Name "张三"
        返回: "你好，张三！欢迎使用PowerShell模块。"
    #>
    param(
        [Parameter(Mandatory=$true, HelpMessage="请输入要问候的人的名字")]
        [string]$Name
    )
    
    return "你好，$Name！欢迎使用PowerShell模块。"
}
```
`[Parameter(Mandatory=$true)]`: 参数限定



#### ScriptBlock
```ps1
# lambda函数定义
$lambda = { param($x) $x * 2 }
$lambda.Invoke(5)    # 输出 10

# lambda默认参数 $_
1..5 | ForEach-Object { $_ * 3 }

# 立即执行函数
& { "Hello" }
```

脚本块


### Class
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


#### Extends
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
    ModuleVersion: # 模块清单版本号
    Author: # 作者信息
    CompanyName: # 公司信息
    Copyright: # 版权信息 
    Description: # 模块描述
    RootModule: # 根模块 xxx.psm1
    FunctionsToExport: # 导出的函数
    VariablesToExport: # 导出的变量（如果有）
    AliasesToExport: # 导出的别名（如果有）
    PowerShellVersion: # 所需的PowerShell版本
    DotNetFrameworkVersion: # 所需的
    RequiredModules: # 所需的模块（如果有）
    FileList: # 模块中的文件列表
    PrivateData: # 私有数据（包含自定义元数据）
        PSData:
            ReleaseNotes:
```


模块清单文件



#### psm1


模块代码文件

