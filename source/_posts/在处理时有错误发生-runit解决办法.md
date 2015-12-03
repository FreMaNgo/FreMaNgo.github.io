title: '在处理时有错误发生:runit解决办法'
date: 2015-12-04 00:32:33
tags: [linux]
---
在安装git的时候出现`在处理时有错误发生:runit`这个错误，如图：

![error](/uploads/error1.png)

还有报错：

`stop: Unable to connect to Upstart: Failed to connect to socket /com/ubuntu/upstart: Connection refused`

`start: Unable to connect to Upstart: Failed to connect to socket /com/ubuntu/upstart: Connection refused`

解决办法:

```
dpkg-divert --local --rename --add /sbin/initctl
ln -s /bin/true /sbin/initctl
```

再重新运行之前的代码，就不会出错了.
