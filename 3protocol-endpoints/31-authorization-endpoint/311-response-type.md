授权端点由授权代码授权类型和隐式授权类型使用。客户端使用以下参数通知授权服务器所需的授权类型：

response\_type

REQUIRED。值必须是请求授权代码的“code”之一，如第4.1.1节所述[Section 4.1.1](https://tools.ietf.org/html/rfc6749#section-4.1.1)，“token”，用于请求第4.2.1节[Section 4.2.1](https://tools.ietf.org/html/rfc6749#section-4.2.1)所述的访问令牌\(隐式授予\)或第8.4节[Section 8.4](https://tools.ietf.org/html/rfc6749#section-8.4)所述的注册扩展值。

扩展响应类型可能包含一个以空格分隔\(%x20\)的值列表，其中值的顺序无关紧要\(例如，响应类型“a b”与“b a”相同\)。这些组合响应类型的含义由它们各自的规范定义。

如果授权请求缺少“response\_type”参数，或者响应类型不被理解，授权服务器必须返回一个错误响应，如4.1.2.1节所述[Section 4.1.2.1](https://tools.ietf.org/html/rfc6749#section-4.1.2.1)。

