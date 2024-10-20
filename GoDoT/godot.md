# GoDoT

>
> `GODOT4.3官方文档：https://docs.godotengine.org/en/stable/getting_started/introduction/key_concepts_overview.html#nodes`
> `【Godot教程】零基础带你从小白到超神：P12`
>
 


## 基础介绍

scene场景 -> node节点树 -> signal信号

scene可进行嵌套（组合node）

每个节点都能添加脚本




## 核心内容
```yaml
Node:
    Viewport:
        Window:
        SubViewport:
    CanvasItem:
        Node2D:
            CollisionObject2D:
            AnimatedSprite2D:
            AudioListener2D:
            AudioStreamPlayer2D:
            Bone2D:
            Camera2D:
            CanvasGroup:
            CollisionPolygon2D:
            Polygon2D:
            RayCast2D:
            ShapeCast2D:
            Sprite2D:
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

### GDScript
```yaml
Node:

```

<br />
<br />

### CSharp
```yaml
Godot:
    AudioServer:
    GD:
        Print(): # 控制台输出
    Input:
        MouseMode:
        MouseModeEnum:
        GetAxis():
        IsActionJustPressed():
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
        FindChild():
        GetParent():
        GetTree():
            CurrentScene:
        QueueFree(): # 销毁节点
        RemoveChild():
    Object:
    OS:
    RefCounted:
    Vector2:
```


<br />
<br />






