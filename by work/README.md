# Node.js
## express
- bodyParser 
- express中间件 处理http 的 content-type和body
- app.use(bodyParser.urlencoded({extended: - true}));
- app.use(bodyParser.json());

## cors
- 只有 Web 才有跨域 CORS，移动端 iOS 与 Android 就没有，谁让 Web 能看源代码呢，沙盒机制也不如移动端健全。HTML5 支持跨域以后，就变成了CORS技术。 这是内置于http协议本身的。所以自然用起来更流畅，更舒心。
同源策略的限制：XmlHttpRequest 只允许请求当前源（域名、协议、端口）的资源，所以AJAX是不允许跨域的。
相反就是跨域：如果想让XmlHttpRequest 按照自己意愿（域名、协议、端口）请求数据，那就需要跨域

- 那为什么有同源策略限制？

- 没有同源策略的话，资源（如HTTP头、Cookie、DOM、localStorage等）就能相互随意访问，那就没有安全了。同源策略就是把每个网站都关在一个笼子里，每个网站互相访问不到数据，只有用户和网站开发者可以访问数据，这样就安全了。

## ejs
- html模板引擎

- querystring 查询字符串

## redis
- [list做大数据分页](https://www.cnblogs.com/rjzheng/p/9096228.html)

## async/await 写法