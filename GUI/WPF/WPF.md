# WPF

``

## 基础介绍


基于xaml的 GUI框架




### 项目结构
```yaml
WPF:
    /bin:
    /obj:
    .csproj:
    App.xaml:
    App.xaml.cs:
    AssemblyInfo.cs:
    MinWindow.xaml:
    MinWindow.xaml.cs:
```


#### App.xaml
```yaml
<Application>:
    StartupUri: # 主窗口界面
    ---
    <Resources>:
        <ResourceDictionary>:
            <MergedDictionaries>:
                <ResourceDictionary>:
                    Source: # 文件路径
```


主应用文件



#### App.config
```yaml
App.config:

```



## 核心内容
```yaml
Microsoft.Win32:
    OpenFileDialog:
        FileName:
        Filter: # 文件过滤
        InitialDirectory: # 初始化目录
        Multiselect:
        SafeFileName:
        ShowDialog():        
System:
    Collections:
        ObjectModel:
            ObservableCollection: # 可观测集合
    ComponentModel:
        INotifyPropertyChanged:
            PropertyChangedEventHandler: # 数据绑定（属性变化通知）
                Invoke():
    Runtime:
        CompilerServices:
            CallerMemberName:
    Windows:
        Controls: # 控件
            Button: # 按钮
            Expander:
                IsExpanded:
            ListView: # 列表视图
                Items:
                    Add():
                    Remove():
                    RemoveAt():
                SelectedIndex:
                SelectedItem:
                SelectedItems:
                Clear():
            UserControls:
        Data:
        Documents:
        Forms:
            DialogResult:
                Ok:
                Yes:
            FolderBrowserDialog:
                InitialDirectory:
                showDialog():
        Input:
            ICommand: # 自定义命令
        Media:
            Animation: # 动画
            Imaging:
        Navigation:
        Shapes:
        Application:
            Current:
                Shutdown(): # 关闭应用
        MessageBox: # 消息框
            Show():
        MessageBoxButton:
            ERROR:
            OK:
        MessageBoxResult:
        RoutedEventArgs: # 事件参数
            Handled:
            OriginalSource:
            RoutedEvent:
            Source:
        Window: # 窗体类
            DataContext: # 数据上下文（数据绑定用）
            WindowState:
                Maximized:
                Minimized:
                Normal:
            Close():
            DragMove():
            InitializeComponent(): # 初始化控件
```


### XAML
```yaml
<Window>:
    <Window.Resources>: # 资源定义
        <Style>:
            BaseOn: # 样式继承
            TargetType: # 作用组件类型
                x:Type:
            x:Key:
            ---
            <Style.Triggers>:
                <Trigger>:
                    <Setter>:
                    Property:
                        IsMouseOver:
            <Setter>: # 属性设置
                Property:
                    FontSize:
                    FontWeight:
                    Height:
                    Width:
                Value:
                    <ControlTemplate>:
                        <ContentPresenter>: # 原内容显示
    x:Class: # 窗口绑定类
    Height:
    Title:
    Width:
    WindowStyle:
```

XAML（eXtensible Application Markup Language）是 WPF 的 UI 声明式语言

xaml常用指令：
- x:Static
- x:Type
- Binding
- DynamicResource
- StaticResource



#### App
#### Window


#### ResourceDictionary
```yaml
<ResourceDictionary>:
    <Style>:
        <Setter>:
            Property:
```


资源字典文件


##### Style
```xml
<Style TargetType="Button" x:Key="mystyle"></Style>

<Button Style="{StaticResource mystyle}"/>
```

Style类似CSS样式
- BaseOn: 样式继承
- StaticResource：
- DynamicResource:


#### ControlTemplate
```yaml
<Template>: # 模板
    <ControlTemplate>: # 控件模板
        TemplateBinding: # 引用原始属性（属性透传）
        <ContentPresenter>: # 原始内容显示
        <Triggers>: # 样式触发器
            <Trigger>:
        ---
        <Border>: # 边框
```

控件模板
组件插槽，用于自定义组件内容样式
ControlTemplate、TemplateBinding


##### Trigger


控件触发器
CSS中的伪元素



### MVVM


`DataContext = MyViewModel`

View -> ViewModel(INotifyPropertyChanged、ICommand、Window) -> Model -> Service -> Dao
DataBinding、UIEvent、ModelEvents


- ViewModel持有可观测对象`INotifyPropertyChanged`
- ViewModel聚合多个Model（Vue中的data属性）
- ViewModle聚合多个ICommand方法（Vue中的methods方法）


#### DataContext

窗口数据上下文

#### Binding
```yaml
Binding:
    Mode: # 绑定模式
        Default:
        OneTime:
        OneWay:
        OneWayToSource:
        TwoWay:
    UpdateSourceTrigger: # 触发模式
        Default:
        Explicit:
        LostFocus:
        PropertyChanged:
```

数据绑定：`{Binding xxx}`，属性修改需显式调用`PropertyChanged::Invoke()`重绘界面
DataContext -> Property -> NotifyChanged()

#### INotifyPropertyChanged

属性变更通知事件
Model数据模型使用


##### DependencyProperty

依赖属性
自定义控件属性（Vue中的defineProps）


#### ICommand
```cs
class MyCommand: ICommand {
    public event EventHandler? canExecuteChanged;

    public bool CanExecute(object? parameter) {
        // 命令是否执行
    }

    public void Execute(object? prameter) {
        // 命令执行逻辑
    }
}
```
ICommand(Vue methods)
普通方法包装

##### CommandManager

注册Command命令




### Layout
```yaml
Basic Control:
    <Border>:
    <Button>:
        Click: # 点击事件
            sender: 
            event:
        Content:
        Style: # 样式
            DynamicResource:
            StaticResource: # 静态资源引用（x:Key）
    <Calendar>:
    <Canvas>:
    <CheckBox>:
    <ComboBox>:
    <ContentControl>:
    <DataGrid>: # 表格组件
        <DataGrid.Columns>:
            <DataGridTextColumn>:
                Binding:
                Header:
        ItemsSource: # 数据源
        SelectedItem:
    <DatePicker>:
    <DockPanel>:
    <DocumentViewer>:
    <Ellipse>:
    <Expander>: # 折叠控件
    <Frame>:
    <Grid>: # 网格布局
        <RowDefinitions>: # 网格 行定义
            <RowDefinition>:
                Height:
        <ColumnDefinitions>: # 网格 列定义
            <ColumnDefinition>:
        Grid.Row: # 组件网格 行索引
        Grid.Column: # 组件网格 列索引
    <GridSplitter>: # 网格分隔线（可拖动）
    <GroupBox>:
    <Image>:
    <Label>:
    <ListBox>:
    <ListView>: # 列表视图
        ItemsSource:
    <MediaElement>:
    <Menu>: # 菜单栏
        <MenuItem>: # 菜单项（可嵌套）
            Header:
    <RadioButton>:
    <Rectangle>: # 矩形
        Fill:
    <ScrollBar>:
    <ScrollViewer>:
    <Slider>:
    <StackPanel>: # 堆叠面板（水平/垂直布局）
        Orientation:
    <TabControl>:
    <TextBlock>: # 文本块
        FontSize:
        Margin:
        Name:
        Text:
    <TextBox>: # 输入框
    <UserControl>: # 自定义控件
        d:DesignHeight:
        d:DesignWidth:

Layout:

```

布局


#### StackPanel
```xml
<StackPanel Orientation="Horizontal">
    <Button Content="A"/>
    <Button Content="B"/>
</StackPanel>
```

堆叠、水平/垂直排列

#### WrapPanel

堆叠换行

#### DockPanel
```xml
<DockPanel>
    <Button DockPanel.Dock="Top" Content="标题"/>
    <Button Content="内容"/>
</DockPanel>
```

停靠布局


#### Grid
```xml
<Grid>
    <Grid.RowDefinitions>
        <RowDefinition Height="50"/>
        <RowDefinition Height="*"/> <!-- 自动填满 -->
    </Grid.RowDefinitions>

    <Button Content="上" Grid.Row="0"/>
    <Button Content="下" Grid.Row="1"/>
</Grid>
```


网格布局

#### UniformGrid




### Widget

控件


#### Button

按钮

#### TextBox

输入框
#### CheckBox

#### Slider

#### TextBlock
文本块

### View

显示组件





#### ScrollViewer

#### ListBox

列表渲染视图
ListBoxItem
ItemTemplate -> DataTemplate

#### DataGrid

表格渲染视图
Columns -> DataGridTextColumn
        -> DataGridTemplateColumn -> CelllTemplate -> DataTempalte


### User Control

UserControl
用户自定义组件，（可复用）


## Prism
```yaml
```


Shell(主窗口) -> Region(区域)


### PrismApplication

主应用 

#### IModuleCatalog

子模块注册


### IModule

子模块

#### IContainerRegistry

容器注册(依赖注入)
- 注入导航视图
- 注入弹出框


### BindableBase

MVVM基类

#### DelegateCommand
#### ViewModelLocator

#### IDialogService

弹出框服务

##### IDialogAware
##### IDialogParameters
##### IDialogResult


### ContentControl

类似`<router-view>`、`<component>`，用于动态组件渲染
常用于和区域绑定



#### IRegionManager

区域管理，动态切换容器


##### NavigationParameters

导航参数

##### NavigationContext
##### IRegionNavigationJournal
##### INavigationAware

导航进入/离开事件
- void OnNavigatedTo(NavigationContext navigationContext);
- bool IsNavigationTarget(NavigationContext navigationContext);
- void OnNavigatedFrom(NavigationContext navigationContext);

##### IConfirmNavigationRequest



### PubSubEvent

事件机制


#### IEventAggregator





## 第三方库

### MvvmLight
### MicrosoftToolkitMVVM
