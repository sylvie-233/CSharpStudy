# MySql.Data


## 基础介绍


`dotnet add package MySql.Data`


## 核心内容
```yaml
MySql.Data:
    MySqlClient:
        MySqlCommand: # mysql执行句柄
            Parameters:
                AddWithValue():
            ExecuteReader():
            ExecuteNonQuery():
        MySqlConnection: # mysql连接
            Open():
        MySqlDataReader: # 数据读取器
            GetInt32():
            GetString():
            Read():
```