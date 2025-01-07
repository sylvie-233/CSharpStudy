# GoDoT

>
> `GODOT4.3官方文档：https://docs.godotengine.org/en/stable/getting_started/introduction/key_concepts_overview.html#nodes`
> `戈多翰 Godot4基础教程：P6`
>
 


## 基础介绍


场景`.tscn`

scene场景 -> node节点树 -> signal信号

scene可进行嵌套（组合node、预制体）

每个节点都能添加脚本



### 项目设置
```yaml
项目设置:
    常规:
        应用:
            配置:
            运行:
            启动画面:
        显示:
            窗口:
        音频:
        国际化:
        GUI:
        渲染:
    输入映射:
    本地化:
    自动加载:
    着色器全局量:
    插件:
    默认导入设置:
```









## 核心内容
```yaml
Node:
    :
        Process:
        Editor Description:
        Script: # 脚本
    Viewport:
        Window:
        SubViewport:
    CanvasItem:
        :
            Visibility:
                Visible: # 可见性
            Ordering:
                Z Index: # 图层排序
        Node2D:
            : 
                Transform: # 图层变换属性
                    Position:
                    Rotation:
                    Scale:
                    Skew:
            AnimatedSprite2D: # 动画精灵图
            AudioListener2D:
            AudioStreamPlayer2D: # 2D音频播放
            Bone2D:
            Camera2D: # 摄像机
            CanvasGroup:
            CollisionObject2D:
                Area2D: # 2D区域物体
                CharacterBody2D:
                RigidBody2D:
                StaticBody2D: # 静态物体
            CollisionPolygon2D:
            CollisionShape2D: # 碰撞形状
            CPUParticles2D:
            GPUParticles2D:
            Joint2D:
            Light2D:
                DirectionalLight2D:
                PointLight2D:
            LightOccluder2D: # 灯光阴影
            NavigationRegion2D: # 导航区域
            Path2D:
            Polygon2D:
            RayCast2D: # 物理射线
            ShapeCast2D: # 物理形状射线
            Sprite2D: # 精灵图
                Texture: # 图片
                Offset:
                    Centered:
                    Offset:
                    Flip H:
                    Flip V:
                Animation:
                    Hframes:
                    Vframes:
                    Frame: # 帧
                Region:
                    Rect:
            TileMap: # 瓦片地图
            TouchScreenButton:
        Control:
            BaseButton:
                Button:
                    CheckBox: # 多选框
                    CheckButton:
                    OptionButton:
                LinkButton:
                TextureButton:
            Container:
                BoxContainer:
                    HBoxContainer:
                    VBoxContainer:
                CenterContainer:
                FlowContainer:
                GraphElement:
                GridContainer:
                SplitContainer:
                MarginContainer:
                PanelContainer:
                ScrollContainer:
                SubViewportContainer:
                TabContainer:
            ItemList:
            Label: # 标签
            TextEdit:
            TextureRect: # 图片框
    Node3D:
    AnimationMixer:
        AnimationPlayer:
        AnimationTree:
    AudioStreamPlayer: # 音频播放器
    CanvasLayer:
    HTTPRequest: # 发送Http请求
    MultiplayerSpawner:
    MultiplayerSynchronizer:
    NavigationAgent2D: # 导航代理
```
### Script
#### GDScript
```yaml
Godot:
    @GDScript:
        INF:
        NAN:
        preload(): # 导入其它模块
    @GlobalScope:
        $: # 获取node节点（根据name）
        ProjectSettings:

        print():
        str(): # 转换为字符串
    bool:
    float:
    int:
    AABB:
    Array:
        append():
        append_array():
        erase():
        is_empty():
        push_back():
        push_front():
        remove_at():
        resize():
        size():
    Basis:
    Callable: # 可调用对象
        call():
    Color:
    Dictionary:
        clear():
        erase():
        has():
        is_empty():
        keys():
        size():
        values():
    NodePath:
    Object:
        :
            emit_signal(): # 触发信号
            free():
            get():
            get_meta():
            get_signal_list():
            new(): # 实例化类
        AudioServer:
        CameraServer:
        ClassDB:
        DisplayServer:
        EditorFileSystemDirectory:
        EditorInterface:
        GDExtensionManager:
        Geometry2D:
        Input:
        InputMap:
        IP:
        JavaClassWrapper:
        JavaScriptBridge:
        JNISingleton:
        JSONRPC:
        MainLoop: # 事件循环
            SceneTree: # 场景树
                _props:
        Marshalls:
        NativeMenu:
        NavigationServer2D:
        Node:
            _child_entered_tree():
            _ready():
            _tree_entered():
            _tree_exited():
            name:
            owner:
            get_node(): # 获取节点
            process_mode():  
            _enter_tree(): # 进入节点树
            _exit_tree():
            _input():
            _physics_process():
            _process():
            _ready():
            AnimationMixer:
            AudioStreamPlayer:
            CanvasItem:
                hide():
                show():
                Control:
                    Label:
                        text:
                Node2D:
                    :
                        global_position:
                        global_rotation:
                        position: # 位置
                        rotation:
                        scale:
                        skew:
                        translate():
                    Sprite2D:
                        :
                            _frame_change():
                            centered:
                            get_rect():
            CanvasLayer:
            EditorFileSystem:
            EditorPlugin:
            EditorResourcePreview:
            HTTPRequest:
            MultiplayerSpawner:
            NavigationAgent2D:
            RefCounted:
            Time:
            TreeItem:
        ProjectSettings:
            get_setting():
            has_setting():
            set_setting():
        RefCounted: # 引用计数Object
            get_reference_count():
            Resource:

    Plane:
    Rect2:
    Signal:
    String:
        length:
        match():
        num():
    SstringName:
    Transform2D:
    Variant: # 变体类型（任意类型，默认）
    Vector2:
        x:
        y:
        angle():
        dot(): # 点乘
        normalized(): # 单位化
    Vector3:
```


一个gd脚本就是一个类（类似Java，默认文件名为类名）

借助项目配置的自动加载脚本实现对象单例








##### 数据类型


String



Array数组



Dictionary字典



##### 语法结构
```yaml
:
    @:
        export: # 变量导出
        onready:
        tool:
    class_name: # 类名定义
    extends: # 继承类
    signal: # 信号定义（C#中的事件event）
        connect(): # 连接信号
        disconnect(): # 断连信号
        emit(): # 触发信号
    static: # 静态变量、方法
    enum: # 枚举定义
    const: # 常量定义
    var: # 变量定义
        get:
        set(value):
        ---
        false:
        null:
        true:
    func: # 函数定义
        # comment:
        self: # this引用
        and ... or ... not:
        for ... in ...:
        if ... is:
        if ... elif ... else:
        match:
        pass:
        while ...:
            break:
            continue:
    class:
        new():
```

<br />
<br />




#### CSharp
```yaml
Godot:
    []:
        Export:
    AudioServer:
    Collections:
        Array:
    GD:
        Load(): # 资源加载
        Print(): # 控制台输出
    Input:
        MouseMode:
        MouseModeEnum:
        GetAxis():
        IsActionJustPressed(): # 键盘按键
        IsActionJustReleased():
        IsActionPressed():
        IsKeyPressed():
    InputEvent:
    InputEventKey:
        IsEcho(): # 持续按压
        IsPressed(): # 首次按压
        IsReleased(): # 取消按压
    InputEventMouse:
    Key:
        B:
    Node:
        CanvasItem:
            Node2D:
                Sprite2D:
                    Frame:
                    Position:
                    RotationDegrees:
                    Skew:
                    Texture:
                    Visible:
                    ZIndex:
                    LookAt():
            Control:
        Node3D:
        _EnterTree(): # 进入节点树
        _ExitTree(): # 退出节点树
        _Input():
        _Ready(): # 准备运行钩子
        _PhysicsProcess(): # 物理运行钩子
        _Process(): # 运行钩子
            delta:
        AddChild():
        AddToGroup(): # 加入分组
        Connect(): # 信号连接
        FindChild():
        GetNode():
        GetParent():
        GetTree(): # 获取场景树
            CurrentScene:
            GetNodesInGroup():
        QueueFree(): # 销毁节点
        RemoveChild():
    Object:
    OS:
    PackedScene: # 场景预制体
        Instantiate(): # 实例化场景（生成Node）
    RefCounted:
    SceneTree: # 场景树
        CurrentScene:
        AddChild(): # 添加子节点
        CallGroup(): # 调用分组里指定方法
        ChangeSceneToFile():
        ChangeSceneToPacked():
        GetNodesInGroup(): # 在分组里查找节点
    Vector2:
    GetGlobalMousePosition(): # 获取全局鼠标位置
```

全局脚本：项目设置 -> 自动加载








##### 属性
```yaml
:
    [Export]:
```


##### 信号




 


<br />
<br />






### Node









#### Signal

节点信号


自定义信号


#### Group

节点分组、类似Unity的标签tag




### GUI

Control基类



### Physical

物理

CollisionObject2D：添加对应的碰撞检测形状
RayCast2D：物理射线
RigidBody2D：刚体



#### Camera

摄像机



### Animation

动画



### Assets

- `res://`
- `user://`


### Effect







### Shade




