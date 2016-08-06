---
title: Scrapy版本导致txweb.py缺失导致Scrapyd无法启动的问题解决方法
date: 2016-07-16 21:58:14
categories: 
- Develop
tags: 
- Python
- Scrapy
---
# 问题概述
[Scrapy](https://github.com/scrapy/scrapy)升级到V1.0以上之后, 在**scrapy/utils/**缺少了原有的**txweb.py**文件, 这会导致[Scrapyd](https://github.com/scrapy/scrapyd)无法正常启动, 对应的版本号为V1.1.

* Scrapy: V1.1
* Scrapyd: V1.1

```
exceptions.ImportError: No module named txweb

Failed to load application: No module named txweb
```

# 解决方案
在安装了Scrapyd的机器上, 手动的将**txweb.py**拷贝到Scrapy的目录下.

我在Linux(Ubuntu 14.04)上的Scrapy目录地址是**/usr/local/lib/python2.7/dist-packages/scrapy/utils**

# 查找Python安装路径的方法
```
from distutils.sysconfig import get_python_lib
print (get_python_lib())
```
