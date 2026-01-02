# WebAPI

`.NET 10 Web API 开发：P16`

## 基础介绍

rest api项目框架

### 项目结构
```yaml
webapi:
    /xxx:
        /bin:
        /Controllers:
            WeatherForecastController.cs:
        /obj:
        /Properties:
            launchSettings.json:
        appsettings.Development.json:
        appsettings.json:
        xxx.csproj:
        Program.cs:
        WeatherForecast.cs:
    xxx.sln:
```

#### launchSettings.json
```yaml
launchSettings.json:

```

## 核心内容

### Dependency Inject

依赖注入
#### WebApplicationBuilder
```yaml
WebApplicationBuilder:
    Configuration: # 配置系统
    Environment: # 环境
    Logging: # 日志
    Services: # 服务管理
        AddControllers(): # 注册 Controller 所需的全部核心服务，让 MapControllers() 能工作
    WebHost: # Kestrel / Host 配置
```

应用构建器


#### WebApplication
```yaml
WebApplication:
    MapControllers(): # Controller Action 注册成 Endpoint（自动扫描）
    MapDelete():
    MapGet(): # mini api
    MapPost():
    MapPud():
    Run(): # 运行
    UseAuthentication(): # 中间件 认证管理
    UseAuthorization(): # 中间件 授权管理
    UseHttpsRedirection(): # 中间件 http重定向到https
    UseRouting(): # 根据请求路径 + HTTP Method，匹配一个 Endpoint，并把结果挂到 HttpContext 上
```

Web应用
常用于配置中间件

#### IConfiguration

配置文件读取


### Controller


#### ControllerBase
```yaml
ControllerBase:

```

控制器基类
ControllerBase 是 ASP.NET Core 为 API 控制器准备的“轻量基类”
1. 请求与上下文访问
2. 返回 HTTP 语义化结果
3. 模型绑定 & 验证支持

控制器基类
- Request
- Response
- HttpContext
- User
- RouteData
- ModelState


##### ApiController

控制器注解（自动扫描）
核心功能：
- 自动模型验证
- 参数绑定规则更“严格”
- 更标准的错误返回（ProblemDetails）


#### Route

路由

##### HttpGet
##### HttpPost
##### HttpPut
##### HttpDelete

#### Request

请求


##### FromBody

请求体参数（json）

##### FromForm
##### FromHeader
##### FromQuery

query url参数

##### FromRoute

path 路由参数


#### IActionResult

响应结果


##### BadRequest
##### Ok
##### NotFound
##### StatusCode



#### Pagination

分页


#### Validation

数据校验:
- url数据校验
- json数据校验（在DTO上写注解）

##### URL Validation

##### ModelState

json数据校验结果

##### EmailAddress
##### MaxLength
##### MinLength
##### Range
##### Required

必填参数


##### ValidationAttribute

自定义校验属性

###### ValidationContext
###### ValidationResult

### Filter

过滤器机制

#### IActionFilter

##### ActionFilterAttribute

自定义过滤器属性

###### ActionExecutingContext
```yaml
ActionExecutingContext:
    ActionArguments:
    ModelState:
    Result:
```

###### ValidationProblemDetails

#### IResultFilter
#### AuthorizationFilter
#### ExceptionFilter

### Middleware

#### ExceptionHandler

全局异常处理

#### Routing

路由匹配

#### MapControllers

请求转发匹配的路由

#### Authentication

认证

##### IdentityUser

认证用户基类

##### IdentityRole

##### UserManager

认证用户管理

##### IdentityDbContext

认证EF数据库上下文


##### SignInManager


#### Authorization

授权    


##### Authorize

### Swagger




