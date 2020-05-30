---
layout: post
title: "Some Useful Node.js Internal Modules"
---

## OS

JavaScript in Web browser cannot get the information about Operating System (OS) but node.js can

{% highlight javascript %}

```javascript
const os = require("os");
console.log("operating system information -------------");
console.log("os.arch()", os.arch()); // x64
console.log("os.platform():", os.platform()); // win32
console.log("os.type():", os.type()); // Windows_NT
console.log("os.uptime():", os.uptime()); // 53354.5432871
console.log("os.hostname():", os.hostname()); // DESKTOP-CPLOU
console.log("os.release():", os.release()); // 10.0.15063
console.log("path -------------");
console.log("os.homedir():", os.homedir()); // C:\Users\cplou
console.log("os.tmpdir()", os.tmpdir()); // C:\Users\cplou\AppData\Local\Temp
console.log("memory information -------------");
console.log("os.freemem():", os.freemem()); // 9122930688
console.log("os.totalmem():", os.totalmem()); // 17060175872
```

{% endhighlight %}

- os.type() : Shows the Operating Systems type
- os.uptime() : Shows pc runtime after last reboot
- os.hostname() : Shows the computer name
- os.release() : Shows OS version
- os.homedir() : Shows home directory path
- os.freemem () : Shows available RAM
- os.totalmem() : Show entire memory capacity

## Path

It helps manipulating folder & file path

- Path module is very useful because every Operating system has different path delimiter
- Windows type & POSIX type
- Window type : separated by ₩ (i.e., C:₩Users₩cplou)
- POSIX type is used in Unix based Operating system such as macOS and Linux
- POSIX type : separated by (i.e., /home/cplou)

{% highlight javascript %}

```javascript

const path = require('path');
const string = **filename;
// path.sep: /
console.log('path.sep:', path.sep);
// path.delimiter: :
console.log('path.delimiter:', path.delimiter);
console.log('------');
// path.dirname(): /Users/gp/Desktop/node_module
console.log('path.dirname():', path.dirname(string));
// path.extname(): .js
console.log('path.extname():', path.extname(string));
// path.basename(): path.js
console.log('path.basename():', path.basename(string));
// path.basename(): path
console.log('path.basename():', path.basename(string, path.extname(string)));
console.log('------');
// path.parse() { root: '/',
// dir: '/Users/gp/Desktop/node_module',
// base: 'path.js',
// ext: '.js',
// name: 'path' }
console.log('path.parse()', path.parse(string));
// path.format(): C:\users\cplou/pathjs
console.log('path.format():', path.format({
dir: 'C:\\users\\cplou',
name: 'path',
ext: 'js',
}));
// path.normalize(): C:/users\\cplou\path.js
console.log('path.normalize():', path.normalize('C://users\\\\cplou\\\path.js'));
console.log('------');
// path.isAbsolute(): false
console.log('path.isAbsolute():', path.isAbsolute('C:\\'));
// path.isAbsolute(): false
console.log('path.isAbsolute():', path.isAbsolute('./home'));
console.log('------');
// path.relative(): ../C:\
console.log('path.relative():', path.relative('C:\\users\\cplou\\path.js', 'C:\\'));
// path.join(): /Users/gp/Desktop/users/cplou
console.log('path.join():', path.join(__dirname, '..', '..', '/users', '.', '/', 'cplou'));
// path.resolve(): /cplou
console.log('path.resolve():', path.resolve(__dirname, '..', 'users', '.', '/cplou'));
```

{% endhighlight %}

- \_\_filename\_\_, \_\_dirname represents current file and current folder path respectively
- path:sep : path delimiter (i.e., Windows : \ , POSIX : / )
- path.delimiter : env variable delimiter (i.e., Windows : ; , POSIX :)
- path.dirname(path) : file Path
- path.extname(path) : file extension
- path.basename(path, extension) : file name
- path.parse(path) : separate the file path into root, dir, base, ext, name
- path.format(object) : path.parse() object to file path
- path.noramlize(path) : remove duplicates / \
- path.isAbsolute(path) : return boolean tells whether the file path is absolute path or relative path
- path.join(path, …) : combine into a path
- path.resolve(path, …) : combine into a path

### difference between path.join & path.resolve

- path.resolve : absolute path
- path.join : relative path
  path.join('/a', '/b', 'c'); // /a/b/c
  path.resolve('/a', '/b', 'c'); // /b/c

## Url

It helps manipulate Internet address (url)
They are two types of url manipulation 1) WHATWG url 2) traditional node url
Some Useful Node.js Internal Modules 1

{% highlight javascript %}

```javascript
const url = require("url");
const URL = url.URL;
const myURL = new URL(
  "https://christosploutarchou.com/posts/nodejs/#authentication-vs-authorization"
);
console.log("new URL():", myURL);
// new URL(): URL {
// href:
// 'https://christosploutarchou.com/posts/nodejs/#authentication-vs-authorization',
// origin: 'https://christosploutarchou.com',
// protocol: 'https:',
// username: '',
// password: '',
// host: 'christosploutarchou.com,
// hostname: 'https://christosploutarchou.com',
// port: '',
// pathname: '/posts/nodejs/',
// search: '',
// searchParams: URLSearchParams {},
// hash: '#authentication-vs-authorization' }
console.log("url.format():", url.format(myURL));
// url.format(): https://christosploutarchou.com/posts/nodejs/#authentication-vs-authorization
console.log("--------");
const parsedUrl = url.parse(
  "https://christosploutarchou.com/posts/nodejs/#authentication-vs-authorization"
);
console.log("url.parse():", parsedUrl);
// url.parse(): Url {
// protocol: 'https:',
// slashes: true,
// auth: null,
// host: 'christosploutarchou.com',
// port: null,
// hostname: https://christosploutarchou.com',
// hash: '#authentication-vs-authorization',
// search: null,
// query: null,
// pathname: '/posts/nodejs//',
// path: '/posts/nodejs/',
// href:
// 'https://christosploutarchou.com/posts/nodejs/#authentication-vs-authorization'}
console.log("url.format():", url.format(parsedUrl));
// url.format():https://christosploutarchou.com/posts/nodejs/#authentication-vs-authorization
```

{% endhighlight %}

- url.parse(address) : separate url
- url.format(object) : reassemble url

## querystring

Convert searchParams of url into an object

{% highlight javascript %}

```javascript
const url = require("url");
const querystring = require("querystring");
const parsedUrl = url.parse(
  "http://www.google.com/?page=3&limit=10&category=nodejs&category=javascript"
);
const query = querystring.parse(parsedUrl.query);
console.log("querystring.parse():", query);
// querystring.parse(): [Object: null prototype] { page: '3', limit: '10', category:
// [ 'nodejs', 'javascript' ] }
console.log("querystring.stringify():", querystring.stringify(query));
// querystring.stringify(): page=3&limit=10&category=nodejs&category=javascript
```

{% endhighlight %}
