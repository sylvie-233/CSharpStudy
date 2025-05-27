# MongoDB.Driver



## 基础介绍

MongoDB数据库操作


## 核心内容
```yaml
MongoDB:
    Bson:
        Serialization:
            Attributes:
                [BsonElement]:
                [BsonId]:
                [BsonRepresentation]:
        BsonType:
            ObjectId:
    Driver:
        IMongoCollection: # 集合
            DeleteOneAsync():
            Find():
            FirstOrDefaultAsync():
            InsertOneAsync():
            ReplaceOneAsync():
            ToListAsync():
        IMongoDatabase:  # 数据库
            GetCollection():
        MongoClient: # 客户端
            GetDatabase():
```