# NLua


## 基础介绍

Lua 操作库


## 核心内容
```yaml
NLua:
    ILuaObject:
    Lua: # Lua运行
        Context:
        DoFile():
        DoString():
        GetFunction():
        GetTable():
        RegisterFunction():
    LuaContext: # lua 运行上下文
    LuaException:
    LuaFunction: # lua 函数
        Call():
        IsValid():
    LuaResult: # lua 执行结果
    LuaTable: # lua 表
        Get():
        Remove():
        Set():
    LuaTableProxy:
    LuaThread:
```