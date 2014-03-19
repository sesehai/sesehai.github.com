---
layout: post
category : 教程
tagline: "Supporting tagline"
tags : [Github_blog, 初学者, jekyll]
---

#### Start with git

#####（1）初始化git

git init
git pull git@github.com:sesehai/vimwiki.git

##### (2) 提交数据

git add .
git commit -a
git push git@github.com:sesehai/vimwiki.git

##### (3)另一种初始化方法

git config --global user.name "Your Name"
git config --global user.email sesehai@gmail.com
mkdir sesehai.github.com
cd sesehai.github.com 
git init
touch README
git add README
git commit -m 'first commit'
git remote add origin git@github.com:sesehai/sesehai.github.com.git
git push -u origin master


##### github:help

[github帮助](http://help.github.com/)

