---
title: "如何用hugo搭建个人博客"
date: 2020-04-15T17:18:48+08:00
draft: false
---
# 如何用hugo搭建个人博客

## 1. 下载配置hugo.exe
* 从hugo官网[Hogo](https://gohugo.io/)下载hugo.exe并将hugo.exe所在路径添加至path中
* 使用hugo version查看是否安装成功
* 根据hugo官网步骤进行配置(`hugo new site <XXX>`中的`XXX`建议设置为`<github用户名>.github.io-creator`理由在后文说明)
  
## 2. 内容风格的设置
* 文本内容的编撰
  -    添加新的文章  
~~~
hugo new posts/title.md
~~~
使用此命令进行本地 .md文件的编辑 完成后保存退出即可
* 偏好设置
  -    标签等内容的个性化  
  打开config.toml文件 在此文件中进行设置
  -    主题更换
  在网络中寻适合的主题 根据上传主题进行配置即可
* 运行命令  
~~~
hugo server -D
~~~
此命令意为生成博客页面于public目录中可以通过[http://localhost:1313/  ](http://localhost:1313/)进行预览
## 3. 对public目录进行处理
  -    在github中新建一个仓库 名为`<github用户名>.github.io`
  -    进入public路径运行代码
~~~
git init
git remote add origin git@github.com:<github用户名>/<github用户名>.github.io.git
git add .
git commit
git push -u origin master
~~~
此时public目录已经上传至github仓库中
## 4. 设置github仓库
* 进入github设置界面 如下为设置完成情况
  ![](/1.png)
  此时点击图中网址即可看到自己的博客界面
## 5. 购买域名与配置
* 进入[阿里云](https://cn.aliyun.com/) 购买一个域名 进入如图页面
![](/2.png)
* 在github的help列表中查找DNS 找到下图页面
![](/3.png)
* 将DNS填入记录值中 完成域名配置
## 6. 添加域名至github
* 进入`<github用户名>.github.io`仓库的设置页面 找到Custom domain选项卡 填入买好的域名 完成添加
* 此时 我们就搭建完了属于自己博客
--------------------------
## *对生成器进行备份
 注：生成器指步骤1中`hugo new site <github用户名>.github.io-creator>`环节生成的`<github用户名>.github.io-creator`文件除了public目录外的其他所有路径
 * 在`<github用户名>.github.io-creator`目录中新建`.gitignore`并文件输入/public/ 意为将public路径隔离出去不和`XXX`一起提交
 * 在github中新建仓库`<github用户名>.github.io-creator`
 * 在`<github用户名>.github.io-creator`目录下运行代码
  ~~~
git init
git remote add origin git@github.com:<github用户名>/<github用户名>.github.io-creator.git
git add .
git commit
git push -u origin master 
  ~~~
此步骤意为防止操作失误对生成器造成改动致使无法使用。
