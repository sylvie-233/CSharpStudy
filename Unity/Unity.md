# Unity

>
>`【Unity教程】零基础带你从小白到超神：P63`
>



## 基础介绍


游戏引擎


- Scene -> GameObject -> Component
- 一个3D对象通常具有 Mesh Filter(网格)、Mesh Renderer(材质)、Mesh Collider(碰撞)、Material(材质)四个组件
- 一个物体有 图层、标签 两个分组
- 一个基础的UI组件具有 Rect Transform(UI属性变换)、Canvas Renderer(UI渲染器)
- Time.deltaTime帧延时



## Scripting
```yaml
Unity:


UnityEditor:
    EditorApplication:
        isPlaying:

UnityEngine:
    AI: # 智能寻路
        NavMeshAgent: # 导航代理组件
            SetDestination(): # 设置寻路终点
    Events:
        UnityEvent:
            Invoke():
    SceneManagement: # 场景管理
        Scene: # 场景
            buildIndex:
            isLoaded:
            name:
            path:
            rootCount:
            GetRootGameObjects(): # 获取场景根节点
        SceneManager: # 场景管理器
            activeSceneChanged: # 
            sceneLoaded:
            sceneUnloaded:
            GetActiveScene():
            LoadScene():
            LoadSceneAsync():
            SetActiveScene():
            UnloadSceneAsync():
        SceneUtility: # 场景管理工具类
            GetBuildIndexByScenePath():
            GetScenePathByBuildIndex():
    UIElements:
        Slider:
            value:
    Animator: # 动画状态机
        deltaPosition:
        Play(): # 播放动画
        SetFloat():
        SetTrigger(): # 设置触发器变量
    AnimatorStateInfo: # 动画状态信息
    Application: # 应用程序
        Quit():
    AsyncOperation: # 异步操作
        progress:
    CharacterController: # 人物控制器
        center:
        isGrounded:
        Move():
    Collider: # 碰撞体
    Debug: # 调试工具
    GameObject:
        layer: # 层级
        scene:
        tag:
        transform:
        AddComponent(): # 添加组件
        CompareTag():
        Destroy():
        Find(): # 物体对象查找
        GetComponent():
        GetScene():
        SendMessage():
        SetActive():
    Input: # 输入系统
        location:
        touchCount:
        GetAxis(): # 获取轴向输入
        GetKey():
        GetTouch():
    LayerMask:
    Physics: # 物理系统
        Raycast(): # 射线碰撞检测
        RaycastAll():
    Quaternion: # 旋转控制
        LookRotation(): # 看向指定方向
        RotateTowards():
    Time:
        deltaTime:
    Transform:
        rotation:
        TransformDirection(): # 改变方向
    Mathf: # 数学工具类
        PI:
        Abs():
        Ceil():
        MoveTowards():
        Round():
    MonoBehaviour: # 基础脚本类
        gameObject:
        transform:
        Awake():
        FixedUpdate():
        GetComponent(): # 获取物体对象上的组件
        LateUpdate():
        OnAnimatorMove():
        OnDisable():
        OnEnable():
        OnGUI:
        Start():
        StartCoroutine(): # 启动协程
        Update():
    Vector3:
        x:
        y:
        z:
        Cross():
        Lerp():
    WaitForSeconds:
```

Unity C# 脚本 


## GameObject

物体对象

- transform组件控制 位置、缩放、旋转


### 2D Object


#### Sprites

##### 9-Sliced
##### Capsule
##### Circle
##### Hexagon Flat-Top
##### Hexagon Pointed-Top
##### Isometric Diamond
##### Square
##### Triangle


#### Physics
#### Tilemap
#### Sprite Shape
#### Pixel Perfect Camera
#### Sprite Mask

### 3D Object


#### Cube

立方体

#### Sphere
#### Capsule
#### Cylinder
#### Plane
#### Quad
#### Text-TextMeshPro
#### Legacy
#### Ragdoll
#### Terrain

地形

#### Tree
#### Wind Zone


### Effects
### Light
### Audio
### Video
### UI
### UI Toolkit
### UI Camera



## Component

组件


### Mesh
### Effects
### Physics
### Physics 2D
### Navigation
### Audio
### Video
### Rendering
### Tilemap
### Layout
### Playables
### Miscellaneous
### Scripts
### Visual Scripting
### Event
### 2D Animation
### Ul Toolkit



## UI

UI系统

- Canvas、EventSystem是UI必备的两个物体
- 所有UI空间都应该挂在Canvas物体下面
- UI组件的位置、长宽是基于锚点的位置计算的、自身的变换是基于轴心点计算的



### Rect Transform

UI属性
- 位置
- 长、宽
- 锚点
- 轴心
- 旋转
- 缩放



### Canvas

画布

画布渲染模式：
- 屏幕空间-覆盖
- 屏幕空间-摄像机
- 世界空间

#### Canvas Scaler

画布缩放模式

#### Graphic Raycaster

画布射线检测





### EventSystem

事件系统




### View

视图容器

#### Panel

面板

#### ListView
#### ScrollView


### Layout Group

布局容器

#### HorizontalLayoutGroup
#### VerticalLayoutGroup
#### GridLayoutGroup


### Widget

控件

#### Button

按钮

#### Dropdown

下拉框

#### Foldout

折叠区域

#### Image

图片

#### InputField

输入框

#### Label

标签

#### ProgressBar

进度条

#### Scrollbar

#### Slider

滑动条

#### Text

文本

#### Toggle

勾选框

#### Toolbar

工具栏


##### ToggleButton

开关按钮

#### TextMeshPro

Unity新UI框架

##### Text


#### VisualElement

所有 UI 的基础类


#### Mask

遮罩

## Input
```yaml
Input:
    mousePosition: # 鼠标位置
    GetAxis(): # 获取轴向输入
    GetKeyDown():
```

输入系统

### Axis

虚拟轴向输入


### Key

键盘输入

#### KeyCode


### Mouse

鼠标输入


## Physics

物理系统


### Collider

碰撞体

碰撞检测：
- OnCollisionEnter(Collision collision)：发生碰撞
- OnCollisionStay(Collision collision)：持续碰撞
- OnCollisionExit(Collisioncollision)：碰撞结束
- OnTriggerEnter(Collider other)
- OnTriggerStay(Collider other)
- OnTriggerExit(Collider other)

- 只有两个物体都有碰撞体组件、才会发生碰撞

#### Collision
#### Sphere Collider

球形碰撞体


### RigitBody

刚体

### Physic Material

物理材质：
- 动态摩擦力
- 静态摩擦力
- 弹力
- 座擦组合
- 反弹合并



### Joint

关节

#### Fixed Joint

固定关节

#### Hinge Joint

铰链关节

#### Spring Joint

弹簧关节



### Ray

射线

- 可通过Camera摄像机获取射线


#### RayCastHit

射线碰撞检测


### Navigation

导航寻路


#### NavMeshAgent

导航代理组件


#### NavMeshObstacle

导航障碍物


#### OffMeshLink

导航网格链接


## Animation

旧版动画系统

### Animation Clip

动画片段`.anim`
- 曲线
- 事件


### Animator

新版动画系统、基于状态机

状态变量类型：
- Float
- Int
- Bool
- Trigger


- 通过设置状态变量，进行过渡
- 支持动画分层、动画混合、子状态机
- 不同的动画层中的 动画片段并行执行

#### Animator Controller

动画控制器、状态机


#### Blend Tree

混合树、动画混合



#### Avatar Mask

动画遮罩、用于不同动画层混合时使用





## Assets

资源系统

### Scene

场景

#### SceneManager

场景管理器


#### SceneUtility

场景管理工具类


### Audio


### Video



## Effect

特效系统

### Camera

摄像机


### Light

灯光


### Particle

粒子

#### Particle System

粒子系统


## Shader


### Material

材质


### Renderer

渲染器


#### Canvas Renderer

画布渲染器、常用于UI组件中

#### Line Renderer

线条渲染器

网格

#### Mesh Filter

网格容器

#### Mesh Renderer

网格渲染器

#### Trail Renderer

拖尾渲染器



## Network

网络











