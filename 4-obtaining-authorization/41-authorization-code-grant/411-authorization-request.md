客户端通过使用“application / x-www-form-urlencoded”格式将以下参数添加到授权端点URI的查询组件来构造请求URI，如附录B所示：

response\_type

REQUIRED。值必须设置为“code”。

client\_id

REQUIRED。客户端标识符，如第2.2节中所述[Section 2.2](https://tools.ietf.org/html/rfc6749#section-2.2)。

redirect\_uri

OPTIONAL。如第3.1.2节所述[Section 3.1.2](https://tools.ietf.org/html/rfc6749#section-3.1.2)。

scope

OPTIONAL。第3.3节[Section 3.3](https://tools.ietf.org/html/rfc6749#section-3.3)描述的访问请求的范围。

state

RECOMMENDED。客户端用于维护请求和回调之间状态的不透明值。授权服务器在将用户代理重定向回客户端时包含此值。该参数应该用于防止跨站点请求伪造，如第10.12节所述[Section 10.12](https://tools.ietf.org/html/rfc6749#section-10.12)。

客户端使用HTTP重定向响应，或通过用户代理提供的其他方法，将资源所有者定向到构造的URI。

例如，客户端指示用户代理使用TLS发出以下HTTP请求：

```
GET /authorize?response_type=code&client_id=s6BhdRkqt3&state=xyz
        &redirect_uri=https%3A%2F%2Fclient%2Eexample%2Ecom%2Fcb HTTP/1.1
   
Host: server.example.com
```

授权服务器验证请求以确保所有必需参数都存在且有效。如果请求有效，则授权服务器验证资源所有者并获得授权决策（通过询问资源所有者或通过其他方式建立批准）。

建立决策时，授权服务器使用HTTP重定向响应或通过用户代理可用的其他方式将用户代理指向提供的客户端重定向URI。

