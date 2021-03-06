# February

| Sun.               | Mon.               | Tues. | Wed.              | Thur. | Fri.               | Sat.               |
| ------------------ | ------------------ | ----- | ----------------- | ----- | ------------------ | ------------------ |
|                    |                    | 1     | 2                 | 3     | 4                  | 5                  |
| 6                  | 7                  | 8     | [9 写了](#_02-09) | 10    | 11                 | 12                 |
| [13 写了](#_02-13) | 14                 | 15    | 16                | 17    | [18 写了](#_02-18) | [19 写了](#_02-19) |
| 20                 | 21                 | 22    | 23                | 24    | 25                 | 26                 |
| 27                 | [28 写了](#_02-28) |       |                   |       |                    |                    |


- [February](#february)
  - [02-09](#02-09)
    - [PicGo+Gitee](#picgogitee)
    - [Apache ShardingSphere ElasticJob-UI漏洞复现](#apache-shardingsphere-elasticjob-ui漏洞复现)
  - [02-13](#02-13)
    - [hexo pure主题 个性化](#hexo-pure主题-个性化)
  - [02-18](#02-18)
    - [整理了面试题](#整理了面试题)
    - [Github PR是啥](#github-pr是啥)
  - [02-19](#02-19)
    - [Github个人主页](#github个人主页)
  - [02-28](#02-28)
    - [Python 格式化字符串f-string](#python-格式化字符串f-string)


## 02-09

### PicGo+Gitee

之前的博客写了PicGo+Github图床设置，不过没写Gitee的，其实Gitee的设置基本和Github一致，不过PicGo默认图床没有gitee，需要在PicGo >> 插件设置 >> 搜索gitee >> 安装gitee-uploader，安装好后就有gitee图床了



### Apache ShardingSphere ElasticJob-UI漏洞复现

拖了好久的工作任务，今天终于搞定了，详情见[我的博客](https://vvmdx.github.io/2022/02/11/2022-02-11-Apache-ShardingSphere-ElasticJob-UI-%E6%BC%8F%E6%B4%9E%E5%A4%8D%E7%8E%B0/)



## 02-13

### hexo pure主题 个性化

参考1：[pure主题设计者cofess](https://blog.cofess.com/2017/11/01/hexo-blog-theme-pure-usage-description.html)

参考2：[个人觉得个性化做的很完善的博主](https://hwame.top/20200520/hello-hexo-troubleshooting.html)

整个周末都在玩博客个性化，因为想添加一些自己的东西，参考了若干资料，最终做了一些改动：

- **增加了壁纸侧边栏和壁纸页**：https://vvmdx.github.io/wallpapers/

   参考参考2的[增加相册部分](https://hwame.top/20200520/hello-hexo-troubleshooting.html#7-%E6%B7%BB%E5%8A%A0%E3%80%8C%E7%9B%B8%E5%86%8C%E3%80%8D%E9%A1%B5%E9%9D%A2)，我没有用他的样式，但是增加个性化路径方式大同小异

   1. 增加文件夹：`hexo\themes\pure\_source\wallpapers`，其中放入`index.md`

   2. 将上面的文件夹复制到`hexo\source`下，`index.md`部分如下

      ```
      ---
      title: 深度宅男的壁纸收集癖
      description: 别骂了别骂了...
      layout: wallpaper
      comments: true
      sidebar: custom
      toc: true
      ---
      正文...
      ```

      

   3. `hexo\themes\pure\layout`下新增页面模板文件`wallpaper.ejs`

      ```ejs
      <%- partial('_partial/sidebar-wallpaper', {post: page}) %>
      <main class="main" role="main">
        <%- partial('_partial/article-wallpaper', {post: page}) %>
      </main>
      ```

      

   4. `hexo\themes\pure\layout\_partial`下新增文件`article-wallpaper.ejs`

      ```ejs
      <article class="article archives-about article-type-normal" itemscope="">
        <header class="article-header">
          <h1 itemprop="title"><%= page.title %></h1>
          <% if(page.description || theme.profile.author_description) { %>
          <p class="text-muted"><%= page.description || theme.profile.author_description %></p>
          <% } %>
        </header>
        <div class="article-header">
            <div class="article-meta">
              <%- partial('post/date', {class_name: 'article-date', date_format: null}) %>
              <%- partial('post/category') %>
              <%- partial('post/tag') %>
              <%- partial('post/pv') %>
              <span class="post-comment"><i class="icon icon-comment"></i> <a href="<%- url_for(post.path) %>#comments" class="article-comment-link"><%= __('article.comments') %></a></span>
              <%- partial('post/wordcount') %>
            </div>
         </div>
        <div class="article-body">
          <%- page.content %>
        </div>
      </article>
      <% if (theme.comment.type && !is_home()) { %>
        <%- partial('post/comment', {post: page}) %>
      <% } %>
      ```

      这里面拼接了`hexo\themes\pure\layout\_partial\article.ejs`的header和`article-about.ejs`的框架

   5. `hexo\themes\pure\layout\_partial`下新增侧边栏文件`sidebar-wallpaper.ejs`

      ```ejs
      <% if (theme.config.toc && post.toc) { %>
      <aside class="sidebar sidebar-toc collapse in" id="collapseToc" itemscope itemtype="http://schema.org/WPSideBar">
        <div class="slimContent">
          <nav id="toc" class="article-toc">
      	  <a href="#top"><h3>壁纸目录~</h3></a>
            <%- toc(post.content) %>
          </nav>
        </div>
      </aside>
      <% } %>
      ```

      这里其实本来是博文下方点击”文章目录“会弹出来的地方，我观察点击前后html标签变化后发现区别在于第二行的`class="sidebar sidebar-toc collapse in"`和`class="sidebar sidebar-toc collapse"`

      ![image-20220213212934573](https://cdn.jsdelivr.net/gh/vvmdx/myImageForPicgo@main//img/image-20220213212934573.png)

      上面是目录展开状态，可以和下面对比一下，后面的`aria-expanded`和`style`参数可以不用管

      ![image-20220213213026557](https://cdn.jsdelivr.net/gh/vvmdx/myImageForPicgo@main//img/image-20220213213026557.png)

   6. 最后修改语言配置文件`hexo\themes\pure\languages\zh-CN.yml`

      ```yml
      menu:
        ...
        Wallpapers: 壁纸~
      page:
        ...
        wallpapers: 壁纸~
        wallpapers-desc: 深度宅男的壁纸收集癖...
      ```

      

   7. 当然别忘了最重要的站点配置文件`:\hexo\themes\pure\_config.yml`

      ```yml
      menu:
        ...
        Wallpapers: wallpapers
      menu_icons:
        ...
        wallpapers: icon-coding
      ```

      

## 02-18

### 整理了面试题

昨晚偶然在群里提了一嘴，好像还挺多人对面试题感兴趣的，因此整理了下自己的面试复盘

https://github.com/vvmdx/Sec-Interview-4-2023



### Github PR是啥

知乎这篇讲的真不错：https://www.zhihu.com/question/21682976/answer/79489643



## 02-19

### Github个人主页

1. 新建和自己id同名从仓库
2. 引入一个链接 ==> https://github.com/anuraghazra/github-readme-stats  看这个怎么搞就行
3. readme.md如下（以我自己为例）

```md
# vvmdx

<img align="right" src="https://github-readme-stats.vercel.app/api?username=vvmdx&theme=gruvbox&count_private=true&hide=prs&line_height=30" />

- 中度肥宅
- 二刺螈
- 误打误撞走上安全路
- 目前希望能顺利毕业+找个好工作:)

## 

博客: https://vvmdx.github.io/

<!-- <img src="https://github-readme-stats.vercel.app/api/pin/?username=vvmdx&repo=Sec-Interview-4-2023&theme=slateorange" /> -->
```

效果：

![image-20220219211414863](https://cdn.jsdelivr.net/gh/vvmdx/myImageForPicgo@main//img/image-20220219211414863.png)



## 02-28

### Python 格式化字符串f-string

今天遇到一个问题，当python使用f-string时，外层有花括号会出现`Expression fragment inside an f-string is nested too deeply`

查了后发现其实是因为在使用一个花括号来占位时，外层若还有一个花括号，则需要双写花括号如下

```python
string1 = "abc"
string2 = f"{{This is string1: {string1}}}"
print(string2)

# {This is string1: abc}
```



