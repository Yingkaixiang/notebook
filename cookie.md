## samesite

https://github.com/mqyqingfeng/Blog/issues/157

> 首先要理解的一点就是跨站和跨域是不同的。同站(same-site)/跨站(cross-site)」和第一方(first-party)/第三方(third-party)是等价的。但是与浏览器同源策略（SOP）中的「同源(same-origin)/跨域(cross-origin)」是完全不同的概念。

> 同源策略的同源是指两个 URL 的协议/主机名/端口一致。例如，https://www.taobao.com/pages/...，它的协议是 https，主机名是 www.taobao.com，端口是 443。

> 同源策略作为浏览器的安全基石，其「同源」判断是比较严格的，相对而言，Cookie中的「同站」判断就比较宽松：只要两个 URL 的 eTLD+1 相同即可，不需要考虑协议和端口。其中，eTLD 表示有效顶级域名，注册于 Mozilla 维护的公共后缀列表（Public Suffix List）中，例如，.com、.co.uk、.github.io 等。eTLD+1 则表示，有效顶级域名+二级域名，例如 taobao.com 等。

> 举几个例子，www.taobao.com 和 www.baidu.com 是跨站，www.a.taobao.com 和 www.b.taobao.com 是同站，a.github.io 和 b.github.io 是跨站(注意是跨站)。

## document.cookie

将 cookie 设置为 samesite=none 必须保证 secure 为 true，所以当前前端使用 js 也就是 document.cookie 写入 samesite=none 的 cookie 时得保证当前 url 的协议为 https，否则将无法写入

## secure

cookie 的 secure 为true时 发起的请求为 https 才会携带 cookie

## 浏览器展示 cookie

当我们打开一个网站时我们会发现非当前打开网站的域名cookie也能查看到，这是浏览器的默认机制，只能看不能操作，同时按照 cookie 设置的属性不同也会影响它的展示逻辑，如果再 a.com 下写了一个 secure=true 的 cookie，在 b.a.com 下打开可能看不见，原因是取决于你的  b.a.com 是 http 还是 https
