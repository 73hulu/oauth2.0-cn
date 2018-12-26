客户端通过使用附录B中的“application / x-www-form-urlencoded”格式发送以下参数，并在HTTP请求实体主体中使用UTF-8的字符编码来向令牌端点发出请求：

grant\_type

REQUIRED。值必须设置为“authorization\_code”。

code

REQUIRED。从授权服务器接收的授权代码。

redirect\_uri

REQUIRED。如果“redirect\_uri”参数包含在第4.1.1节[Section 4.1.1](https://tools.ietf.org/html/rfc6749#section-4.1.1)中描述的授权请求中，并且它们的值必须相同。

client\_id

REQUIRED。如果客户端未使用授权服务器进行身份验证，如第3.2.1节中所述[Section 3.2.1](https://tools.ietf.org/html/rfc6749#section-3.2.1)。

如果客户端类型是机密的或客户端已获得客户端凭证（或分配了其他身份验证要求），则客户端必须使用授权服务器进行身份验证，如第3.2.1节中所述[Section 3.2.1](https://tools.ietf.org/html/rfc6749#section-3.2.1)。

例如，客户端使用TLS发出以下HTTP请求：

```
POST /token HTTP/1.1
     Host: server.example.com
     Authorization: Basic czZCaGRSa3F0MzpnWDFmQmF0M2JW
     Content-Type: application/x-www-form-urlencoded

     grant_type=authorization_code&code=SplxlOBeZQQYbYS6WxSbIA
     &redirect_uri=https%3A%2F%2Fclient%2Eexample%2Ecom%2Fcb
```

授权服务器必须：

* 要求对机密客户端或任何已发布客户端凭据（或其他身份验证要求）的客户端进行客户端身份验证，
* 如果包含客户端身份验证，则验证客户端，
* 确保授权代码是发给经过身份验证的机密客户端，或者如果客户端是公共的，请确保代码已发送到请求中的“client\_id”，
* 验证授权代码是否有效，以及
* 如果第4.1.1节中描述的初始授权请求中包含“redirect\_uri”参数，则确保存在“redirect\_uri”参数，如果包含，则确保它们的值相同。



