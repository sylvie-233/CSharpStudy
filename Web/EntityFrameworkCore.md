# EntityFrameworkCore


## 基础介绍

C#主流ORM框架

DbContext(数据库上下文) -> DbSet() -> Entity(实体模型)


- 支持Linq sql查询


### dotnet ef
```yaml
dotnet ef:
    database: # 数据库
        update: # 根据迁移文件、更新数据库
    migrations: # 数据库迁移
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
        Dispose(): # 关闭连接
        Entry(): # 获取操作实体
            State:
        SaveChanges(): # 执行数据库操作
    DbContextOptions:
        UseInMemoryDatabase():
        UseLazyLoadingProxies():
        UseSqlServer():
    DbSet: # 数据库表操作
        Add(): # 添加数据
        AddRange():
        FindAsync():
        FirstOrDefault(): 
        Remove():
        ToList():
        Where():
```



### DbContext

数据库上下文

### DbSet


模型集合

### Model

模型


#### Table

数据库表

##### Key
主键