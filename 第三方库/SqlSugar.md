# SqlSugar



## 基础介绍

国产 C# ORM 框架


## 核心内容
```yaml
SqlSugar:
    [SugarColumn]: # 表字段映射
    [SugarTable]: # 表映射
    ConnectionConfig: # 连接配置
        ConnectionString:
    SqlSugarClient: # 客户端
        Ado:
            BeginTran():
            CommitTran():
            RollbackTran():
        CodeFirst:
            InitTables():
        OnLogExecuting:
        Deleteable():
        ExecuteCommand():
        Insertable():
        Queryable():
            ToList():
            ToPageList():
            Where():
        Updateable():
```