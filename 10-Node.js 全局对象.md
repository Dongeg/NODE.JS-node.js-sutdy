<h3>Node.js 全局对象</h3>
JavaScript 中有一个特殊的对象，称为全局对象（Global Object），它及其所有属性都可以在程序的任何地方访问，即全局变量。

在浏览器 JavaScript 中，通常 window 是全局对象， 而 Node.js 中的全局对象是 global，所有全局变量（除了 global 本身以外）都是 global 对象的属性。

在 Node.js 我们可以直接访问到 global 的属性，而不需要在应用中包含它

<h3>__fliename</h3>

__filename 表示当前正在执行的脚本的文件名。它将输出文件所在位置的绝对路径，且和命令行参数所指定的文件名不一定相同。 如果在模块中，返回的值是模块文件的路径

```javascript
// 输出全局变量 __filename 的值
console.log( __filename );
```
执行返回绝对路径

<h3>__dirname</h3>
__dirname 表示当前执行脚本所在的目录。

```javascript
// 输出全局变量 __dirname 的值
console.log( __dirname );
```
返回当前脚本所在目录

<h3>全局函数？</h3>
setTimeout()

clearTimeout()

setInterval()

console
