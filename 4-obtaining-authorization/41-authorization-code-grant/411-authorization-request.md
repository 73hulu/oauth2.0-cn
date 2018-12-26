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

