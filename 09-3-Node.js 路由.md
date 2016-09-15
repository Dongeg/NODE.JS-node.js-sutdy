<h3>Node.js 路由</h3>
我们要为路由提供请求的URL和其他需要的GET及POST参数，随后路由需要根据这些数据来执行相应的代码。
因此，我们需要查看HTTP请求，从中提取出请求的URL以及GET/POST参数。

我们需要的所有数据都会包含在request对象中，该对象作为onRequest()回调函数的第一个参数传递。但是为了解析这些数据，我们需要额外的Node.JS模块，它们分别是url和querystring模块。

```javascript
                   url.parse(string).query
                                           |
           url.parse(string).pathname      |
                       |                   |
                       |                   |
                     ------ -------------------
http://localhost:8888/start?foo=bar&hello=world
                                ---       -----
                                 |          |
                                 |          |
              querystring(string)["foo"]    |
                                            |
                         querystring(string)["hello"]
```

server.js
```javascript
var http = require("http");
var url = require("url");

function start(route) {
  function onRequest(request, response) {
    var pathname = url.parse(request.url).pathname;
    console.log("Request for " + pathname + " received.");

    route(pathname);

    response.writeHead(200, {"Content-Type": "text/plain"});
    response.write("Hello World");
    response.end();
  }

  http.createServer(onRequest).listen(8888);
  console.log("Server has started.");
}

exports.start = start;
```
编写路由（虽然里面啥都没做）

router.js
```javascript
function route(pathname) {
  console.log("About to route a request for " + pathname);
}

exports.route = route;

```
编写入口函数

index.js

```javascript
var server = require("./server");
var router = require("./router");

server.start(router.route);
```
运行


```
$ node index.js
Server has started.
```










