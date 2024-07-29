# 请解释xss和csrf分别是什么？两者有什么联系？如何防御？
xss：跨域脚本攻击，csrf：跨站请求伪造

区别1：xss不需要登录，csfr需要用户先登录，然后获取网站的cookie
区别2: xss是向网站A注入恶意js代码，然后在网站A中执行js代码，而csrf是利用网站A的漏洞，去请求网站A的api

xss和csrf如何防御？
xss：
1. 建立可信任字符和html白名单，对于不在白名单之列的字符或者标签进行过滤或编码。

包括：
a. 输入检查，对于< >等特殊字符进行编码处理。
b. 给cookie设置HttpOnly属性，不让js读取cookie信息。

2. 可以通过csp（浏览器内容安全策略）来防御xss，即浏览器自动禁止外部注入恶意脚本。
两种方法可以启用csp：
a. 设置 HTTP 的 Content-Security-Policy 头部字段
b. 设置meta标签的http-equiv和content属性，http-equiv设置成Content-Security-Policy

csrf：
1. 通过判断origin和referer字段是不是来自同一个网站来判断请求是不是伪造的
2. 通过验证token来验证请求是不是伪造的。