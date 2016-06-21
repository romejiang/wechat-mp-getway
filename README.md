# 微信公众平台授权回调页面转发工具

解决微信公众平台网页授权回调域名只能设置一个的问题

## 使用方法

1. 将 wechat-getway.html 文件中的 redirect_url 改成你真实的项目地址。比如：http://localhost:3000

2. 将 wechat-getway.html 改名并上传到你的微信授权回调域名的目录下，例如 http://meteorup.cn/local.html

3. 在你的项目中将微信授权接口的回调地址改为  http://meteorup.cn/local.html 。
例如这样：
https://open.weixin.qq.com/connect/oauth2/authorize?appid=APPID&redirect_uri=http%3A%2F%2Fmeteorup.cn%2Flocal.html&response_type=code&scope=SCOPE&state=STATE#wechat_redirect

4. local.html 页面从微信那里拿到 code 之后会跳转到 redirect_url 指向的页面，并且在url后面带上code 和 state

## 使用建议

0. wechat-getway.html 支持传入 debug 参数，debug 时将不再跳转，而是打印出目标 url
1. 有了这个工具，你的微信公众平台授权项目将不再局限于一个域名。
2. 同时也可以对本地项目调试微信用户授权功能。
3. 所以在你的授权域名下可以有多个 wechat-getway.html 文件的副本，只是不同的名字，或者放在不同的目录。记住：每个文件的 redirect_url 地址需要改成你项目的真实回调地址。

