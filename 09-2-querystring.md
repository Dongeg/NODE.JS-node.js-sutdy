<h3>Querystring()</h3>
```
$ node
> querystring
{ unescapeBuffer: [Function],
  unescape: [Function],
  escape: [Function],
  encode: [Function],
  stringify: [Function],
  decode: [Function],
  parse: [Function] }
```
<h4>querystring.stringify()</h4>
对象序列化
```shell
$ node
> querystring.stringify({ foo: 'bar', baz: ['qux', 'quux'], corge: '' })
'foo=bar&baz=qux&baz=quux&corge='

```
<h4>querystring.parse()</h4>
反序列化(解析)
```shell
$ node
> querystring.parse('foo=bar&baz=qux&baz=quux&corge=')
{ foo: 'bar', baz: [ 'qux', 'quux' ], corge: '' }


```
序列化和解析都可以方法中都可以添加第二和第三个参数，分别代表键值对之间使用的连接符（默认&）和键与值之间的连接符（默认=）

<h4>转译与反转译</h4>

```
$ node
> querystring.escape('我爱你')
'%E6%88%91%E7%88%B1%E4%BD%A0'
> querystring.unescape('%E6%88%91%E7%88%B1%E4%BD%A0')
'我爱你'

```










