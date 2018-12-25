完成与资源所有者的交互后，授权服务器将资源所有者的用户代理指向客户端。授权服务器在用户注册过程中或在发出授权请求时，将用户代理重定向到先前与授权服务器建立的客户端重定向端点。

重定向端点URI必须是\[RFC3986\]第4.3节定义[\[RFC3986\] Section 4.3](https://tools.ietf.org/html/rfc3986#section-4.3)的绝对URI。端点URI可以包括“application / x-www-form-urlencoded”格式化（根据附录B）查询组件（\[RFC3986\]第3.4节[\[RFC3986\] Section 3.4](https://tools.ietf.org/html/rfc3986#section-3.4)），在添加其他查询参数时必须保留该组件。端点URI不能包含片段组件。

