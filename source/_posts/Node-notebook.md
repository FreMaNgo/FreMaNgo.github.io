title: Nodejs 学习笔记
date: 2015-12-03 15:30:00
tags: [前端,nodejs]
---
> 2015-12-03更新

### nodejs 程序运行方法

1. `node xxx.js`
2. `node -e "console.log('hello world!')"`

### 使用 node 的 REPL 模式

直接在终端输入`node`即可进入REPL，会出现一个`>`大于号，此时可以输入代码。

连续按两次`ctrl + c`退出REPL模式

### 使用**surpervistor**实时更新nodejs，提高效率

1. `npm install -g supervisor`
2. 使用surpervistor命令启动js `supervisor app.js`，监测到改动自动重启nodejs服务器

### nodejs单线程异步操作

``` javascript
var fs = require('fs');
fs.readFile('file.txt','utf-8',function(err,data){
    if(err){
        console.log(err);
    }else{
        console.log(data);
    }
});

console.log('finished');
```
这段代码输出：

```
finished
file.txt contents
```
**为什么先输出`finished`？**

因为异步操作的时候，运行`fs.readFile`之后就立即运行后面的`console.log('finished')`函数了，不会等到`fs.readFile`内的回调函数运行完成再运行它后面的语句。

