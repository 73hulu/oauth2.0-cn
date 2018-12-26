如果访问令牌请求有效且已获得授权，则授权服务器会发出访问令牌和可选的刷新令牌，如第5.1节所述[Section 5.1](https://tools.ietf.org/html/rfc6749#section-5.1)。 如果请求客户端身份验证失败或无效，授权服务器将返回错误响应，如第5.2节中所述[Section 5.2](https://tools.ietf.org/html/rfc6749#section-5.2)。

一个成功的响应示例：

```
HTTP/1.1 200 OK
     Content-Type: application/json;charset=UTF-8
     Cache-Control: no-store
     Pragma: no-cache

     {
       "access_token":"2YotnFZFEjr1zCsicMWpAA",
       "token_type":"example",
       "expires_in":3600,
       "refresh_token":"tGzv3JOkF0XG5Qx2TlKWIA",
       "example_parameter":"example_value"
     }
```



