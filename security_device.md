# Security Device {#security-device}

### WAF {#waf}

Web Application Firewall(WAF) 入门

Web Application Firewall又名WEB应用安全防火墙，简称WAF，07年底08年开始Web应用防火墙日趋流行，过去这些工具被很少数的大型项目垄断，但是，随着大量的低成本产品的面市以及可供选择的开源试用产品的出现，它们最终能被大多数人所使用。在这篇文章中，先向大家介绍Web应用防火墙能干什么，然后快速的概览一下Web应用防火墙最有用的一些特征。通过这篇文章的阅读，大家能清楚地了解web应用防火墙这个主题，掌握相关知识。

什么是web应用防火墙？

有趣的是，还没有人能真正知道web应用防火墙究竟是什么，或者确切的说，还没有一个大家认可的精确定义。从广义上来说，Web应用防火墙就是一些增强 Web应用安全性的工具。然而，如果我们要深究它精确的定义，就可能会得到更多的疑问。因为一些Web应用防火墙是硬件设备，一些则是应用软件；一些是基于网络的，另一些则是嵌入WEB服务器的。

国外市场上具有WEB应用防火墙功能的产品名称就有不同的几十种，更不用说是产品的形式和描述了。它难以界定的原因是这个名称包含的东西太多了。较低的网络层（Web应用防火墙被安置在第七层）被许多设备所覆盖，每一种设备都有它们独特的功能，比如路由器，交换机，防火墙，入侵检测系统，入侵防御系统等等。然而，在HTTP的世界里，所有这些功能都被融入在一个设备里：Web应用防火墙。

总体来说，Web应用防火墙的具有以下四个方面的功能：

1\. 审计设备：用来截获所有HTTP数据或者仅仅满足某些规则的会话

2\. 访问控制设备：用来控制对Web应用的访问，既包括主动安全模式也包括被动安全模式

3\. 架构/网络设计工具：当运行在反向代理模式，他们被用来分配职能，集中控制，虚拟基础结构等。

4\. WEB应用加固工具：这些功能增强被保护Web应用的安全性，它不仅能够屏蔽WEB应用固有弱点，而且能够保护WEB应用编程错误导致的安全隐患。

但是，需要指出的是，并非每种被称为Web应用防火墙的设备都同时具有以上四种功能。

由于WEB应用防火墙的多面性，拥有不同知识背景的人往往会关注它不同方面的特点。比如具有网络入侵检测背景的人更倾向于把它看作是运行在HTTP层上的 IDS设备；具有防火墙自身背景的人更趋向与把它看作一种防火墙的功能模块。还有一种理解来自于&quot;深度检测防火墙&quot;这个术语。他们认为深度检测防火墙是一种和Web应用防火墙功能相当的设备。然而，尽管两种设备有些相似之处，但是差异还是很大的。深度检测防火墙通常工作在的网络的第三层以及更高的层次，而 Web应用防火墙则在第七层处理HTTP服务并且很好地支持它。

直接更改WEB代码解决安全问题是否更好？这是毋庸置疑的，但也没那么容易（实现）。

因为，通过更改WEB应用代码是否一定就能增强系统安全性能，这本身就存在争论。而且现实也更加复杂：

◆ 不可能确保100%的安全。人的能力有限，会不可避免地犯错误。

◆ 绝大多数情况下，很少有人力求100%的安全。如今的现实生活中那些引领应用发展的人更多注重功能而不是安全。这种观念正在改变，只是有点缓慢。

◆ 一个复杂的系统通常包含第三方产品（组件，函数库），它们的安全性能是不为人知的。如果这个产品的源代码是保密的，那么你必须依赖商品的厂商提供补丁。即使有些情况下源代码是公开的，你也不可能有精力去修正它们。

◆ 我们不得不使用存在安全隐患的业务系统，尽管这些旧系统根本无法改进。

因此，为了获得最好的效果，我们需要双管齐下：一方面，必须提高管理者和开发者的安全意识；另一方面，尽可能提高应用系统的安全性。

Web应用防火墙的特点

Web应用防火墙的一些常见特点如下:

异常检测协议

如果阅读过各种RFC，就会发现一个被反复强调的主题。大多数RFC建议应用自己使用协议时要保守，而对于接受其他发送者的协议时可以自由些。Web服务器就是这样做的，但这样的行为也给所有的攻击者打开了大门。几乎所有的WAF对HTTP的请求执行某种异常检测，拒绝不符合Http标准的请求。并且，它也可以只允许HTTP协议的部分选项通过，从而减少攻击的影响范围。甚至，一些WAF还可以严格限定HTTP协议中那些过于松散或未被完全制定的选项。

增强的输入验证

就频繁发生的Web安全问题而言，有些是源于对Web设计模型的误解，有些则来自于程序师认为浏览器是可信的。很多WEB程序员用 JavaScript在浏览器上实现输入验证。而浏览器只是一个用户控制的简单工具，因此攻击者可以非常容易地绕过输入验证，直接将恶意代码输入到WEB 应用服务器。

有一个解决上述问题的正确方法，就是在服务端进行输入验证。如果这个方法不能实现，还可以通过在客户和应用服务器之间增加代理，让代理去执行Web页面上嵌入的JavaScript，实现输入验证。

消极的安全模型VS积极的安全模型

曾经设置过防火墙规则的人，可能会碰到这样的建议：允许已知安全的流量，拒绝其他一切访问。这就是一种很好的积极安全模型。恰恰相反，消极安全模型则是默认允许一切访问，只拒绝一些已知危险的流量模式。

每种安全模型方式都存在各自的问题：

消极安全模型：什么是危险的？

积极安全模型：什么是安全的？

消极安全模式通常使用的更多。识别出一种危险的模式并且配置自己的系统禁止它。这个操作简单而有趣，却不十分安全。它依赖于人们对于危险的认识，如果问题存在，却没有被意识到（这种情况很常见），就会为攻击者留下可趁之机。

积极安全模式（又称为白名单模式）看上去是一种制定策略的更好方式,非常适于配置防火墙策略。在Web应用安全领域中，积极安全模式通常被概括成对应用中的每一个脚本的枚举。对枚举的每一个脚本，需要建立一个相应列表，表中内容如下所示：

◆ 允许的请求方式（比如，GET/POST或者只POST）

◆ 允许的Content-Type

◆ 允许的Content-Length

◆ 允许的参数

◆ 指定参数和可选参数

◆ 参数类型（比如，文本或整数）

◆ 附加参数限制

上述列表仅仅是个例子，实际的积极安全模式通常包括更多的要素。它试图从外部完成程序员本应从内部完成的工作：为提交到Web应用的信息验证每一个比特。如果肯花时间的话，使用积极安全模式就是一个比较好的选择。这个模式的难点之一，在于应用模式会随着应用的发展而改变。每当应用中添加新脚本或更改旧脚本，就需要更新模式。但是，它适用于保护那些稳定的、无人维护的旧应用。

自动开发策略可以解决以上问题：

◆ 一些WAF能够监视流量，并根据这些流量数据自动配置策略，有些产品可以实时进行这样的工作。

◆ 通过白名单，可以标识特定的IP地址是可信的，然后，依据观察的流量，配置WAF，更新安全策略。

◆ 如果通过一个全面的衰减测试，（仿真正确的行为，）来创建一个应用，并且在WAF处于监控状态时执行测试，那么WAF可以自动生成策略。

可见，没有哪个模式是完全令人满意的。消极安全模式适用于处理已知问题，而积极安全模式则适用于稳定的Web应用。理想的做法是，在现实生活中，将二者结合使用，取长补短。

及时补丁

积极安全模式理论上更好一些因为浏览器和WEB应用程序之间的通信协议通过HTML规范进行了很好的定义。现在的Web开发语言都可以处理带有多个参数的 HTTP请求。因为这些参数在Web应用防火墙中都是可见的，因此WEB应用防火墙可以分析这些参数判断是否存在允许该请求。，

当一个应用中的漏洞被发现时大多数情况下我们会尽可能在代码中修补它。受诸多因素的影响（如应用的规模，是否有开发人员，法律问题等等 ），开发补丁的过程可能需要几分钟，或者一直到无限长的是时间。这些时间正是攻击者发起攻击的好机会。

如果开发人员能够在非常短的时间内在代码中修补好漏洞，那你就不用担心了。但如果修补这个漏洞需要花费几天，甚至几周来修复呢？Web 应用防火墙就是处理这个问题的理想工具：只要给一个安全专家不错的WAF和足够的漏洞信息，他就能在不到一个小时的时间内屏蔽掉这个漏洞。当然，这种屏蔽掉漏洞的方式不是非常完美的，并且没有安装对应的补丁就是一种安全威胁，但我们在没有选择的情况下，任何保护措施都比没有保护措施更好。

及时补丁的原理可以更好的适用于基于XML的应用中，因为这些应用的通信协议都具规范性。

基于规则的保护和基于异常的保护

现在市场上大多数的产品是基于规则的WAF。其原理是每一个会话都要经过一系列的测试，每一项测试都由一个过多个检测规则组成，如果测试没通过，请求就会被认为非法并拒绝。

基于规则的WAFs很容易构建并且能有效的防范已知安全问题。当我们要制定自定义防御策略时使用它会更加便捷。但是因为它们必须要首先确认每一个威胁的特点，所以要由一个强大的规则数据库支持。WAF生产商维护这个数据库，并且他们要提供自动更新的工具。

这个方法不能有效保护自己开发的WEB应用或者零日漏洞（攻击者使用的没有公开的漏洞），这些威胁使用基于异常的WAF更加有效。

异常保护的基本观念是建立一个保护层，这个保护层能够根据检测合法应用数据建立统计模型，以此模型为依据判别实际通信数据是否是攻击。理论上，一但构建成功，这个基于异常的系统应该能够探测出任何的异常情况。拥有了它，我们不再需要规则数据库而且零日攻击也不再成问题了。但基于异常保护的系统很难构建，所以并不常见。因为用户不了解它的工作原理也不相信它，所以它也就不如基于规则的WAF应用广范。

状态管理

HTTP的无状态性对Web应用安全有很多负面影响。会话只能够在应用层上实现，但对许多应用来说这个附加的功能只能满足业务的需要而考虑不到安全因素了。Web应用防火墙则将重点放在会话保护上，它的特征包括：

强制登录页面。在大多数站点， 你可以从任何你所知道的URL上访问站点，这通常方便了攻击者而给防御增加了困难。WAF能够判断用户是否是第一次访问并且将请求重定向到默认登录页面并且记录事件。

分别检测每一个用户会话。如果能够区分不同的会话，这就带来了无限的可能。比如，我们能够监视登陆请求的发送频率和用户的页面跳转。通过检测用户的整个操作行为我们可以更容易识别攻击。

对暴力攻击的识别和响应。通常的Web应用网络是没有检测暴力攻击的。有了状态管理模式，WAF能检测出异常事件（比如登陆失败），并且在达到极限值时进行处理。此时它可以增加更多的身份认证请求的时间，这个轻微的变化用户感觉不到，但对于足以对付自动攻击脚本了。如果一个认证脚本需要 50毫秒完成，那它可以发出大约每秒20次的请求。如果你增加一点延时，比如说，一秒种的延迟，那会将请求降低至每秒不足一次。与此同时，发出进一步检测的警告，这将构成一个相当好的防御。

实现会话超时。超出默认时间会话将失效，并且用户将被要求重新认证。用户在长时间没有请求时将会自动退出登录。

会话劫持的检测和防御。许多情况下，会话劫持会改变IP地址和一些请求数据（HTTP请求的报头会不同）。状态监控工具能检测出这些异常并防止非法应用的发生。在这种情况下应该终止会话，要求用户重新认证，并且记录一个警告日志信息。

只允许包含在前一请求应答中的链接。一些WAF很严格，只允许用户访问前一次请求返回页面中的链接。这看上去是一个有趣的特点但很难得到实施。一个问题在于它不允许用户使用多个浏览器窗口，另一个问题是它令使用JavaScript自动建立连接的应用失效。

其他防护技术

WAF的另外一些安全增强的功能用来解决WEB程序员过分信任输入数据带来的问题。比如：

隐藏表单域保护。有时，内部应用数据通过隐藏表单变量实现，而它们并不是真的隐藏的。程序员通常用隐藏表单变量的方式来保存执行状态，给用户发送数据，以确保这些数据返回时未被修改。这是一个复杂繁琐的过程，WAF经常使用密码签名技术来处理。

Cookies保护。和隐藏表单相似的是，cookies经常用来传递用户个人的应用数据，而不一样的是，一些cookies可能含有敏感数据。WAFs 通常会将整个内容加密，或者是将整个cookies机制虚拟化。有了这种设置，终端用户只能够看到cookies令牌（如同会话令牌），从而保证 cookies在WAF中安全地存放

抗入侵规避技术。基于网络的IDS对付WEB攻击的问题就是攻击规避技术。改写HTTP输入请求数据（攻击数据）的方式太多，并且各种改写的请求能够逃避IDS探测。在这个方面如果能完全理解HTTP就是大幅度的改进。比如，WAF每次可以看到整个HTTP请求，就可以避免所有类型的 HTTP请求分片的攻击。因为很好的了解HTTP协议，因此能够将动态请求和静态请求分别对待，就不用花大量时间保护不会被攻击的静态数据。这样WAF可以有足够的计算能力对付各种攻击规避技术， 而这些功能由NIDSs完成是很耗时的。

响应监视和信息泄露保护。信息泄露防护是我们给监视HTTP输出数据的一个名称。从原理上来说它和请求监视是一样的，目的是监视可疑的输出，并防止可疑的 http输出数据到达用户。最有可能的应用模式是监视信用卡号和社会保险号。另外，这个技术的另一项应用是发现成功入侵的迹象。因为有经验攻击者总会给信息编码来防止监测，所以防止这样有决心并技术熟练的攻击者获取信息是很困难的。但是，在攻击者没有完全掌控服务器而仅仅尝试WEB应用的安全漏洞的情况下，这项技术可以起到防护效果

#### ModSecurity {#modsecurity-0}

ModSecurity原本是Apache上的一款开源WAF模块，可以有效的增强Web安全性。目前已经支持Nginx和IIS，配合Nginx的灵活和高效可以打造成生产级的WAF，是保护和审核Web安全的利器。

在这篇文章中，我们将学习配置ModSecurity与OWASP的核心规则集。

### 什么是ModSecurity {#modsecurity}

ModSecurity是一个入侵侦测与防护引擎，它主要是用于Web应用程序，所以也被称为Web应用程序防火墙(WAF)。它可以作为Web服务器的模块或是单独的应用程序来运作。ModSecurity的功能是增强Web Application 的安全性和保护Web application以避免遭受来自已知与未知的攻击。

ModSecurity计划是从2002年开始，后来由Breach Security Inc.收购，但Breach Security Inc.允诺ModSecurity仍旧为Open Source，并开放源代码给大家使用。最新版的ModSecurity开始支持核心规则集(Core Rule Set)，CRS可用于定义旨在保护Web应用免受0day及其它安全攻击的规则。

ModSecurity还包含了其他一些特性，如并行文本匹配、Geo IP解析和信用卡号检测等，同时还支持内容注入、自动化的规则更新和脚本等内容。此外，它还提供了一个面向Lua语言的新的API，为开发者提供一个脚本平台以实现用于保护Web应用的复杂逻辑。

官网：https://www.modsecurity.org/