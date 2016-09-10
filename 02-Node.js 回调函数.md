回调函数在完成任务后就会被调用，Node 使用了大量的回调函数，Node 所有 API 都支持回调函数。

例如，我们可以一边读取文件，一边执行其他命令，在文件读取完成后，我们将文件内容作为回调函数的参数返回。这样在执行代码时就没有阻塞或等待文件 I/O 操作。这就大大提高了 Node.js 的性能，可以处理大量的并发请求



创建一个用于读取的文本文件input.txt
```
hello woeld
```

同步读取
server.js
```javascript
var fs=require("fs");
var data=fs.readFileSync('input.txt');
console.log(data.toString());
console.log("i am running");
```
结果
```bash
$ node server.js

hello world

i am running
```


异步读取
server.js
```javascript
var fs=require("fs");
fs.readFile('input.text',function(err,data){
  if(err)return console.error(err);
  console.log(data.toString());
});
```
结果
```bash
$ node server.js

i am running

hello world
```
阻塞按是按顺序执行的，而非阻塞是不需要按顺序的，所以如果需要处理回调函数的参数，我们就需要写在回调函数内







