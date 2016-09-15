<h3>url模块</h3>
url中有如下几个方法可以调用
```bash
$ node
> url
{ parse: [Function: urlParse],
  resolve: [Function: urlResolve],
  resolveObject: [Function: urlResolveObject],
  format: [Function: urlFormat],
  Url: [Function: Url] }

```
url.parse()用于地址解析

```
$ node
> url.parse('https://github.com/Dongeg/node.js/tree/master')
Url {
  protocol: 'https:',//使用的协议
  slashes: true,     //是否有协议的双斜线
  auth: null,        //值为null不一定是没有，有可能只是在url中没有写
  host: 'github.com',//域名
  port: null,//端口号默认80
  hostname: 'github.com',////主机名
  hash: null,//哈希值，通常对应页面上的锚节点
  search: null,//查询字符串参数
  query: null,//发送给http服务器的数据
  pathname: '/Dongeg/node.js/tree/master',//访问资源路径名
  path: '/Dongeg/node.js/tree/master',//访问资源路径
  href: 'https://github.com/Dongeg/node.js/tree/master' }//

```
example2
```
$ node

> url.parse('https://github.com:8080/Dongeg/node.js/tree/master?id
=1&name=deg#list1')
Url {
  protocol: 'https:',
  slashes: true,
  auth: null,
  host: 'github.com:8080',
  port: '8080',
  hostname: 'github.com',
  hash: '#list1',
  search: '?id=1&name=deg',
  query: 'id=1&name=deg',
  pathname: '/Dongeg/node.js/tree/master',
  path: '/Dongeg/node.js/tree/master?id=1&name=deg',
  href: 'https://github.com:8080/Dongeg/node.js/tree/master?id=1&n
ame=deg#list1' }

```





