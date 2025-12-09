# LuaRocks


## 基础介绍

lua包管理工具


vscode集成luarocks安装第三方模块
```json
{
    "Lua.runtime.version": "Lua 5.4",
    "Lua.workspace.library": [
        "~/AppData/Roaming/luarocks/share/lua/5.4",
        "~/AppData/Roaming/luarocks/lib/luarocks/rocks-5.4"
    ],
    "Lua.runtime.path": [
        "?.lua",
        "?/init.lua",
        "~/AppData/Roaming/luarocks/share/lua/5.4/?.lua",
        "~/AppData/Roaming/luarocks/share/lua/5.4/?/init.lua"
    ]
}
```
- Lua.workspace.library：告诉 VSCode第三方库路径，使得require("xxx") 时能找到文件
- Lua.runtime.path：提供代码提示、补全、跳转定义，不影响 require 查找
- 这两个配置常一起使用



不使用环境变量，改为手动加载
```lua
local function init_package()
  -- 把 LuaRocks 路径加入 Lua 搜索路径
  package.path = package.path
    .. ";libs/share/lua/5.4/?.lua"
    .. ";libs/share/lua/5.4/?/init.lua"

  package.cpath = package.cpath
    .. ";libs/lib/luarocks/rocks-5.4/?.dll"
    .. ";libs/lib/lua/5.4/?.dll"
end
```


vsocde调试lua
```json
{
    "version": "0.2.0",
    "configurations": [
        {
            "name": "lua debug",
            "request": "launch",
            "runtimeArgs": "${workspaceFolder}/main.lua",
            "runtimeExecutable": "lua.exe",
            "stopOnEntry": true,
            "type": "lua"
        }
    ]
}
```



- 第三方包默认安装路径：tree `~/AppData/Roaming/luarocks`
- luarocks path设置LUA_PATH、LUA_CPATH环境变量，从而关联第三方模块
- 可使用luarocks install --tree (libs) 安装模块到本地指定目录(libs)
- 安装使用带dll文件的库时，建议使用visual studio自带的cmd运行安装命令



### luarocks
```yaml
luarocks:
    --version: # 版本
    build:
    config:
    help:
    init:
    install: # 安装第三方包
        --tree: # 安装到tree 配置指定的目录
    list:
    path: # 提供lua path路径搜索
    remove:
    search: # 搜索模块
    show:
```



#### Rocks trees
```yaml
Rocks trees:
    /lib: # dll文件
        /luarocks:
            /rocks-5.4:
                /<package>: # 第三方包
    /share: # lua文件
        /lua:
            /5.4:
                /<package>: # 第三方包
```


第三方包安装目录



#### .rockspec
```yaml
.rockspec:
    build:
    dependencies:
    description:
    package:
    source:
        url:
    version:
```

模块配置文件


## 核心内容