---
layout: post
title: iterm2添加连接远程服务器的脚本. 方便以后连接服务器
categories: Tools
description: iterm2添加连接远程服务器的脚本. 方便以后连接服务器.
keywords: iterm2, iterm
---

iterm2添加连接远程服务器的脚本. 方便以后连接服务器, 使用起来太方便了.


方法, 如图:

![-w600](/images/posts/14901486312469.jpg)


重点是箭头指向的地方:

填入的格式:
`expect /Users/qiuyu/iterm_login_shell/192.168.10.2`

其中
`/Users/qiuyu/iterm_login_shell/192.168.10.2`是我的文件路径. 如图:

![-w400](/images/posts/14901484425066.jpg)

内容如下:

```shell
#!/usr/bin/expect -f
set user root
set host 192.168.10.2
set password 111111
set timeout -1

spawn ssh $user@$host
expect "*assword:*"
send "$password\r"
interact
expect eof
```

这样, 以后按`command+o`, 就可以呼出选项了. 

![-ww600](/images/posts/14901490028120.jpg)




