---
layout: post
title: Sublime Text 添加中文支持
category: 技术
tags: Sublime
keywords: 
description: 
---

1. 打开Sublime Text 3，按Ctrl+～打开控制行，复制粘贴以下python代码，然后回车运行。

2. 复制并粘贴如下代码：
```python
import urllib.request,os,hashlib; h = '7183a2d3e96f11eeadd761d777e62404e330c659d4bb41d3bdf022e94cab3cd0'; pf = 'Package Control.sublime-package'; ipp = sublime.installed_packages_path(); urllib.request.install_opener( urllib.request.build_opener( urllib.request.ProxyHandler()) ); by = urllib.request.urlopen( 'http://sublime.wbond.net/' + pf.replace(' ', '%20')).read(); dh = hashlib.sha256(by).hexdigest(); print('Error validating download (got %s instead of %s), please try manual install' % (dh, h)) if dh != h else open(os.path.join( ipp, pf), 'wb' ).write(by)
```
3. 重启Sublime Text。

4. 按Ctrl+Shift+P打开命令行，输入Install Package，回车，然后继续输入ConvertToUTF8，回车。等安装好了以后，应该问题就解决了。

5. 如果还是不行，再按照安装ConvertToUTF8的方式安装GBK Encoding Support。