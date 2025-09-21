# WPF

## 基础介绍


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
    <Application.Resources>:
        <ResourceDictionary>:
            <ResourceDictionary.MergedDictionaries>:
                <ResourceDictionary>:
                    Source:
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
    <Window.Resources>:
        <Style>:
            <Style.Triggers>:
                <Trigger>:
                    <Setter>:
                    Property:
                        IsMouseOver:
            <Setter>:
                <Setter.Value>:
                    <ControlTemplate>:
                        <ContentPresenter>: # 原内容显示
                Property:
                    FontSize:
                    FontWeight:
                    Height:
                    Width:
            TargetType:
                x:Type:
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

Style类似CSS样式

```xml
<Style TargetType="Button" x:Key="mystyle"></Style>

<Button Style="{StaticResource mystyle}"/>
```

#### ControlTemplate
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


### Basic Control
```yaml
Basic Control:
    <Border>:
    <Button>:
        Click: # 点击事件
            sender: 
            event:
        Content:
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
        <Grid.RowDefinitions>:
            <RowDefinition>:
                Height:
        <Grid.ColumnDefinitions>:
            <ColumnDefinition>:
        Grid.Column:
        Grid.Row:
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



### User Control

UserControl




### MVVM


`DataContext = MyViewModel`



View -> ViewModel -> Model 类似 View -> Service -> Dao

DataBinding、UIEvent、ModelEvents


ViewModel持有可观测对象`INotifyPropertyChanged`
