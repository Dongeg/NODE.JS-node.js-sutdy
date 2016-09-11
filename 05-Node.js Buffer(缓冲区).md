<h3>Node.js Buffer(缓冲区)</h3>

JavaScript 语言自身只有字符串数据类型，没有二进制数据类型。

但在处理像TCP流或文件流时，必须使用到二进制数据。

因此在 Node.js中，定义了一个 Buffer 类，该类用来创建一个专门存放二进制数据的缓存区。在 Node.js 中，Buffer 类是随 Node 内核一起发布的核心库。

Buffer 库为 Node.js 带来了一种存储原始数据的方法，可以让 Node.js 处理二进制数据，每当需要在 Node.js 中处理I/O操作中移动的数据时，就有可能使用 Buffer 库。

原始数据存储在 Buffer 类的实例中。一个 Buffer 类似于一个整数数组，但它对应于 V8 堆内存之外的一块原始内存。

<h3>创建 Buffer 类</h3>
```javascript
//创建长度为 10 字节的 Buffer 实例：
var buf=new Buffer(10)

//通过给定的数组创建 Buffer 实例：
var buf = new Buffer([10, 20, 30, 40, 50]);

通过一个字符串来创建 Buffer 实例：
var buf=new Buffer("abcdefghijklmn","utf-8");
```
<h3>写入缓冲区</h3>
```javascript
//[]内是可选参数
buf.write(string[, offset[, length]][, encoding])
```
string - 写入缓冲区的字符串。

offset - 缓冲区开始写入的索引值，默认为 0 。

length - 写入的字节数，默认为 buffer.length

encoding - 使用的编码。默认为 'utf8' 。
```javascript
buf=new Buffer(256);
len=buf.write("asddd")

```
返回值为写入的字节数
<h3>从缓冲区读取数据</h3>

```javascript
buf.toString([encoding[, start[, end]]])
```

<h3>将 Buffer 转换为 JSON 对象</h3>
```javascript
buf.toJOSN()
```
栗子
```javascript
var buf = new Buffer('www.runoob.com');
var json = buf.toJSON(buf);

console.log(json);

```
<h3>缓冲区合并</h3>
```javascript
Buffer.concat(list[, totalLength])
```
栗子
```javascript
var buf1=new Buffer('bac');
var buf2=new Buffer('def');
var buf3=Buffer.concat([buf1,buf2]);
console.log(buf3.toString());//abcdef
```
<h3>缓冲区比较</h3>
```javascript
buf.compare(otherBuffer);
```
```javascript
var buffer1 = new Buffer('ABC');
var buffer2 = new Buffer('ABC');
var result = buffer1.compare(buffer2);
console.log(result);//返回-1 0 1 表示比较结果
```
<h3>拷贝缓冲区</h3>
```javascript
buf.copy(targetBuffer[, targetStart[, sourceStart[, sourceEnd]]])
```
targetBuffer - 要拷贝的 Buffer 对象。

targetStart - 数字, 可选, 默认: 0

sourceStart - 数字, 可选, 默认: 0

sourceEnd - 数字, 可选, 默认: buffer.length
栗子
```javascript
var buffer1 = new Buffer('ABC');
// 拷贝一个缓冲区
var buffer2 = new Buffer(3);
buffer1.copy(buffer2);
console.log("buffer2 content: " + buffer2.toString());//buffer2 content: ABC
```
<h3>缓冲区裁剪</h3>
```javascript
buf.slice([start[, end]])
```
```javascropt
var buffer1=new Buffer('0123456879');
var buffer2=buffer1.slice(0,3);
console.log("buffer2 content: " + buffer2.toString());//012
```
<h3>缓冲区长度</h3>
```javascript
buf.length;
```
