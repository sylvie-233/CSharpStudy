# WPF

`WPF入门教程 Visual Studio 2022: P11`

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
        Controls:
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

xaml常用指令：
- x:Static
- x:Type
- Binding
- DynamicResource
- StaticResource






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


#### ControlTemplate
```yaml
<Template>:
    <ControlTemplate>:
        TemplateBinding: # 引用原始属性
        <ContentPresenter>: # 原始内容显示
        <Triggers>: # 样式触发器
            <Trigger>:
        ---
        <Border>: # 边框
```

控件模板
组件插槽，用于修改组件样式
ControlTemplate、TemplateBinding

模板样式绑定，常用于Style中


#### DataBinding
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

DataContext -> Property -> NotifyChanged()

数据绑定：`{Binding xxx}`，属性修改需显式调用`PropertyChanged::Invoke()`重绘界面



#### Command

```csharp
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

ICommand
类似JavaScript代码


### MVVM


`DataContext = MyViewModel`



View -> ViewModel -> Model 类似 View -> Service -> Dao

DataBinding、UIEvent、ModelEvents


ViewModel持有可观测对象`INotifyPropertyChanged`



### Basic Control
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
```


通过控件Name操作控件

#### Layout

布局


##### StackPanel

堆叠
div



##### Grid

网格布局




#### Input

输入组件


##### Button

按钮

##### TextBox

输入框




#### View

显示组件


##### TextBlock
文本块





### User Control

UserControl

用户自定义组件


