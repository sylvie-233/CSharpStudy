# Blender

`Blender4.0建模入门教程：P84`

## 基础介绍

3D建模软件


核心操作：
- 网格：点、线、面
- 曲线：


游标Cursor用于物体定位


### 菜单栏
```yaml
Blender:
    File:
    Edit:
        Preferences: # 偏好设置
    Render:
    Window:
    Help:
    Layout:
    Modelling:
    Shading:
    Animation:
    Rendering:
    Scripting:
```



### 工作模式
```yaml
Blender:
    Object Mode: # 物体模式
        View:
        Select:
        Add:
        Object:
    Edit Mode: # 编辑模式
        View:
        Select: # 选择
            Checker Deselect: # 间隔式弃选
            Select Loops:
                Edge Loops: # 循环边
                Edge Rings: # 并排边
        Add:
        ---
        Mesh: # 网格
            Normals:
                Flip: # 法线翻转
        Vertex: # 顶点
            New Edge/Face From Vertices: # 由顶点创建边/面
        Edge: # 边
            Bridge Edge Loops: # 桥接循环边
        Face: # 面
            Poke Faces: # 尖分面
            Fill: # 填充
            Grid Fill: # 栅格填充
        UV:
        ---
        Curve:
        Control Points:
        Segments:
        ---
        Proportional Editing: # 衰减编辑
    Sculpt Mode:
    Vertex Paint:
    Weight Paint:
    Texture Paint:
    Viewport Gizmos:
    Viewport Overlays:
```











### 工具栏
```yaml
Blender:
    Object Mode: # 物体模式
        Select:
            Tweak: # 调整
            Select Box: # 框选
            Select Circle: # 刷选
            Select Lasso: # 套索
    Edit Mode: # 编辑模式 工具栏
        Vertex/Edge/Face:
            Extrude: # 挤出
                Extrude Region: # 挤出面
                Extrude Manifold: # 挤出流形
                Extrude Along Normals: # 挤出沿法线
                Extrude Individual: # 挤出各个面
                Extrude To Cursor: # 挤出至光标
            Inset Face: # 内插面
            Bevel: # 倒角
            Loop Cut: # 环切
            Knife: # 切割
            Poly Build:
            Spin:
            Smooth:
            Edge Slide:
            Shrink/Fatten:
            Shear:
            Rip Region:
        Curve: # 曲线
            Draw:
            Curve Pen: # 曲线笔，钢笔工具
            Extrude:
            Radius:
            Tilt:
            Shear:
            Randomize:
```


### 上下文菜单
```yaml
Blender:
    Edge:
        Edge Crease: # 边线折痕
    Face:
        Subdivide: # 细分
        Dissolve Faces: # 融并面
        Delete Faces: # 删除面
    Object:
        Convert To: # 物体转换
        Join: # 合并
    Vertex:
        Merge Vertices: # 合并顶点
```



### 快捷键
```yaml
Blender:
    ctrl:
        b: # 倒角
    shift:
        d:
    k: # 切割
    n: # 侧边栏
    x: # 删除
```







## 核心内容
```yaml
Blender:
    Camera: # 摄像机
        Object:
            Transform: # 变换
            Viewport Display: # 视图显示
    Constraints: # 常量
    Curve: # 曲线
        Bezier: # 贝塞尔曲线
            Data: # 常用于曲线
                Shape: # 形状
                Texture Space: # 纹理空间
                Geometry: # 几何数据
                    Extrude: # 挤出
                    Bevel: # 倒角
                        Round: # 圆形
                            Depth: # 深度
                            Resolution: # 细分
                        Object: # 指定物体形状
                Animation:
                Custom Properties:
            Object:
        Circle: # 圆形
        Path: # 路径
    Empty: # 空物体
        Arrows:
        Single Arrow:
    Image:
    Light:
    Material: # 材质
    Mesh: # 网格
        Circle: # 圆
        Cone: # 圆锥
        Cube: # 立方体
            Transform: # 变换
            Viewport Display: # 视图显示
        Cylinder: # 圆柱体
        Grid: # 网格
        Monkey:
        Plane: # 平面
        Torus: # 圆环
    Modifier: # 修改器
        Edit: # 编辑
        Generate: # 生成
            Array: # 阵列修改器
                Count: # 数量
                Relative Offset: # 相对偏移
                Constant Offset: # 恒定偏移
                Object Offset: # 物体偏移，常使用空物体做参考
                Merge: # 合并
            Bevel: # 倒角
                Vertices:
                Edges:
                Profile:
                Geometry:
                Shading:
            Boolean: # 布尔修改器
                Intersect: # 交集
                Union: # 并集
                Difference: # 差集
            Mirror: # 镜像生成器
                Axis: # 轴
                Bisect: # 切分
                Flip: # 翻转
            Solidify: # 实体化
                Thickness: # 厚度
            Subdivision Surface: # 表面细分器
        Deform: # 形变
            Smooth: # 光滑形变器
        Normals:
        Physics: # 物理
        Hairs:
    Physics: # 物理
    Viewport: # 视口
        Overlays: # 视图叠加层
```


### Scene




### World



### Collection


### Object


### Mesh



### Modifier



### Paticle




### Animation




### Physics



### Material


### Script

