<h3>express使用说明</h3>
1.全局安装express-generator
```
$ npm install express-generator -g
```
2.进入项目目录
```
cd /c/demo/demo
```
3.本地安装express(默认为jade模板加了 -e后缀则安装ejs模板引擎)
```
$ express -e
```
4.安装依赖
```
$ npm install
```
5.然后你就能正常使用啦

6.安装supervisor

每次代码改动都需要重启 node！不过安装 npm install supervisor 后可以偷懒；它会在你每次修改完代码后自动重启。 神器哦！

```
npm install supervisor -g
```
安装之后进入启动文件目录(bin)，执行
```
supervisor -www
```
就可以实时监听了

