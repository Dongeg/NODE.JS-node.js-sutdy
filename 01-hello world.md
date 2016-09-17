<h3>http服务器</h3>
```javascript
//server.js
var http=require('http');
http.createServer(function(request,response){
	response.writeHead(200,{'Content-Type':'text/plain'});
	response.end('hello world\n');
}).listen(8888);
console.log('Server running at http://127.0.0.1:8888/')
```
<h3>https服务器</h3>
ps:这个应该要那两个证书文件才能运行
```js
var https=require('https')

var fs=require('fs')

var options={
	key:fs.readFileSync('ssh_key.pem'), 
	cert:fs.readFileSync('ssh_cert.pem')
}
https.createServer(options,function(req,res){
	res.writeHead(200)
	res.end('hello world')
}).listen(8888);
console.log("success")
```



```bash
<!--bash-->
$ cd C:/nodejs/app

$ node server.js
```
