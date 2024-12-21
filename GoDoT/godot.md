# GoDoT

>
> `GODOT4.3官方文档：https://docs.godotengine.org/en/stable/getting_started/introduction/key_concepts_overview.html#nodes`
> `【Godot教程】零基础带你从小白到超神：P20`
>
 


## 基础介绍

scene场景 -> node节点树 -> signal信号

scene可进行嵌套（组合node、预制体）

每个节点都能添加脚本




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
            AnimatedSprite2D:
            AudioListener2D:
            AudioStreamPlayer2D:
            Bone2D:
            Camera2D:
            CanvasGroup:
            CollisionObject2D:
            CollisionPolygon2D:
            Polygon2D:
            RayCast2D:
            ShapeCast2D:
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
            TileMap:
        Control:
    Node3D:
    AnimationMixer:
        AnimationPlayer:
        AnimationTree:
    AudioStreamPlayer:
    CanvasLayer:
    HTTPRequest:
    MultiplayerSpawner:
    NavigationAgent2D:
```
### Script

#### GDScript
```yaml
Godot:
    float:
    int:
    Array:
    Color:
    Node:
        CanvasItem:
            Control:
                BaseButton:
                    _signals:
                        pressed:
                Label:
                    text: # 标签文本
            Node2D:
                Sprite2D:
            _signals:
                _draw:
            modulate: # 背景色
        Timer:
            _signals:
                timeout:
        _input():
            event:
                is_action_pressed():
        _process(delta):
        _ready():
        get_node():
    String:
    Variant:
    Vector2:
    Vector3:
    clamp(): # 数值截取
    int():
    print():
    randf():
    randf_range():
    randi_range():
    str():
```


##### 语法结构
```yaml
:
    @:
        export: # 变量导出
        onready:
        tool:
    class_name: # 类定义
    extends: # 继承类
    signal: # 信号定义
        connect(): # 连接信号
        disconnect(): # 断连信号
        emit(): # 触发信号
    enum: # 枚举定义
    const: # 常量定义
    var: # 变量定义
        get:
        set(value):
    func: # 函数定义
        # comment:
        for ... in ...:
        if ... is:
        if ... elif ... else:
        match:
        pass:
        while ...:
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
        FindChild():
        GetParent():
        GetTree(): # 获取场景树
            CurrentScene:
        QueueFree(): # 销毁节点
        RemoveChild():
    Object:
    OS:
    PackedScene: # 场景预制体
        Instantiate(): # 实例化场景（生成Node）
    RefCounted:
    SceneTree: # 场景树
        AddChild(): # 添加子节点
        CallGroup():
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

节点信号


节点分组



### Animation

