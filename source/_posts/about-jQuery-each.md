title: 有关jQuery里.each()的用法和使用技巧
date: 2015-11-26 17:53:18
tags: [jQuery,each]
---
> `2015-11-26` 

### each函数不能用break和contiune跳出循环

可以使用`return true`和`return false`跳出，和for中跳出循环对比：

each:`return true` === for: `continue`

each:`return false` === for: `break`