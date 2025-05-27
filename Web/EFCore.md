# EntityFrameworkCore


## 基础介绍


### ef
```yaml
dotnet ef:
    database:
        update: # 更新数据库
    migrations:
        add: # 根据模型生成迁移文件
```




## 核心内容
```yaml
Microsoft.EntiryFrameworkCore:
    InMemory:
    Proxies:
    Sqlite:
    SqlServer:
    DbContext: # 连接上下文管理
        Database:
            BeginTransaction():
                Commit():
                Rollback():
        Entry(): # 获取操作实体
            State:
        SaveChanges(): # 执行数据库操作
    DbContextOptions:
        UseInMemoryDatabase():
        UseLazyLoadingProxies():
        UseSqlServer():
    DbSet: # 数据库表操作
        Add():
        AddRange():
        FindAsync():
        FirstOrDefault():
        Remove():
        ToList():
        Where():
```