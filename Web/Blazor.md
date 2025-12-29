# Blazor

``

## 基础介绍


允许使用C#代替JS编写交互式的WEB用户界面
基于WebAssembly技术的WEB开发框架

- Interactive render mode交互渲染模式：Blazor Server、Blazor WebAssembly（默认SSR）
- 支持组件封装、同级组件可直接引用
- 自定义razor组件可通过@using导入使用
- razor中声明的变量默认都是响应式的
- Blazor中与服务器的交互主要是通过blazor.web.js脚本（websocket）进行的




### 项目结构
```yaml
Blazor Server App:
    /bin:
    /Components:
        /Layout: # 布局
            MainLayout.razor:
            NavMenu.razor:
        /Pages:
            Counter.razor:
            Error.razor:
            Home.razor:
            Weather.razor:
        _Imports.razor: # 类似原来的_ViewImports.cshtml
        App.razor: # 主页面
            <ImportMap>:
            <HeadOutlet>:
            <Routes>:
        Routes.razor: # 页面路由
    /obj:
    /Properties:
    /wwwroot:
        /lib:
        app.css:
        favicon.png:
    _Imports.razor:
    App.razor:
    appsettings.json:
    Program.cs:
```


#### Routes.razor
```yaml
Routes.razor: # 路由视图规则配置（类似<route-view>视图显示组件）
    <Router>:
        AppAssembly: # 主应用 Assembly
        <Found>: # 路由匹配成功规则
            Context: # 路由上下文参数
            <RouteView>:
                DefaultLayout:
                RouteData: # 路由上下文参数
            <FocusOnNavigate>:
                RouteData:
                Selector:
```


## 核心内容
```yaml
Blazor:
    @: # 使用变量
    @(): # 变量表达式
    @addTagHelper: # 添加辅助标签
    @attribute: # 使用属性
        [StreamRendering]:
    @bind: # 变量绑定
    @code: # C#代码
        [CascadingParameter]: # 获取级联参数
        [Parameter]: # 组件属性
            ElementReference: # DOM引用
            RenderFragment: # 组件插槽类型（默认ChildContent变量）
                Context: # 插槽作用域
        OnInitialized(): # 初始化钩子
        OnInitializedAsync():
        OnParametersSet():
        OnParametersSetAsync():
        OnAfterRender():
        OnAfterRenderAsync():
        Activity:
            Current:
        Assets: # 资源文件
        Body: # Layout默认插槽
        ComponentBase: # 组件基类
            BuildRenderTree(): # 自定义渲染内容（默认使用razor页面）
        HttpContext:
        StateHashChanged(): # 手动触发UI刷新
    @foreach: # 列表渲染
    @functions:
    @if ... else ...: # 条件渲染
    @implements: # 接口实现
    @inherits: # 模板继承
    @inject: # 依赖注入
        IJSRuntime:
        NavigationManager: # 编程式导航
    @layout: # Layout模板使用
    @namespace: # 命名空间
    @onclick: # 点击事件绑定
    @page: # 标注响应页面，页面 url 路径
    @ref: # DOM引用
    @rendermode: # 组件交互渲染模式（server、client）
        InteractiveServer:
        InteractiveWebAssembly:
    @typeparam: # 组件属性
    @using: # 命名空间使用
    asp-action:
    asp-controller:
    asp-for:
    asp-items:
    asp-page:
    asp-route-xxx:
    asp-validation-for:
    <component>: # 动态组件
        render-mode: # 组件渲染模式
    <environment>:
    <CascadingValue>: # 级联传参（父子组件通信）
    <ErrorBoundary>: # 错误边界 
        <ChildContent>:
        <ErrorContent>:
    <HeadOutlet>:
    <ImportMap>:
    <PageTitle>: # 页面标题
    <Router>: # 路由
        <Found>:
        <NotFound>:
            <RouterView>: # 路由视图 
            <LayoutView>:
            <FocusOnNavigate>:
    _Imports.razor: # 组件引入命名空间
    App.razor: # 主应用（路由配置）
    _Layout.cshtml: # 根布局
        @RenderBody: # 内容渲染
    _Host.cshtml: # 入口页面（引入主应用App）
    Error.cshtml:
```


### Component

组件

#### Lifecycle

生命周期：
- OnInitialized
- OnAfterRender

##### OnInitialized
###### OnInitializedAsync

##### OnParametersSet

路由参数设置成功

#### Binding

属性、事件绑定


#### Rendering

渲染

##### List Render
```jsx
<ul>
@foreach (var item in items)
{
    <li>@item.Name</li>
}
</ul>
```

列表渲染


##### Condition Render
```jsx
// 普通条件渲染
@if (state == 0)
{
    <p>Init</p>
}
else if (state == 1)
{
    <p>Running</p>
}
else
{
    <p>Error</p>
}

// switch多分支条件渲染
@switch (status)
{
    case Status.Success:
        <p>成功</p>
        break;
    case Status.Fail:
        <p>失败</p>
        break;
    default:
        <p>未知</p>
        break;
}
```

条件渲染


#### Widget

内置组件

##### EditForm

表单
###### DataAnnotationsValidator
###### ValidationMessage
###### ValidationSummary

###### InputCheckbox
###### InputNumber
###### InputText


##### HeadOutlet
##### NavLink

链接

##### PageTitle

页面头


### Page

页面



#### Layout
```jsx
@page "/admin/users"
@layout AdminLayout

<h3>User Management</h3>
```

布局页面
@layout手动指定布局页面


##### LayoutComponentBase

布局组件基类



#### Route

页面路由

##### Route Parameter
```jsx
// 路由参数定义
@page "/users/{userId}"

@code {
    [Parameter]
    public string userId { get; set; }
}

// query参数定义
@page "/users"

@code {

    []
    public string? keyword { get; set; }
}
```

路由参数

###### Parameter 
###### SupplyParameterFromQuery
###### SupplyParameterFromForm


##### NavigationManager

编程式导航、依赖注入获取


#### Attribute

##### StreamRendering

流式渲染


### App

应用页面

#### Route

路由页面

##### Router

路由根组件

###### Found
###### NotFound
###### RouterView



#### Dependency Inject

依赖注入

##### NavigationManager

#### Static Resources

静态资源