# Unity

>
>`【Unity教程】零基础带你从小白到超神：P39`
>



## 基础介绍


游戏引擎


- Scene -> GameObject -> Component
- 一个3D对象通常具有 Mesh Filter(网格)、Mesh Renderer(材质)、Mesh Collider(碰撞)三个组件



## Scripting
```yaml
Unity:


UnityEditor:
    EditorApplication:
        isPlaying:

UnityEngine:
    Events:
        UnityEvent:
            Invoke():
    SceneManagement:
        SceneManager:
            sceneCount:
            LoadScene():
            LoadSceneAsync():
    UIElements:
        Slider:
            value:
    Animator: # 动画控制器
        deltaPosition:
        SetFloat():
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
        GetComponent():
        GetScene():
        SendMessage():
        SetActive():
    Input: # 输入系统
        location:
        touchCount:
        GetAxis():
        GetKey():
        GetTouch():
    LayerMask:

    Quaternion: # 旋转
        LookRotation():
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
        GetComponent():
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


## GameObject

物体对象


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






## Input



## Physics







## Animation

动画控制器、动画片段

动画播放能添加事件



## Assets


### Audio


### Video



## Effect




## Shader



## Network













