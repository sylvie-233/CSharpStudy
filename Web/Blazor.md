# Blazor

``

## 基础介绍


允许使用C#代替JS编写交互式的WEB用户界面
基于WebAssembly技术的WEB开发框架
Blazor Server、Blazor WebAssembly

支持组件封装、同级组件可直接引用


- ComponentBase组件基类



### 项目结构
```yaml
Blazor Server App:
    /bin:
    /Components:
        /Layout:
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
    @rendermode:
        InteractiveServer:
    @typeparam: # 组件属性
    @using:
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



### 生命周期


- OnInitialized
- OnAfterRender
