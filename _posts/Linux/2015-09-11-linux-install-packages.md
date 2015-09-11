---
layout: post
title: PHPUnit
category: Linux
tags: Linux
description: Linux 安装包依赖
---
### 系统环境
<pre><code>
Distributor ID:	Ubuntu
Description:	Ubuntu 14.04.1 LTS
Release:	14.04
Codename:	trusty
</code></pre>

### 遇到问题
使用apt-get install php5安装成功,由于自己的瞎折腾，导致php环境坏掉.
再次安装也没有问题。
但是安装php5-dev包的时候出现问题.

安装php5-dbg,我记得是提示是否升级包.我选择Y导致php好像都被移除了. 暂时都没找到原因

###### 提示错误信息
`ubuntu E: Package 'shtool' has no installation candidate`
提示shtool包没有安装.
下意识执行 sudo apt-get install shtool包.

没有！apt-get update之后也没有.换源之后也还是没有(163的源).

###解决方法
在官方软件包地址
<b>`packages.ubuntu.com`</b>
中搜索shtool包,下载对应版本的软件安装包(deb).

执行`sudo dpkg -i shtool_xxxxx_all.deb`安装shtool.

然后就可以执行`sudo apt-get install php5-dev`.

当然中间还是会有另外的一些包的依赖

###总结
在我个人，Linux中包的依赖关系比较复杂.所以使用apt-get(ubuntu下)或yum无法安装依赖包的话.最快的解决方法是在官方软件包地址中找到然后下载安装.

###### Ubuntu 软件安装包地址

 **`packages.ubuntu.com`**


