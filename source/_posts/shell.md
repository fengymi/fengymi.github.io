---
title: shell加密解密
date: 2016-10-13 16:32:50
tags: [shell,加密,解密]
---
<h3>shell脚本进行加密和解密操作</h3>

+ <h4>使用gzexe</h4>

使用gzexe进行shell加密或者说压缩
``` bash
    gzexe shell.sh #这时就会产生一个shell.sh（压缩文件）和shell.sh~（源文件）
```
<!--more-->
对刚才新产生的shell.sh文件进行解密
``` bash
    tail -n +44 shell.sh > new_shell.gz # 使用tail命令从第44行开始读取shell.sh文件并存入一个new_shell.gz的文件中（后缀必须为.gz,为gunzip解密使用）
    gunzip new_shell.gz #对这个.gz文件解密就能得到源码了    
```

+ <h4>使用shc</h4>

shc 安装
``` bash
    wget http://www.datsi.fi.upm.es/~frosal/sources/shc-3.8.9b.tgz
    tar vxf shc-3.8.9b.tgz
    cd shc-3.8.9b
    make test
    make install
```

shc 使用
``` bash
    #参数说明
    -e date (指定过期时间)
    -m message  （指定过期提示的信息）
    -f  script_name （指定要编译的shell路径）
    -r  relax security  （在不同操作系统执行）
    -v  Verbose compilation （输出编译的详细情况）
    #使用样例
    shc -r shell.sh # 生成的shell.sh.x是加密的可执行脚本,shell.sh.x.c是c的源代码
    shc -e 28/09/2016 -m "过期了" -f shell.sh
```

shc解密
[参考](http://blog.xuthus.cc/post/17.html)