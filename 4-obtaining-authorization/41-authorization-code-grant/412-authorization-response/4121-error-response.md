如果请求因缺少，无效或不匹配的重定向URI而失败，或者客户端标识丢失或无效，授权服务器应该通知资源所有者错误，并且不得自动将用户代理重定向到无效重定向URI。

如果资源所有者拒绝访问请求或者请求因缺失或无效重定向URI以外的原因而失败，则授权服务器通过使用“application / x-”将以下参数添加到重定向URI的查询组件来通知客户端。 www-form-urlencoded“格式，根据附录B：

error

REQUIRED。来自单个ASCII \[USASCII\]错误代码

如下：

invalid\_request

请求缺少必需参数，包括无效参数值，多次包含参数，或者其他方式格式错误。

unauthorized\_client

客户端无权使用此方法请求授权代码。

access\_denied

资源所有者或授权服务器拒绝了该请求。

unsupported\_response\_type

授权服务器不支持使用此方法获取授权代码。

invalid\_scope

请求的范围无效，未知或格式错误。

server\_error

授权服务器遇到意外情况，导致无法完成请求。（需要此错误代码，因为无法通过HTTP重定向将500内部服务器错误HTTP状态代码返回给客户端。）

temporarily\_unavailable

由于服务器的临时过载或维护，授权服务器当前无法处理请求。（需要此错误代码，因为无法通过HTTP重定向将503 Service Unavailable HTTP状态代码返回给客户端。）

“error”参数的值不得包含设置％x20-21 /％x23-5B /％x5D-7E之外的字符。

error\_description

OPTIONAL。人类可读的ASCII \[USASCII\]文本，提供附加信息，用于帮助客户端开发人员理解发生的错误。

“error\_description”参数的值不得包含设置％x20-21 /％x23-5B /％x5D-7E之外的字符。

error\_uri

OPTIONAL。一个URI，用于标识包含错误信息的人类可读网页，用于向客户端开发人员提供有关错误的其他信息。

“error\_uri”参数的值必须符合URI引用语法，因此不得包含集合％x21 /％x23-5B /％x5D-7E之外的字符。

state

REQUIRED 。如果客户端授权请求中存在“state”参数。 从客户端收到的确切值。



例如，授权服务器通过发送以下HTTP响应来重定向用户代理：

```
 HTTP/1.1 302 Found
   Location: https://client.example.com/cb?error=access_denied&state=xyz
```





