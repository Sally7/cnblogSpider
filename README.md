# 基于 nodejs 的博客园爬虫项目

运行方式
```
node index.js
```

## 相关博文

具体使用请看：

[【node爬虫】前端爬虫系列「博客园」爬虫](http://www.cnblogs.com/coco1s/p/4954063.html)

年代久远，博客园接口如果改动，爬虫很可能失效。

## license 
MIT

#使用原demo 报错或得不到正确结果对原demo修改如下
1.第19行
pageUrls.push('https://www.cnblogs.com/?CategoryId=808&CategoryType=%22SiteHome%22&ItemListActionName=%22AggSitePostList%22&PageIndex='+ i +'&ParentCategoryId=0&TotalPostCount=4000')
2.第97行
superagent.get(url)
3.作者等统计不对
第121行
var appUrl = 'https://www.cnblogs.com/'+currentBlogApp+'/ajax/news.aspx';

在写入mysql表的时候，更新表在插入数据前，执行第二次 才会正确
解决方案思路：更新表和写入表的顺序注意一下

为了方便，只爬取了一页的数据 存入了mysql表，修改一下pageNum,避免多文章对应一个作者，可以把requestId作为唯一值
现在用的是 currentBlogApp