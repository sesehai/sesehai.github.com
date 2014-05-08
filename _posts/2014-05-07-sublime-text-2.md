---
layout: post
category : 教程
tagline: ""
tags : [Sublime Text 2]
title : 使用Sublime Text 2
author: SSH
---

做web程序开发，开发语言（html,javascript,php,python,go）,要选择一个轻便、快捷的编辑器，那么Sublime Text 2是个不错的选择；
<!--break-->

#### 使用Sublime Text 2（windows系统为例）

##### 1. 安装Sublime Text 2

下载Sublime Text 2，[http://www.sublimetext.com/](http://www.sublimetext.com/)
备注：如无法访问，需要翻墙；
安装下载的文件

##### 2. Sublime Text 2插件安装

　　Sublime Text 2安装的插件和所有预置的插件全部在Packages文件下，可以直接通过”preferences“—>”Browse Pakcages“来访问。

Sublime Text 2安装插件有两种方法：
	1) 离线安装，先下载好安装包，解压之后放到Packages文件夹下，重启Sublime即可。
	2) 在线安装，在线安装之前，需要安装”Packages Control“这个包管理插件，安装方法是：
		选择”查看“—>”显示控制台“，然后在下面弹出的框中输入：

			import urllib2,os;pf='Package Control.sublime-package';ipp=sublime.installed_packages_path();os.makedirs(ipp) if not os.path.exists(ipp) else None;open(os.path.join(ipp,pf),'wb').write(urllib2.urlopen('http://sublime.wbond.net/'+pf.replace(' ','%20')).read())

　　　　然后回车确认，安装完毕之后重启sublime，如果发现在Perferences中看到package control这一项，则安装成功。
		插件使用方法：Ctrl+Shift+P 调用命令面板，我们就会找到一些以“Package Control:”开头的命令，我们常用到的就是几个 Install Package (安装扩展)、List Packages (列出全部扩展)、Remove Package (移除扩展)、Upgrade Package (升级扩展)

##### 3. Build System的配置（php为例）

通过“preferences”->"Package Settings"->"Package Control"->"Settings - User"打开 “Package Control.sublime-settings” 文件，再打开的文件上点击鼠标右键选择“Open Containing Folder...” 打开目录；在该目录下创建文件“PHP.sublime-build”，内容如下：

		{
		"cmd": ["D:\\Program Files\\xampp\\php\\php.exe", "$file"],
		"file_regex": "^(...*?):([0-9]*):?([0-9]*)",
		"selector": "source.php"
		}

其中 "D:\\Program Files\\xampp\\php\\php.exe" 是我本机的php路径

##### 4. Sublime Text 2 快捷键

		Ctrl+D 选词 （反复按快捷键，即可继续向下同时选中下一个相同的文本进行同时编辑）
		Ctrl+G 跳转到相应的行
		Ctrl+J 合并行（已选择需要合并的多行时）
		Ctrl+L 选择整行（按住-继续选择下行）
		Ctrl+M 光标移动至括号内开始或结束的位置
		Ctrl+T 词互换
		Ctrl+U 软撤销
		Ctrl+P 查找当前项目中的文件和快速搜索；输入 @ 查找文件主标题/函数；或者输入 : 跳转到文件某行；
		Ctrl+R 快速列出/跳转到某个函数
		Ctrl+K Backspace 从光标处删除至行首
		Ctrl+K+B 开启/关闭侧边栏
		Ctrl+KK 从光标处删除至行尾
		Ctrl+K+T 折叠属性
		Ctrl+K+U 改为大写
		Ctrl+K+L 改为小写
		Ctrl+K+0 展开所有
		Ctrl+Enter 插入行后（快速换行）
		Ctrl+Tab 当前窗口中的标签页切换

		Ctrl+Shift+A 选择光标位置父标签对儿
		Ctrl+Shift+D 复制光标所在整行，插入在该行之前
		ctrl+shift+F 在文件夹内查找，与普通编辑器不同的地方是sublime允许添加多个文件夹进行查找
		Ctrl+Shift+K 删除整行
		Ctrl+Shift+L 鼠标选中多行（按下快捷键），即可同时编辑这些行
		Ctrl+Shift+M 选择括号内的内容（按住-继续选择父括号）
		Ctrl+Shift+P 打开命令面板
		Ctrl+Shift+/ 注释已选择内容
		Ctrl+Shift+↑可以移动此行代码，与上行互换
		Ctrl+Shift+↓可以移动此行代码，与下行互换
		Ctrl+Shift+[ 折叠代码
		Ctrl+Shift+] 展开代码
		Ctrl+Shift+Enter 光标前插入行
		Ctrl+PageDown 、Ctrl+PageUp 文件按开启的前后顺序切换

		Ctrl+Z 撤销
		Ctrl+Y 恢复撤销
		Ctrl+F2 设置书签
		Ctrl+/ 注释整行（如已选择内容，同“Ctrl+Shift+/”效果）
		Ctrl+鼠标左键 可以同时选择要编辑的多处文本

		Shift+鼠标右键（或使用鼠标中键）可以用鼠标进行竖向多行选择
		Shift+F2 上一个书签
		Shift+Tab 去除缩进
		Alt+Shift+1（非小键盘）窗口分屏，恢复默认1屏
		Alt+Shift+2 左右分屏-2列
		Alt+Shift+3 左右分屏-3列
		Alt+Shift+4 左右分屏-4列
		Alt+Shift+5 等分4屏
		Alt+Shift+8 垂直分屏-2屏
		Alt+Shift+9 垂直分屏-3屏

		Alt+. 闭合当前标签
		Alt+F3 选中文本按下快捷键，即可一次性选择全部的相同文本进行同时编辑

		Tab 缩进 自动完成
		F2 下一个书签
		F6 检测语法错误
		F9 行排序(按a-z)
		F11 全屏模式