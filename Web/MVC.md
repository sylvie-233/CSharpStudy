# MVC

`全网最新最全Net7微服务教程从零基础到精通：P34`

## 基础介绍


MVC框架

默认使用Razor模板引擎
每个子目录可以有自己的 Shared 文件夹，用于存放该子目录下特定的共享资源
_Layout、_ViewImport、_ViewImport页面子目录也支持
Layout布局页面支持继承




### 项目结构
```yaml
mvc:
    /Controllers:
    /Models:
    /obj:
    /Properties:
        launchSettings.json: # 启动配置    
    /Views: # 视图名与控制器名匹配
        /Home:
        /Shared:
            _Layout.cshtml:
            _ValidationScriptsPartial.cshtml:
            Error.cshtml:
        _ViewImports.cshtml: # 共享常用的命名空间
        _ViewStart.cshtml: # 定义默认的布局文件，最先访问
    /wwwroot: # 静态资源文件夹
    appsettings.Development.json:
    appsettings.json:
    Program.cs:
    xxx.csproj:
    xxx.sln:
```


#### launchSettings.json
```yaml
launchSettings.json:

```



## 核心内容
```yaml
Microsoft:
    AspNetCore:
        Builder:
            WebApplication:
                Configuration: # appsettings.json配置
                    GetConnectionString():
                Environment:
                CreateBuilder():
                    Services: # 服务配置
                        AddControllers():
                        AddControllersWithViews(): # 使用控制器、视图
                        AddDbContext(): # 注入EFCore
                        AddEndpointsApiExplorer():
                        AddJsonOptions():
                        AddRazorPages():
                        AddServerSideBlazor(): # Blazor Server支持
                        AddSingleton(): # 注入单例服务
                        AddSwaggerGen():
                        AddTransient(): # 注入多例服务
                        Configure(): # 配置绑定
                        CreateScope():
                            ServiceProvicer:
                    Build():
                MapControllerRoute(): # MVC Controler路由映射规则
                MapControllers():
                MapFallbackToPage():
                MapGet(): # mini api直接映射
                MapGroup():
                MapPost():
                MapRazorPages():
                Run():
                UseAuthorization():
                UseExceptionHandler():
                UseHsts():
                UseHttpsRedirection():
                UseRouting():
                UseStaticFiles():
                UseSwagger():
                UseSwaggerUI():
                UseWebSockets():
        Components:
            Authorization:
                AuthenticationState:
                AuthenticationStateProvider:
                    GetAuthenticationStateAsync():
            Form:
            Routing:
            Web:
                RenderMode:
                Virtualization:
        Http:
            HttpContext:
                Request:
                Response:
        Mvc:
            RazorPages:
                IPageModelActivator:
                PageContext:
                PageModel: # Razor 页面模型
                    OnGet():
                    OnPostAsync():
                    Page(): # 视图响应
                    RedirectToPage(): # 重定向
                PageResult:
                RazorPage:
                RedirectToPageResult:
            [ApiController]:
            [Controller]:
            [FromBody]:
            [HttpGet]:
            [Route]:
                controller:
            ActionResult:
            Controller:
                Index():
                View(): # 放回视图
            ControllerBase:
                HttpContext: # http上下文
                    RequestServices:
                        GetService(): # 手动获取依赖
                BadRequest():
                CreatedAtAction(): # 路由转发
                NoContent():
                NotFound():
            IActionResult:
                ExecuteResultAsync():
            TagHelpers:
            ViewResult:
        OpenApi: # swagger
    Extensions:
        DependencyInjection: # 依赖注入
            IServiceCollection:
            IServiceProvider:
                GetRequiredService():
                GetService(): # 获取依赖服务
            IServiceScopeFactory:
                CreateScope():    
                    ServiceProvider:
            ServiceDescriptor:
            ServiceCollection:
        Options:
        Hosting():
```





### Websocket



### SSE







## Razor

嵌入C#的HTML模板引擎，`cshtml`



### 模板语法
```yaml
Razor:
    @: # 使用变量
    @**@: # 注释
    @{}: # 代码块
        Html:
            Partial(): # 页面引入（部分渲染）
        Json:
        Layout: # 布局文件
        Model: # 模型
        Url:
        ViewBag:
        ViewData: # 视图数据（在页面中默认传递，可直接使用）
        RenderBody(): # 默认插槽，渲染子页面（Layout）
        RenderSection(): # 具名插槽，渲染section块
        RenderSectionAsync(): # 异步渲染section块
    @addTagHelper: # 引入 Tag Helpe
    @await: # 异步调用
    @for: # 列表渲染
    @foreach:
    @functions: # 声明C#函数
    @if ... @else ... @elseif: # 条件渲染
    @inherits: # 继承视图
    @inject: # 依赖注入
    @model: # 绑定模型
    @namespace:
    @page: # 标注 Razor 页面，能直接响应 HTTP 请求
    @raw:
    @section: # 定义块
    @switch ... @case ... @default:
    @using: # 使用命名空间
    @while:
Tag Helpers:
    asp-action:
    asp-area:
    asp-controller:
    asp-for:
    asp-items:
    asp-page: # razor page页面跳转
    asp-route-xxx:
    asp-validation-for:
    asp-validation-summary: # 
```

