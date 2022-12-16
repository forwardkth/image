title: 关于Hexo next主题如何在首页隐藏指定的文章
date: 2016-05-08 22:21:29
tags: 
- hexo
- next
categories: Notes-随笔
---

<meta name="referrer" content="no-referrer" />

之前我有一个关于next主题的需求就是希望可以在next主题的主页只显示特定category下的文章。这样就可以在home 首页下控制想要突出展示的文章。
比如我的博客下混合了技术类和生活类文章，我可以选择只在首页展示技术类的，而其他类别的文章不会在首页列出，但是可以到category里面点击查看。
这样就不用像以前的老博客那样开两个博客再链接了。
https://github.com/iissnan/hexo-theme-next/issues/843
具体做法如下：
<!-- more -->
  
### 修改next主题文件夹下的layout中的index.swig文件
  
定位修改 post_template.render(post, true) 
 
![](https://ww1.sinaimg.cn/large/74505a4cgw1f3onp6eculj20ds0d70vb.jpg)

其中修改的是为文章的首页显示添加判断条件

### 在新的post中添加visible字段来控制是否首页显示
例如我的当前这篇文章：
  
title: 关于Hexo next主题如何在首页隐藏指定的文章
date: 2016-05-08 22:21:29
tags: 
...
...
categories: Notes-随笔
visible: hide   这里如果加上hide则该文章就不会在文章首页显示，如果留空则表示默认显示
.....

### 在单独的category下 显示归类的多篇文章目录

看这里
https://www.zhihu.com/question/33324071/answer/58775540?group_id=654307162210365440#comment-106092511