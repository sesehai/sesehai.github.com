---
layout: post
category : 教程
tagline: ""
tags : [php]
title : 几个php的问题
author: SSH
---

- zend framework request router 的实现；

- empty() 判断返回true值的变量的值：
   "",0,"0",null,false,array(),var $var,没有任何属性的对象；

- error_reporting(E_ALL) 设置哪些错误、提示、警告，汇报出来；
   ini_set('display_errors',1) 是否显示错误
   ini_set('log_errors',1)     错误信息是否存入error.log
   ini_set('error_log','error.log') 设置错误存放文件
   set_error_handler() 设置自定义的错误处理方法

- json_decode($str,true); 第二个参数true 将返回的对象转换为数组

- memcache 内容如何更新：1）切换新的key（缺点耗资源）

- 生成静态文件时，同一目录下最多能放多少个文件或文件夹，而不会影响存取效率，如何解决？
   同一路径下一级子目录最多有 31998 个，如果名字是数字，都除以10000得到的整数最为父目录；

- array 排序：
   asort() 对数组按值排序，保持索引
   sort()  对数组按值排序，不保持索引
   ksort()按键值排序

- ajax 跨域请求
   ajax 的刷新

- html5 video 标签的试用？

- 静态化解决方案：
    db并发太高、表死锁频繁、php执行缓慢、积压负载 如何处理？
    db->应用之间缓存，db->静态化

- 数据统计：
    百万条数据、多表联合查询、数据去重 执行缓慢如何处理？
    去重有何方法？
