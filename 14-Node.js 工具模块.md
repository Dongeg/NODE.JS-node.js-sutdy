<h2>Node.js 工具模块</h2>
在 Node.js 模块库中有很多好用的模块。接下来我们为大家介绍几种常用模块的使用：
<h3>OS 模块</h3>
Node.js os 模块提供了一些基本的系统操作函数。我们可以通过以下方式引入该模块：
```javascript
var os=require("os")
```
方法
```javascript
1	os.tmpdir()
返回操作系统的默认临时文件夹。
2	os.endianness()
返回 CPU 的字节序，可能的是 "BE" 或 "LE"。
3	os.hostname()
返回操作系统的主机名。
4	os.type()
返回操作系统名
5	os.platform()
返回操作系统名
6	os.arch()
返回操作系统 CPU 架构，可能的值有 "x64"、"arm" 和 "ia32"。
7	os.release()
返回操作系统的发行版本。
8	os.uptime()
返回操作系统运行的时间，以秒为单位。
9	os.loadavg()
返回一个包含 1、5、15 分钟平均负载的数组。
10	os.totalmem()
返回系统内存总量，单位为字节。
11	os.freemem()
返回操作系统空闲内存量，单位是字节。
12	os.cpus()
返回一个对象数组，包含所安装的每个 CPU/内核的信息：型号、速度（单位 MHz）、时间（一个包含 user、nice、sys、idle 和 irq 所使用 CPU/内核毫秒数的对象）。
13	os.networkInterfaces()
获得网络接口列表。
```

example

```
var os = require("os");

// CPU 的字节序
console.log('endianness : ' + os.endianness());

// 操作系统名
console.log('type : ' + os.type());

// 操作系统名
console.log('platform : ' + os.platform());

// 系统内存总量
console.log('total memory : ' + parseInt(os.totalmem()/1024/1024) + " mb.");

// 操作系统空闲内存量
console.log('free memory : ' + parseInt(os.freemem()/1024/1024) + " mb.");
```
result
```
$ node text.js
endianness : LE
type : Windows_NT
platform : win32
total memory : 6007 mb.
free memory : 2682 mb.

```
<h3>Node.js Path 模块</h3>
Node.js path 模块提供了一些用于处理文件路径的小工具，我们可以通过以下方式引入该模块：
```javascipt
var path=require("path)
```
```
1	path.normalize(p)
规范化路径，注意'..' 和 '.'。
2	path.join([path1][, path2][, ...])
用于连接路径。该方法的主要用途在于，会正确使用当前系统的路径分隔符，Unix系统是"/"，Windows系统是"\"。
3	path.resolve([from ...], to)
将 to 参数解析为绝对路径。
4	path.isAbsolute(path)
判断参数 path 是否是绝对路径。
5	path.relative(from, to)
用于将相对路径转为绝对路径。
6	path.dirname(p)
返回路径中代表文件夹的部分，同 Unix 的dirname 命令类似。
7	path.basename(p[, ext])
返回路径中的最后一部分。同 Unix 命令 bashname 类似。
8	path.extname(p)
返回路径中文件的后缀名，即路径中最后一个'.'之后的部分。如果一个路径中并不包含'.'或该路径只包含一个'.' 且这个'.'为路径的第一个字符，则此命令返回空字符串。
9	path.parse(pathString)
返回路径字符串的对象。
10	path.format(pathObject)
从对象中返回路径字符串，和 path.parse 相反。
```
example

```
var path = require("path");

// 格式化路径
console.log('normalization : ' + path.normalize('/test/test1//2slashes/1slash/tab/..'));

// 连接路径
console.log('joint path : ' + path.join('/test', 'test1', '2slashes/1slash', 'tab', '..'));

// 转换为绝对路径
console.log('resolve : ' + path.resolve('main.js'));

// 路径中文件的后缀名
console.log('ext name : ' + path.extname('main.js'));
```
```
$ node main.js 
normalization : /test/test1/2slashes/1slash
joint path : /test/test1/2slashes/1slash
resolve : /web/com/1427176256_27423/main.js
ext name : .js
```
<a href="http://www.runoob.com/nodejs/nodejs-net-module.html">	Net 模块</a>

用于底层的网络通信。提供了服务端和客户端的的操作。


<a href="http://www.runoob.com/nodejs/nodejs-dns-module.html">DNS 模块</a>

用于解析域名。


<a href="http://www.runoob.com/nodejs/nodejs-domain-module.html">	Domain 模块</a>
简化异步代码的异常处理，可以捕捉处理try catch无法捕捉的。








