# Minio


## 基础介绍

Minio 客户端SDK


## 核心内容
```yaml
Minio:
    DataModel:
        Args:
            BucketExistsArgs:
            MakeBucketArgs:
    Exceptions:
    MinioClient: # minio客户端
        BucketExistsAsync(): # 判断桶是否存在
        GetObjectAsync(): # 下载对象
        ListObjectsAsync(): # 列出对象
        MakeBucketAsync(): # 创建桶
        PresignedGetObjectAsync(): # 生成预签名 URL（外部浏览器直接访问）
        PutObjectAsync(): # 上传对象
        SetPolicyAsync(): # 设置桶策略
        WithCredentials():
        WithEndpoint():
        WithSSL():
            Build():
```