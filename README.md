# myDiary

<div align=center>
<img src="https://github-readme-streak-stats.herokuapp.com/?user=vvmdx&theme=gruvbox&date_format=%5BY.%5Dn.j" width=120%/>

</div>

<div align=center>
<img src="https://ghchart.rshah.org/vvmdx" width=120%/>
</div>



- [January](#january)
  - [01-03<span id="0103"></span>](#01-03)
    - [Github连续贡献记录](#github连续贡献记录)
    - [vscode快速生成github readme目录](#vscode快速生成github-readme目录)
    - [github和本地git远程关联](#github和本地git远程关联)
    - [继续整理sql注入专题总结（到时更新到博客上](#继续整理sql注入专题总结到时更新到博客上)
  - [01-04<span id="0104"></span>](#01-04)
    - [Github readme 部分折叠](#github-readme-部分折叠)
    - [Github连续贡献样式优化](#github连续贡献样式优化)
    - [markdown日历+锚点](#markdown日历锚点)
    - [github代码贡献图](#github代码贡献图)


# 2022

## January

| Sunday         | Monday                | Tuesday                 | Wednesday           | Thursday | Friday | Saturday   |
| -------------- | --------------------- | ----------------------- | ------------------- | -------- | ------ | ---------- |
|                |                       |                         |                     |          |        | 1 出去玩了 |
| 2 学半天玩半天 | [3 开始写日记](#0103) | [4 做了好多优化](#0104) | [5 准备入职](#0105) | 6        | 7      | 8          |
| 9              | 10                    | 11                      | 12                  | 13       | 14     | 15         |
| 16             | 17                    | 18                      | 19                  | 20       | 21     | 22         |
| 23             | 24                    | 25                      | 26                  | 27       | 28     | 29         |
| 30             | 31                    |                         |                     |          |        |            |



### 01-03<span id="0103"></span>

<details>
    <summary>点击展开</summary>



今天突发奇想，想做一下学习记录，当作小日记之类的（主要是想和博客分开，博客记录的都是一些专题，这里更想分享记录一些好玩的有趣的或者提高生产力的东西），一方面可以看看自己学习的进度和效率，一方面通过日记也可以倒逼自己不摸鱼（尽量...

#### Github连续贡献记录

Github连续贡献记录：可以统计总贡献/当前连续贡献天数/最长连续贡献天数，倒逼自己每天都记录的神器

项目地址：https://github.com/DenverCoder1/github-readme-streak-stats

md生成器：http://github-readme-streak-stats.herokuapp.com/demo/

使用方式：生成器里username改成自己的github名字，其他的按个人喜好修改，把markdown复制到你的md里就完事了

#### vscode快速生成github readme目录

vscode快速生成github readme的目录：https://github.com/yzhang-gh/vscode-markdown
1. vscode里搜索拓展：markdown all in one

2. 用vscode打开md，右键找命令面板（或`ctrl+shift+p`）

   <img src="https://cdn.jsdelivr.net/gh/vvmdx/myImageForPicgo@main//img/image-20220105124111665.png" width=60%/>

3. 点击创建目录即可

>  各级标题多了可以试试

注：标题内含空格的话，生成的目录跳转标志里面也会包含空格，但是在GFW内空格会变为`-`，导致跳转不了

例如

标题：`Github is Good` 

目录：`[Github is Good](#Github is Good)`

Github的索引以url呈现：`https//github.com/user/repo#Github-is-Good`，因此会找不到`Github-is-Good`这个跳转锚点

#### github和本地git远程关联

1. github新建个仓库

2. 本地新建个文件夹，路径不带中文

3. 文件夹下打开git cmd，`git init`

4. 与远程仓库绑定

   - ssh：` git remote add origin git@github.com:vvmdx/myDiary.git`
   - https：` git remote add origin https://github.com/vvmdx/myDiary.git`

   - 我ssh整完了连不上，在合并仓库的时候会报

     ```bash
     $ git pull --rebase origin main
     
     ssh: connect to host github.com port 22: Connection timed out
     fatal: Could not read from remote repository.
     
     Please make sure you have the correct access rights
     and the repository exists.
     ```

     查了下，改成https就好了，修改步骤：

     - 移除远程仓库配置 `git remote rm origin` 
     - 重新添加 ` git remote add origin https://github.com/vvmdx/myDiary.git`

5. 查看远程仓库：

   ```bash
   $ git remote -v
   origin  https://github.com/vvmdx/myDiary.git (fetch)
   origin  https://github.com/vvmdx/myDiary.git (push)
   ```

6. 拉取

   ```bash
   $ git pull origin main
   remote: Enumerating objects: 3, done.
   remote: Counting objects: 100% (3/3), done.
   remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
   Unpacking objects: 100% (3/3), 615 bytes | 55.00 KiB/s, done.
   From https://github.com/vvmdx/myDiary
    * branch            main       -> FETCH_HEAD
    * [new branch]      main       -> origin/main
   ```

7. 由于github现在默认是main分支，而本地git init的还是master分支，所以要改下

   - 新建分支`git checkout -b main`
   - 合并分支`git merge master`

8. 把所有东西添加到缓存区 `git add .`

9. 查看仓库和缓存区哪里不一样（修改了的意思）`git status`

10. 提交到本地 `git commit -m '随便写'`

11. 推送到远程 `git push origin main`

#### 继续整理sql注入专题总结（到时更新到博客上

今天总算把报错注入全搞定了，之前还真不知道居然有这么多种姿势，总结了一下其实很多都是因为各种函数的参数格式不正确导致的，或许将来某一天有新的函数的时候，也可以按这个方式找找新的利用姿势也说不定

</details>

### 01-04<span id="0104"></span>

<details>
    <summary>点击展开</summary>


#### Github readme 部分折叠

因为想着一篇日记还挺不少的，想到之前好像在github的readme看别人有代码折叠的功能，于是想着能不能把内容折叠起来方便找，就搜了一下，没想到还真的可以，不过typora的md语法和github的GFW还是有点区别的，这个虽然在github的readme上可以折叠，但是在typora里面是不可以折叠的，究其原因应该是typora的折叠属于h5标签，而h5标签里不支持md语法导致的吧（我猜的


格式：

```html
<details>
    <summary>点击展开</summary>
    markdown...
</details>
```

如果是在typora里编辑的话，就不用在html块里写了，这是md和GFW语法差异导致的

<img src="https://cdn.jsdelivr.net/gh/vvmdx/myImageForPicgo@main//img/image-20220104101045890.png" width=80% />

其实上面也属于优化的一部分...不过图都截了，懒得改标题了

#### Github连续贡献样式优化

修改了1月3日记中提到的，放在最上面的连续贡献展示，我嫌之前的太小，而且没居中

```
# 修改前生成器生成的md如下
[![GitHub Streak](https://github-readme-streak-stats.herokuapp.com/?user=vvmdx&theme=gruvbox&date_format=%5BY.%5Dn.j)](https://git.io/streak-stats)

# 原版点击后会跳转到项目地址 https://git.io/streak-stats，这里也去掉了
# 添加了大小控制、居中
<div align=center>

<img src="https://github-readme-streak-stats.herokuapp.com/?user=vvmdx&theme=gruvbox&date_format=%5BY.%5Dn.j" width=120%/>
</div>
```

#### markdown日历+锚点

添加了一个日历，一月下面那个，本来想找个日历的插件，或者看看有没有markdown支持的原生语法，不过没找着，，直接用插入表格的形式作为日历吧...（莫名还挺合适的u1s1）

插入表格后还有一个，就是可以直接点击日历某一天跳转到详细日记的地方，这里用md原生的页内跳转好像有时不太行

```
# md原生的页内跳转，其实和普通的超链接是一样的，标题就是需要跳转到的地方
[名字](#标题)
# 这里使用锚点来跳转，问题会少一些
1. 在页面任一位置插入锚点 <span id="随便写"></span>
	这里用<div id=""></div>或者<a id=""></a>都可以，重点在于id
2. 使用[名字](#id) id为随便写的内容
3. github的readme里点击即可跳转，typora里要按住ctrl再点击
```

#### github代码贡献图

也就是最上面的第二个图，来自于github的代码贡献图，官方没有直接提供api，不过有获取贡献量的接口和js，因此各路大神也整了不少花里胡哨的，虽然我也想整，但是大多是用在博客里的，放github的readme里属实是ntr，不过还是记录一下，说不定什么时候就开始玩起来了呢

本文用的：https://github.com/2016rshah/githubchart-api

大神博客自己整的：https://zfe.space/post/hexo-githubcalendar.html

Github上高star的项目1：https://github.com/Bloggify/github-calendar

Github上高star的项目2：https://github.com/sallar/github-contributions-chart

顺便授人鱼不如授人与渔，GitHub搜索关键字：github calendar、github chart、github contribution大概就能搜到了

</details>

### 01-05<span id="0105"></span>

<details>
    <summary>点击展开</summary>


本来打算年后入职的，昨晚导师联系后建议年前过去，遂要在一周内买机票、找房子、找找厚衣服（上海比广州冷多了...），还得和学院申请出省，收拾宿舍（大概下学期也不怎么回来了吧），虽然不是第一次实习了，但确实是第一次正儿八经的独自在外面生活，还是有点慌的

昨晚东西整一半去打球了，其实是想把个人日记搭到我的vps上的，今天看看能不能整完

#### 在云服务器上搭建个人云笔记/博客

腾讯云+PuTTY+宝塔

**腾讯云**

使用远程软件登录云服务器，看[官方文档](https://cloud.tencent.com/document/product/1207/44578)就行，十分详细

**PuTTY**

按上面的官方文档搞，不用下载msi去安装，直接下个putty.exe就行

**宝塔**

云服务器安装宝塔官方文档：https://www.bt.cn/admin/servers

1. 登录云服务器切换到root

2. 执行`yum install -y wget && wget -O install.sh http://download.bt.cn/install/install_6.0.sh && sh install.sh ed8484bec`安装

3. 完了会给你个登录的url、username、password

   ![image-20220105205054845](https://cdn.jsdelivr.net/gh/vvmdx/myImageForPicgo@main//img/image-20220105205054845.png)

4. 腾讯云控制台防火墙添加规则

   ![image-20220105205807669](https://cdn.jsdelivr.net/gh/vvmdx/myImageForPicgo@main//img/image-20220105205807669.png)

5. 将第3步的外网面板地址复制到浏览器访问

6. 使用第3步给的账密登录，首次登录要先绑定宝塔账号

7. 

</details>

