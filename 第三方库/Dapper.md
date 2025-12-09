# Dapper


## 基础介绍


轻量级 ORM
Micro ORM，核心是通过扩展方法将 SQL 查询结果映射到对象
`dotnet add package Dapper`


## 核心内容
```yaml
Dapper:
    DynamicParameters:
        Add():
    IDbConnection:
    SqlConnection: # 数据库连接
        BeginTransaction(): # 事务
            Commit():
            Rollback():
        Execute():
        Query():
        QueryFirstOrDefault():
        QueryFirstOrDefaultAsync():
```