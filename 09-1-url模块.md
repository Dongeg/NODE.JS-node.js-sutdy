<h3>url模块</h3>
url中有如下几个方法可以调用

```{r, engine='bash', count_lines}
$ node
> url
{ parse: [Function: urlParse],
  resolve: [Function: urlResolve],
  resolveObject: [Function: urlResolveObject],
  format: [Function: urlFormat],
  Url: [Function: Url] }

```
url.parse()用于地址解析

example
```{r, engine='bash', count_lines}
$ node

> url.parse('https://github.com:8080/Dongeg/node.js/tree/master?id
=1&name=deg#list1')
Url {
  protocol: 'https:',                      //使用的底层协议
  slashes: true ,                          //是否有协议的双斜线
  auth: null,                              //值为null不一定是没有，有可能只是在url中没有写
  host: 'github.com:8080',                 //主机
  port: '8080',                            //端口号
  hostname: 'github.com',                  //主机名
  hash: '#list1',                          //哈希值，通常对应页面锚节点
  search: '?id=1&name=deg',                //查询字符串参数
  query: 'id=1&name=deg',                  //发送给服务器的数据
  pathname: '/Dongeg/node.js/tree/master', //路径名
  path: '/Dongeg/node.js/tree/master?id=1&name=deg',//路径
  href: 'https://github.com:8080/Dongeg/node.js/tree/master?id=1&name=deg#list1'//完整url地址
  }

```
example2

加第二个参数，则query会被解析成对象
```
> url.parse('https://github.com:8080/Dongeg/node.js/tree/master?id
=1&name=deg#list1',true)
Url {
  protocol: 'https:',
  slashes: true,
  auth: null,
  host: 'github.com:8080',
  port: '8080',
  hostname: 'github.com',
  hash: '#list1',
  search: '?id=1&name=deg',
  query: { id: '1', name: 'deg' },
  pathname: '/Dongeg/node.js/tree/master',
  path: '/Dongeg/node.js/tree/master?id=1&name=deg',
  href: 'https://github.com:8080/Dongeg/node.js/tree/master?id=1&n
ame=deg#list1' }

```
加第三个参数 ，可以解析无协议的地址

```
> url.parse('github.com:8080/Dongeg/node.js/tree/master?id=1&name=
deg#list1',true,true)
Url {
  protocol: 'github.com:',
  slashes: null,
  auth: null,
  host: '8080',
  port: null,
  hostname: '8080',
  hash: '#list1',
  search: '?id=1&name=deg',
  query: { id: '1', name: 'deg' },
  pathname: '/Dongeg/node.js/tree/master',
  path: '/Dongeg/node.js/tree/master?id=1&name=deg',
  href: 'github.com:8080/Dongeg/node.js/tree/master?id=1&name=deg#
list1' }

```






format()把解析后的对象生成url地址

```{r, engine='bash', count_lines}
format({
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
ame=deg#list1' })

'https://github.com:8080/Dongeg/node.js/tree/master?id=1&name=deg#list1'

```
url.resolve()
```
>url.resolve('https://github.com','Dongeg/node')

'https://github.com/Dongeg/node'
```


