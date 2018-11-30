title: alipay ios集成
date: 2016-11-18 10:30:37
tags:
---
title: alipay ios集成
tags:
---

ios字符串拼接使用@符号

resultStatus，状态码，SDK里没对应信息，第一个文档里有提到：
9000 订单支付成功
8000 正在处理中
4000 订单支付失败
6001 用户中途取消
6002 网络连接出错

xcode7.1，ios9.1打开会出现6002
在support files 中找到xxx-info.plist
并在其中添加
```bash
<key>NSAppTransportSecurity</key>
	<dict>
		<key>NSAllowsArbitraryLoads</key>
		<true/>
	</dict>
    
```


如何添加framework and bundle

在build phases中添加

ios中h文件和m文件的区别

h 为pulic
m为private

如何添加点击事件

将依赖放倒项目中，再在General>Frameworks中添加

假如遇到

```aa
Cannot find interface declaration for 'NSObject', superclass of 'Base64'
```
需要这样
```qq
#import <Foundation/Foundation.h>
```
添加alipayframework，需要将framework放到项目下。

```error
Unknown type name ‘NSString‘ "或者"Unknown type name ‘NSData‘ "等不识别常见类的问题。
```
需要建立.pch文件

```error
集成SDK编译时找不到 openssl/asn1.h 文件
```
```sol
$(inherited) /Applications/Xcode.app/Contents/Developer/Toolchains/XcodeDefault.xctoolchain/usr/include $(SRCROOT)/AliSDKDemo

header中需要添加这几个路径

```


```error
linker command failed 

添加依赖
libc++.dylib
libz.dylib
```

添加appshema






