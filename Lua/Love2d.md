# Love2d

``

## 基础介绍

Lua 2D游戏引擎
支持图像、音频、物理、输入、窗口控制等
可跨平台运行（Windows / macOS / Linux / Android 等）


Love2D 默认寻找 main.lua 作为程序入口

### love
```yaml
love:

```

love2d 运行命令


## 核心内容
```yaml
love:
    audio:
        newSource():
            play():
            setLooping():
    data:
    event:
    filesystem:
    font:
    graphics:
        print(): # 绘制文本
        rectangle(): # 绘制矩形
            line:
    image:
    joystick:
    keyboard: # 键盘
        isDown(): # 按键
            right:
    math:
    mouse:
    physics:
    sound:
    system:
    thread:
    timer:
    touch:
    video:
    window:
    draw(): # 生命周期
    keypressed():
    load(): # 生命周期
    mousepressed():
    quit(): # 退出
    update(): # 生命周期
```


### Lifecycle

生命周期钩子