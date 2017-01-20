---
Title: 在GitHub使用jekyll建站记录
date: 2013-07-24
category: linux
tags: debian, linux, jekyll
slug: 2013-jekyll-blog-on-github
---

LINUX下的安装命令

	#aptitude install ruby ruby-dev
	#gem install jekyll
	#gem install rdiscount

安装rdiscount是因为默认的maruku对我写的md文档有些会报错，没心思研究为什么，换rdiscount解决了

WINDOWS install

不记得具体步骤了，网上搜一下windows jekyll会有大把的信息。记录下遇到的问题：

1. 使用安装版的RubyInstaller，我用ZIP版的时间发生一个莫明其妙的问题  
2. 修改convertible.rb文件解决中文会出错，加入:encoding => "utf-8".参考路径C:\Ruby\lib\ruby\gems\1.9.1\gems\jekyll-1.0.3\lib\jekyll

        self.content = File.read(File.join(base, name),:encoding => "utf-8")

建个站点

	$jekyll new sitename
	$cd sitename
	$jekyll server

现在可以在本机通过http://localhost:4000 查看效果了,

修改_config.yml，加入下面一行

	markdown: rdiscount

让jettly使用rdiscount解析markdown文档

绑域名，我绑的是二级域名，按GitHub上的说明看顶域和二级域是不同的。  
修改域名绑定，加入一个CNAME,值填对应的[youname].github.io  
GitHub项目中建立CNAME文件，填上要绑的二级域名
