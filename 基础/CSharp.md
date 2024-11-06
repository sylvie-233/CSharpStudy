# C#

>
>
>



## 基础介绍

### dotnet

```yaml
dotnet:
    --version: # 版本
    new: # 新建项目
        console: 
            -n: # 指定项目名
    run: 运行项目
    watch: 
```

<br />
<br />
<br />

### .csproj

```yaml
<Project>:
    <PropertyGroup>:
        <OutputType>: 
```

<br />
<br />
<br />
<br />

## 核心内容

```yaml
System:
    Collections: # 集合
        Generic:
    IO:
    Linq:
    Text:
    Threading: # 多线程
        Task:
    Array:
        Copy(): 拷贝
        CreateInstance():
        Reverse():
        Sort():
    Console:
        ForegroundColor:
        Clear():
        ReadLine(): 读入一行
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
        GetType():
        ToString():
    Random:
        Next():
    String:
        Length: # 长度
        Equals(): # 字符串比较
    StringBuilder: #可修改字符串
        Capacity: 容量
        AppendLine(): 添加字符串行
        Clear(): 清空
        Insert(): 插入
        Remove(): 移除
        Replace(): 字符串替换
    TimeSpan: 时间
        Subtract():
    Type: 类型
        Name:
```

<br />
<br />
<br />

### 数据类型

- bool
- byte
- int
- long
- decimal
- float
- double
- char
- string
- var: 可变类型
- object: 基类对象

可空类型：`type?`



模板字符串：`$"{xxx}"`


#### enum

枚举类


#### struct

结构体

值类型



<br />
<br />
<br />


### 流程控制

- if
- switch
- while / do..while
- for
- foreach
- try..catch..finally

<br />

#### 异常处理

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










<br />
<br />
<br />

### 函数

访问修饰符：`public`、`protected`、`private`

默认函数参数、输出参数`out`、引用参数`ref`、可变参数`param`

具名传参



#### 函数重载

函数参数个数、类型不同、返回值


#### 函数委托

delegate：保存方法的引用类型


#### 事件


event







<br />
<br />
<br />

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











