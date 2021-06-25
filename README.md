# Recessive-url-Forward

## 项目介绍

- 由于常见的 80 443 8080等端口被国内运营商屏蔽，在自己小服务器上建站就不可避免的要使用 domain:port 的形式。 加端口的url看着不优雅，访问网站也只能使用完整的url链接。
- 解决办法有两个：花钱买专线，很明显，我没钱。。 隐性url转发实现隐藏端口。域名提供商提供这个服务，不过需要备案。。 查了Google，其实隐性url转发原理很简单。只是前提条件 公网ip服务器 一直无法解决；
- 最近翻github的时候想起来，可以利用github page之类的托管服务实现效果。

## 具体使用

GitHub pages方式使用（其实就是启用github pages...）

1. 点击右上角 Fork；
2. 点击 index.html；src="https://example.com/" 修改为自己的 url 。
3. 找到 Setting  > Pages  >  Source; 将选项None切换为其它分支；然后 Save就ok了。
4. dns没有配置好的接下来按提示改；

vercel.com （对国内优化更友好，不容器被屏蔽；）

1. 右上角 fork；
2. 进入  https://vercel.com/ 网站中 使用GitHub登录；
3. 点击 new project；选择名字为 Recessive-url-Forward 的项目 import；点击 Continue Deploy 完成后点击 visit就能看到你的网站了。
4. 自定义vercel 为你自己的域名；点击此项目的 Settings Damains 输入你自己的域名；

```html
<html>
<head>
<meta http-equiv="Content-Language" content="zh-CN">
<meta HTTP-EQUIV="Content-Type" CONTENT="text/html; charset=gb2312">
<meta name="viewport" content="initial-scale=1.0, user-scalable=no">
<title>title</title>
  <style type="text/css">
      /* 将根元素占满浏览器 */
      html, body {
          margin: 0;
          padding: 0;
          width: 100%;
          height: 100%;
      }

      iframe {
          margin: 0 auto;
          display: block;
          width: 100vw;
          height: 100vh;
          border: 0;
      }
  </style>
</head>
<body>
  <iframe id="iframe" name="iframe" frameborder="0" scrolling="auto" src="https://example.com/">
	</iframe>
</body>
</html>
```

