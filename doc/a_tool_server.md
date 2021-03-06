#本地server

##简介
* 前端开发有时候我们需要引入线上静态资源，而本地并不关注这些资源，比如公共脚本jQuery，公共头尾样式图片等。
* 利用server，我们可以把线上资源指定在本地目录，如果本地有和线上相同路径的资源，如果没有则直接取线上。
* 完全可取代Fiddler，真正实现本地半离线开发，无需修改一次提交一次代码到测试服务器。

##使用方法

* 安装[chrome插件host文件管理工具](https://chrome.google.com/webstore/detail/kpfmckjjpabojdhlncnccfhkfhbmnjfi) , 此工具支持即时切换hosts，无须浏览多次刷新页面，同时不修改系统的默认hosts，我们的server即基于此规则来取，如果本地没有资源直接用线上来取。

* 在任意项目文件夹执行

		jdf build -combo

* 或者磁盘任意文件下执行
	
		jdf server

这样本地server就跑出来了，默认端口号为80端口

* 用hosts切换工具把静态资源cdn路径配置本地hosts，如

	cdn.com 127.0.0.1

* 项目联调阶段：本地修改项目文件夹下的静态文件，刷新浏览器下，我们会发现，cdn域名下的静态文件即指定我们修改后的文件
* 线上调试BUG阶段：下载某一线上对应svn下的静态文件，修改，刷新浏览器即可进行调试，因为本地没有静态资源我们的server会从线上直接抓取

##todo

* url映射本地指定目录配置
* ip访问
* combo合并的文件也从本地来取
* 可配置指定文件类型转发
* css合并后的文件如何本地开发?
