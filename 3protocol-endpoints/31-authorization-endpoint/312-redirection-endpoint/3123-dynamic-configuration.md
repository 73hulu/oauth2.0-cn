如果已注册了多个重定向URI，如果只注册了部分重定向URI，或者没有注册重定向URI，则客户端必须使用“redirect\_uri”请求参数包含带有授权请求的重定向URI。

当授权请求中包含重定向URI时，如果注册了重定向URI，授权服务器必须将接收到的值与\[RFC3986\]第6节[\[RFC3986\] Section 6](https://tools.ietf.org/html/rfc3986#section-6)中定义的至少一个注册重定向URI\(或URI组件\)进行比较和匹配。如果客户端注册包含完整重定向URI，则授权服务器必须使用\[RFC3986\]第6.2.1节[\[RFC3986\] Section 6.2.1](https://tools.ietf.org/html/rfc3986#section-6.2.1)中定义的简单字符串比较来比较两个URI。

