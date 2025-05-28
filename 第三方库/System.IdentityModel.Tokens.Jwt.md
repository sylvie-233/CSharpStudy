# System.IdentityModel.Tokens.Jwt


## 基础介绍

JWT库


JWT 一般由三个部分组成：
- Header（头部）：包含签名算法（如 HS256）和令牌类型（JWT）。
- Payload（载荷）：包含声明（Claims），如用户信息、过期时间等。
- Signature（签名）：基于头部和载荷，使用密钥进行加密签名，确保令牌不被篡改




## 核心内容
```yaml
System.IdentityModel.Tokens.Jwt:
    Claim: # JWT 中的一个声明
    JwtRegisteredClaimNames: # 标准声明名称常量
        Issuer: # iss，令牌的发行者
        Subject: # sub，令牌的主题
        Audience: # aud，令牌的受众
        ExpirationTime: # exp，令牌的过期时间
        NotBefore: # nbf，令牌生效时间
        IssuedAt: # iat，令牌的签发时间
    JwtSecurityToken: # jwt token
        claims:
        expires:
        signingCredentials:
    JwtSecurityTokenHandler: # 创建和读取 JWT 令牌
        CanReadToken():
        ReadToken():
        ValidateToken(): # token验证
        WriteToken():
    SecurityToken: # token基类
    SecurityTokenDescriptor:
    SigningCredentials: # 签名算法和签名密钥
        Algorithm:
        Key:
    TokenValidationException:
    TokenValidationParameters: # 验证 JWT 时的各种配置参数
```