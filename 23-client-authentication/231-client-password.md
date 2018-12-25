拥有客户端密码的客户端可以使用\[[RFC2617](https://tools.ietf.org/html/rfc2617)\]中定义的HTTP基本身份验证方案对授权服务器进行身份验证。使用附录B中的“application / x-www-form-urlencoded”编码算法对客户端标识符进行编码，并将编码值用作用户名; 客户端密码使用相同的算法进行编码并用作密码。授权服务器必须支持HTTP基本身份验证方案，以便对发出客户端密码的客户端进行身份验证。

例如：

Authorization: Basic czZCaGRSa3F0Mzo3RmpmcDBaQnIxS3REUmJuZlZkbUl3

或者，授权服务器可以使用以下内容支持在请求主体中包括客户端凭证

参数：

client\_id

REQUIRED。在2.2节[Section 2.2](https://tools.ietf.org/html/rfc6749#section-2.2)描述的注册过程中发给客户端的客户端标识符。

client\_secret

REQUIRED。客户的密码。 如果客户端密码是空字符串，则客户端可以省略该参数。

不建议使用这两个参数在请求体中包含客户端凭据，并且应该仅限于不能直接使用HTTP基本身份验证方案\(或其他基于密码的HTTP身份验证方案\)的客户端。参数只能在请求体中传输，不能包含在请求URI中。

例如，使用body参数刷新访问令牌（第6节）的请求：

```
POST /token HTTP/1.1
     Host: server.example.com
     Content-Type: application/x-www-form-urlencoded

     grant_type=refresh_token&refresh_token=tGzv3JOkF0XG5Qx2TlKWIA
     &client_id=s6BhdRkqt3&client_secret=7Fjfp0ZBr1KtDRbnfVdmIw
```

当使用密码认证发送请求时，授权服务器必须使用第1.6节中描述的TLS。

由于此客户端身份验证方法涉及密码，因此授权服务器必须保护使用它的任何端点免受暴力攻击。



