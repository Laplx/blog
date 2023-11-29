# 首页 Welcome

![](./introg.jpg)

*（上海·上海展览中心夜）*

**更新说明**：我使用 Gitment 为网站加入了评论功能。它调用了 Github 仓库的 Issue 操作，无需第三方组件或备案，因此需要评论者拥有 Github 账号并登录来进行评论。

**勘误**：23.10.20 篇中链式法则处 $o(logK(T_1,T_2))$ 应改为 $O(logK(T_1,T_2))$；$(2)$式上方 $K(T_2|T_1) \le T(T_2)$ 应改为 $K(T_2|T_1) \le K(T_2)$。

### 这里有什么？What's here?

这里是 <font size=4 color=#006699><i>Laplx (Hao Chen)</i></font> 的 GithubPage 博客。

我会分享我创作和收集的一些文件、课题与想法。

This is my blog. I create ideas, make studies and share informations here.

### 怎么联系我？Want to contact me?

邮箱 email：laplx@foxmail.com  laplx@outlook.com(may not be receivable in China)

单位 affiliation：复旦大学经济学院 School of Economics, Fudan University, Shanghai

### 每周一句  Weekly sentence

血液的作用之一，是为信仰付出代价。

### 欢迎评论！Comments

评论需使用 Github accounts。

警告 warning：请勿发布无关内容。留言须遵守国家法律法规。Do not post irrelevant content. Comments must comply with laws and regulations.


```{div}
<div id="container"></div>
<link rel="stylesheet" href="https://imsun.github.io/gitment/style/default.css">
<script src="https://imsun.github.io/gitment/dist/gitment.browser.js"></script>
<script>
var gitment = new Gitment({
  id: 'blog ID', // default is 'location.href'
  owner: 'Laplx',
  repo: 'blog_comment',
  oauth: {
    client_id: '4a0be11acd2141eb88a2',
    client_secret: '5942a71cb0015f68c2a99f26d66afe8e91ee6624',
  },
})
gitment.render('container')
</script>
```
