当请求的响应类型是“code”或“token”时，或者当重定向请求将导致在开放网络上传输敏感凭证时，重定向端点应该要求使用如第1.6节所述[Section 1.6](https://tools.ietf.org/html/rfc6749#section-1.6)的TLS。此规范并未强制要求使用TLS，因为在撰写本文时，要求客户端部署TLS对许多客户端开发人员来说是一个重大障碍。如果TLS不可用，授权服务器应该在重定向之前警告资源所有者关于不安全端点（例如，在授权请求期间显示消息）。

缺乏传输层安全性会严重影响客户端及其授权访问的受保护资源的安全性。当授权过程被客户端\(如第三方登录服务\)用作委托终端用户身份验证的一种形式时，传输层安全性的使用尤其关键。
