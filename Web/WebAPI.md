# WebAPI

``

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

#### IConfiguration

配置文件读取


### Controller


#### ControllerBase

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

##### FromQuery

query url参数

##### FromRoute

path 路由参数


#### IActionResult

响应


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


### Filter

过滤器机制

#### IActionFilter
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

#### ApiController


