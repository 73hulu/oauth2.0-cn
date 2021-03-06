隐式授权是针对使用JavaScript等脚本语言在浏览器中实现的客户机优化的简化授权代码流。在隐式流中，不向客户机发出授权代码，而是直接向客户机发出访问令牌\(作为资源所有者授权的结果\)。授权类型是隐式的，因为没有颁发中间凭证\(例如授权代码\)\(稍后用于获取访问令牌\)。

在隐式授权流程期间发出访问令牌时，授权服务器不会对客户机进行身份验证。在某些情况下，可以通过用于将访问令牌传递到客户端的重定向URI来验证客户端身份。访问令牌可以公开给资源所有者或访问资源所有者的用户代理的其他应用程序。

隐式授权提高了某些客户端（例如作为浏览器内应用程序实现的客户端）的响应能力和效率，因为它减少了获取访问令牌所需的往返次数。但是，应该权衡使用隐式授权的安全隐患，例如第10.3节和第10.16节中描述的那些，特别是当授权代码授权类型可用时。

