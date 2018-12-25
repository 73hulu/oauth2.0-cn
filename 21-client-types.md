OAuth根据其与授权服务器安全身份验证的能力（即，维护其客户端凭据机密性的能力）定义了两种客户端类型：

confidential：

客户端能够维护其凭证的机密性（例如，在对客户机凭据访问受限的安全服务器上实现的客户机），或者能够使用其他手段进行安全客户端认证。保密的客户端能够对外部保持客户端密码保密。该客户端密码是由授权服务器分配给客户端应用的。为了避免欺骗，该密码是授权服务器用来识别客户端的。

public：

客户端无法维护其凭证的机密性（例如，在资源所有者使用的设备上执行的客户端，例如安装的本机应用程序或基于Web浏览器的应用程序），并且无法通过任何其他方式进行安全的客户端身份验证。

客户端类型指定基于授权服务器对安全身份验证的定义及其可接受的客户端凭据公开级别。授权服务器不应该对客户端类型做出假设。

客户端可以被实现为分布式组件集，每个组件具有不同的客户端类型和安全性上下文（例如，具有基于机密服务器的机密组件和基于公共浏览器的组件的分布式客户端）。如果授权服务器不提供对此类客户端的支持或不提供有关其注册的指导，则客户端应该将每个组件注册为单独的客户端。

此规范是围绕以下客户端配置文件设计的：

web application：

Web应用程序是在Web服务器上运行的机密客户端。资源所有者通过在资源所有者使用的设备上的用户代理中呈现的HTML用户界面来访问客户端。客户端凭据以及发布到客户端的任何访问令牌都存储在Web服务器上，不会向资源所有者公开或访问。

![](/assets/1.png)

user-agent-based application：

基于用户代理的应用程序是公共客户端，浏览器是用户代理，其中客户端代码从web服务器下载并在资源所有者使用的设备上的用户代理（例如，web浏览器）内执行。协议数据和凭证对资源所有者来说很容易访问\(而且通常是可见的\)。由于此类应用程序驻留在用户代理中，因此在请求授权时，它们可以无缝地使用用户代理功能。

![](/assets/2.png)

native application：

本机应用程序是在资源所有者使用的设备上安装和执行的公共客户端。资源所有者可以访问协议数据和凭证。假设可以提取应用程序中包括的任何客户端认证凭证。另一方面，动态发布的凭证（例如访问令牌或刷新令牌）可以获得可接受的保护级别。至少，这些凭据受到保护，不会受到应用程序可能与之交互的恶意服务器的攻击。在某些平台上，可能会保护这些凭据免受驻留在同一设备上的其他应用程序的影响。原生应用比如桌面应用或移动手机应用。原生应用典型地被安装在用户计算机或设备\(手机，平板等\)上。因此客户端密码也被存储在用户计算机或设备上。

![](/assets/3.png)
