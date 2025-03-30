# GoDoT

>
> `GODOT4.x官方文档：`
> ``
>
 


## 基础介绍


场景`.tscn`
scene场景 -> node节点树 -> signal信号
scene可进行嵌套（组合node、预制体）、基于scene进行组件封装

每个节点都能添加脚本
全局脚本：项目设置 -> 自动加载



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
            AnimatedSprite2D: # 动画精灵图2D
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
```yaml
Godot:
    @GDScript:
        INF:
        NAN:
        load(): # 导入其他资源
        preload(): # 导入其它模块
    @GlobalScope:
        $: # 获取node节点（根据name）
        Input:
        ProjectSettings:
        print(): # 控制台输出
        str(): # 转换为字符串
    bool:
    float:
    int:
    AABB:
    Array: # 数组
        append(): # 追加元素
        append_array():
        erase(): # 删除元素
        is_empty():
        push_back():
        push_front():
        remove_at():
        resize():
        size(): # 数组大小
        slice(): # 截取
    Basis:
    Callable: # 可调用对象
        bind():
        call():
        call_deferred():
    Color:
    Dictionary: # 字典
        clear():
        erase():
        has():
        is_empty():
        keys():
        size():
        values():
    Error: # 异常基类
    NodePath:
    Object:
        connect(): # 连接信号
        disconnect(): # 断开 信号
        duplicate(): # 对象拷贝
        emit_signal(): # 触发信号
        free(): # 立即释放
        get_class():
        get_node(): # 获取子节点
        is_connected():
        get(): # 读取 属性
        get_meta():
        get_signal_list():
        queue_free(): # 安全释放
        new(): # 实例化类
        set(): # 设置 属性
        set_script(): # 动态绑定脚本
        ---
        AudioServer:
        CameraServer:
        ClassDB:
        DisplayServer:
        EditorFileSystemDirectory:
        EditorInterface:
        GDExtensionManager:
        Geometry2D:
        Input: # 输入
            get_action_strength():
            get_axis(): # 方向按键
            is_action_just_pressed(): # 按键 按压
            is_action_just_released(): # 按键 释放
        InputMap:
        IP:
        JavaClassWrapper:
        JavaScriptBridge:
        JNISingleton:
        JSONRPC:
        MainLoop: # 事件循环
            SceneTree: # 场景树
                change_scene(): # 切换场景
                change_scene_to():
        Marshalls:
        NativeMenu:
        NavigationServer2D:
        Node: # 节点
            name:
            owner:
            _init(): # 构造函数
            _enter_tree(): # 进入节点树
            _ready(): # 当节点及其所有子节点准备就绪时调用
            _process(): # 每帧调用，用于处理逻辑更新
            _physics_process(): # 每帧调用，用于物理计算
            _exit_tree(): # 节点从场景树移除时调用
            _input():
            _notification():
            _unhandled_input():
            add_child(): # 添加子节点
            add_to_group():
            find_child():
            find_parent():
            get_groups():
            get_node(): # 获取节点
            get_tree(): # 获取节点树
            process_mode():  
            AnimationMixer:
                AnimationPlayer: # 动画播放
            AudioStreamPlayer: # 音频播放
            CanvasItem:
                modulate: # 颜色
                visible: # 可见性
                y_sort_enabled: # 根据y值确定 z轴排序
                z_as_relative: # z轴排序，相对父级
                z_index: # z轴排序，越高越靠前
                draw_rect():
                draw_string():  
                hide(): # 隐藏
                show(): # 显示
                ---
                Control: # GUI 控件基类
                    clip_contents: # 内容溢出裁剪
                    custom_minimum_size: # 最小尺寸
                    layout_direction: # 布局方向
                    pivot_offset: # 锚点
                    position:
                    size:
                    BaseButton:
                        Button: # 按钮
                            @pressed:
                            text():
                            CheckBox: # 复选框
                            CheckButton:
                            MenuButton:
                            OptionButton:
                        LinkButton: # 链接按钮
                        TextureButton: # 纹理按钮
                    ColorRect:
                    Container: # 容器
                        AspectRadioContainer:
                        BoxContainer:
                            HBoxContainer:
                                alignment:
                            VBoxContainer:
                                ColorPicker: # 颜色选择器
                        CenterContainer: # 居中布局
                        FlowContainer: # 弹性布局
                        GraphNode:
                        GridContainer: # 网格布局
                            columns: # 列数
                        MarginContainer:
                        PanelContainer:
                        ScrollContainer: # 滚动视图容器
                        SplitContainer:
                        SubViewportContainer: # 子视窗容器
                        TabContainer:
                    GraphEdit: # 图
                    ItemList: # 列表渲染
                    Label: # 标签
                        text:
                    LineEdit: # 单行输入框
                    MenuBar: # 菜单栏
                    NinePatchRect: # 九宫格
                    Panel: # 面板，容器
                    Range:
                        ProgressBar: # 进度条
                        Slider: # 滑动条
                        SpinBox: # 数值框
                        TextureProgressBar: # 纹理进度条
                    RichTextLabel: # 富文本标签
                    Separator:
                    TabBar: # 标签栏
                    TextEdit: # 多行输入框
                    TextureRect: # 纹理矩形
                        texture:
                    Tree: # 树状节点
                    VideoStreamPlayer: # 视频播放
                Node2D:
                    global_position:
                    global_rotation:
                    position: # 位置 Vector2
                    rotation: # 旋转
                    scale:
                    skew: # 斜切
                    translate():
                    ---
                    AnimatedSprite2D: # 动画精灵图 
                        @animation_finished:
                        animation: # 动画资源
                        frame: # 当前动画帧
                        speed_scale: # 播放速度
                        play():
                        stop():
                    Camera2D: # 摄像机
                    CollisionObject2D: # 碰撞体
                        collision_layer: # 碰撞层，自己所属
                        collision_mask: # 碰撞遮罩，和谁碰撞
                        Area2D: # 区域，检测
                            @area_entered:
                            get_overlapping_areas():
                        PhysicsBody2D:
                             CharacterBody2D: # 人物
                                is_on_ceiling():
                                is_on_floor():
                                is_on_wall():
                                move_and_slide(): # 根据速度进行移动
                             RigidBody2D: # 刚体，具有物理特性，重力
                                physics_material_override: # 物理材质
                                PhysicalBone2D:
                             StaticBody2D: # 静态物体
                                physics_material_override: # 物理材质
                    CollisionPolygon2D: # 碰撞多边形
                    CollisionShape2D: # 碰撞形状
                        shape: # 形状 Shape2D
                    RayCast2D: # 射线
                    ShapeCast2D: # 形状射线
                    Sprite2D: # 精灵图
                        @frame_changed:
                        @texture_changed:
                        centered:
                        texture: # 纹理 Texture2D
                        get_rect():
                    TileMap: # 地图块
                        tile_set: # 地图集合
            CanvasLayer: # 画布层
            EditorFileSystem:
            EditorPlugin:
            EditorResourcePreview:
            HTTPRequest: # http请求，需借助信号机制完成
                connect():
                    request_completed: # (result, response_code, headers, body)
                new():
                request(): # 发起请求
            MultiplayerSpawner:
            NavigationAgent2D:
            Timer: # 定时器
                @timeout:
                autostart:
                is_stopped():
                start():
                stop():
            TreeItem:
            Viewport: # 视窗
                world_2d:
                push_input():
                SubViewport: # 子视窗
        ProjectSettings: # 项目设置
            get_setting():
            has_setting():
            set_setting():
        RefCounted: # 引用计数Object
            get_reference_count():
            new():
            DirAccess: # 目录操作
                get_next(): # 遍历目录 下一个
                list_dir_begin(): # 遍历目录 开始
                make_dir_absolute(): # 创建目录
                remove_absolute(): # 删除目录
            FileAccess: # 文件操作 res:// user://
                READ: # 读模式
                close(): # 关闭文件
                eof_reached(): # 文件结尾判断
                file_exists(): # 文件存在判断
                flush(): # 刷新缓冲
                get_as_text(): # 获取文件内容
                get_buffer(): # 获取字节数组
                get_length(): # 文件大小
                get_line(): # 按行读取
                open():
                remove_absolute(): # 删除文件
                store_string(): # 写入字符串
            Resource: # 资源文件类
                instantiate(): # 资源实例化
                Animation:
                AnimationNode:
                AudioStream:
                BitMap: # 位图
                Image: # 图片
                    load(): # 加载图片资源
                InputEvent: # 输入事件
                JSON: # json
                    stringify(): # json序列化
                LabelSettings: # 标签设置
                Material:
                Mesh:
                PhysicsMaterial: # 物理材质
                    bounce: # 弹性
                    friction: # 摩擦力
                    rough: # 粗糙
                Script: # 脚本对象
                Shape2D: # 形状
                    CapsuleShape2D: # 胶囊
                    CircleShape2D: # 圆
                    RectangleShape2D: # 矩形
                Texture: # 纹理
                    Texture2D: # 2D纹理
                        AtlasTexture: # 裁剪2D纹理
                            region: # 裁剪区域
                        CompressedTexture2D: # 压缩2D纹理
                        ImageTexture:
                            create_from_image():
                        NoiseTexture2D: # 噪点2D纹理
                TileSet: # Tilemap 的图块库
                World2D:
            StreamPeer:
                StreamPeerTCP: # tcp连接，客户端
                    close():
                    get_data():
                    put_data():
            TCPServer: # TCP 服务器
                listen(): # 端口监听
                new():
                stop():
                take_connection(): # 等待连接
            Thread: # 线程
                new():
                start():
            Tween: # 数值动画
    PackedByteArray: # 字节数组
        get_string_from_utf8(): # 转为字符串
    PackedFloat32Array: # 浮点数数组
    PackedInt32Array: # 整形数组
    PackedStringArray: # 字符串数组 
    Plane:
    Rect2: # 2D 矩形
    Signal:
    String:
        length:
        match():
        num():
        to_utf8_buffer(): # 转换为字节数组
    StringName:
    Transform2D: # 2D 变换
    Variant: # 变体类型（任意类型，默认）
    Vector2: # 
        RIGHT:
        x:
        y:
        angle():
        dot(): # 点乘
        normalized(): # 单位化
    Vector3:
```

每个 GDScript 脚本文件自动成为一个类，并继承它的父节点类型
一个gd脚本就是一个类（类似Java，默认文件名为类名）

借助项目配置的自动加载脚本实现对象单例








#### Data Types
```yaml
DataTypes:
    bool:
    float:
    int:
    null:
    Array:
    String:
    StringName: # 字符串切片
    Nil: # 空类型
```

数据类型主要分为 基本数据类型 和 复合数据类型，此外还有一些 特殊类型
支持自动类型推断



##### String
```python
# 字符串字面量声明
var my_str = "2333"

# 多行字符串
var multiline_string = """
    这是一行
    这是第二行
    这是第三行
"""

# 字符串格式化 %
var message = "我的名字是 %s，今年 %d 岁。" % [name, age]
```


##### Array
```js
var my_array = [1, 2, 3, "hello"]
```

list数组


##### Dictionary
```js
var my_dict = {"name": "Godot", "version": 4.0}
```



#### Control Flow
```yaml
Control Flow:
    @:
        export: # 变量导出
        onready: # 变量延迟初始化
        tool: # 插件类定义
    class_name: # 类名定义
    extends: # 继承类
    signal: # 信号定义（C#中的事件event）
        connect(): # 连接信号
        disconnect(): # 断连信号
        emit(): # 触发信号
    setget: # get/set方法
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
        await: # 等待信号触发
        pass:
        self: # this引用
        super: # 父类引用
        yield: # 协程返回
        and ... or ... not:
        for ... in ...:
        if ... is:
        if ... elif ... else:
        match ...:
        while ...:
            break:
            continue:
    class:
        new():
```

##### Getter Setter
```js
// 定义一个私有变量
var _health: int = 100

// 使用 setget 关键字来定义 getter 和 setter
export var health: int setget set_health, get_health

// setter 方法，用于设置属性值
func set_health(value: int):
    // 在赋值时限制健康值的范围
    _health = clamp(value, 0, 100)  // 限制在 0 到 100 之间
    print("健康值已更新:", _health)

// getter 方法，用于获取属性值
func get_health() -> int:
    return _health
```





##### Exception Handler
```python
# 捕获异常
func _ready():
    try:
        var file = File.new()
        file.open("res://test.txt", File.READ)  # 假设文件不存在
        var content = file.get_as_text()
        print(content)
    except Error as e:
        print("发生错误:", e)
    finally:
        print("无论是否发生错误，都会执行这里的代码")

# 抛出异常
raise Error("年龄不能为负数")
```

try、except、finally
raise




#### Function
```js
func add(a: int, b: int) -> int:
    return a + b
```

支持静态函数、


##### Static Function
```js
// 静态函数 static func
extends Object
class_name Utils  // 定义一个可直接使用的类

static func to_uppercase(text: String) -> String:
    return text.to_upper()
```


静态函数




##### Async Function
```js
async func fetch_data() -> String:
    print("开始加载数据...")
    await _simulate_network_request()
    print("数据加载完毕！")
    return "Hello, Godot!"
```

async、await、yield
异步函数
yield() 等待异步函数执行完成






#### Class


没有接口


##### Extends
```js
class InvalidAgeError extends Error:
    var age: int

    func _init(age: int):
        self.age = age
        message = "年龄 " + str(age) + " 无效，必须是正数！"
```

继承


##### Inner Class
```python
extends Node  # 继承 Node（外部主类）

class InnerClass:  # 定义内部类
    var value: int = 0

    func _init(v: int):
        value = v

    func print_value():
        print("Value is:", value)

func create_inner():
    var obj = InnerClass.new(42)  # 创建内部类的实例
    obj.print_value()  # 输出 "Value is: 42"
```

内部类



#### Attribute
```js
extends Node

var _health: int = 100

// 设置 getter 和 setter
export(int) var health: int setget set_health, get_health

func set_health(value: int):
    _health = clamp(value, 0, 100)  // 限制健康值在 0 到 100 之间

func get_health() -> int:
    return _health
```

export导出给编辑器使用


#### Signal

事件通信机制



 







### Node

Signal节点信号、自定义信号

Group节点分组、类似Unity的标签tag



#### Sprite

精灵图


#### TileMap

瓦片地图



#### Viewport

视窗节点
子视图，可用于 UI、迷你地图、分屏游戏等


#### Timer

定时器


### GUI

Control基类
Container控制布局、





#### Control

控件基类


#### Button


#### Label


#### TextureRect


#### TextEdit



#### PopupMenu


#### Slider


#### Container

常用于布局、View视图展示


##### ScrollContainer



##### HBoxContainer

##### MarginContainer

##### PanelContainer



##### GridContainer



##### TabContainer




#### ItemList

列表视图



#### Window



##### AcceptDialog



##### FileDialog




### Physical

物理
- 刚体（RigidBody / RigidBody2D）；
- 静态物体（StaticBody / StaticBody2D）；
- 运动物体（KinematicBody / KinematicBody2D）；
- 区域（Area / Area2D）；
- 碰撞形状（CollisionShape / CollisionShape2D）；
- 物理材料（PhysicsMaterial / PhysicsMaterial2D）。


CollisionObject2D碰撞体 + CollisionShape2D碰撞形状 实现碰撞检测



#### RigidBody

刚体
用于模拟具有质量、摩擦和弹性的物体。刚体会根据物理引擎计算其运动和碰撞。可以通过设置不同的属性（如 线性和角速度、质量、摩擦力 等）来影响物体的行为


#### StaticBody

静态物体
用于表示不会移动的物体（如地面、墙壁等）。它不会响应力的作用，只用于碰撞检测。


#### CharacterBody

用于 运动物体，并且允许开发者通过脚本控制物体的运动。KinematicBody2D 不受物理引擎的自动影响，它的运动是通过脚本直接控制的，但仍然能够与其他物体碰撞。

#### Area

用于模拟 触发器区域。Area2D 主要用于 感知碰撞区域，比如检测是否有物体进入特定区域。它不像刚体那样响应力，但可以检测与其他物体的交互（如进入区域、离开区域）


#### CollisionShape

用于定义物体的 碰撞形状，可以与 RigidBody2D、KinematicBody2D 或 StaticBody2D 结合使用。CollisionShape2D 可以是 矩形、圆形、胶囊、路径等，定义了物体的物理边界


#### Joint

这些是物理约束组件，用于连接多个物体，模拟它们之间的 连接关系。例如，SpringJoint2D 用于模拟弹簧连接，PinJoint2D 用于固定物体


#### PhysicsMaterial

用于设置 2D 物体的物理属性，如摩擦力、弹性等。你可以将其应用于刚体、静态物体、区域等。通过调整物理材料，改变物体的反应（如碰撞后的反弹效果）

#### RayCast

用于 射线检测，通过从一个点沿一个方向发射射线，检测它与其他物体的碰撞。这对于射击游戏、光线反射/折射、物体拾取等场景非常有用


#### ShapeCast

#### AABB

一种常用的碰撞体积表示方式，它用于描述 物体的包围盒，在物理引擎中经常用来进行 碰撞检测 和 加速碰撞计算。AABB 对象通常作为 碰撞形状 的基础。
在 Godot 中，你可以通过 AABB 类来进行 AABB 计算和碰撞检测

#### DebugDraw

你可以启用物理调试模式，查看物体的 碰撞边界、速度矢量、力的方向 等，帮助你调试物理相关的问题


#### Navigation

寻路





### Animation

动画


#### AnimationPlayer

动画播放器



#### AnimationTree


用于复杂的动画混合和状态机控制


#### AnimatedSprite

精灵动画

#### Tween


用于平滑过渡和插值动画


#### Skeleton

骨骼


### Assets

- `res://`
- `user://`


`tres`、`res`：资源文件


#### PackedScene

场景


#### AudioStreamPlayer

音效特效


#### VideoPlayer



### Effect


#### Camera

摄像机


#### Light

灯光

#### Particles

粒子系统






### Shade


#### ShaderMaterial

Shader 的重要容器，它允许你将自定义的着色器应用到 3D 或 2D 材质 上


#### Shader

存储 顶点着色器（Vertex Shader）和 片段着色器（Fragment Shader）的资源。你可以通过编写 GLSL 代码来实现各种视觉效果


#### ShaderGraph

可视化编辑着色器 的方式，不需要手动编写代码，而是通过图形化界面连接节点来创建着色器


## CSharp
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
    Input: # 输入系统
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






