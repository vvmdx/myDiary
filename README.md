# myDiary

[![GitHub Streak](https://github-readme-streak-stats.herokuapp.com/?user=vvmdx&theme=gruvbox&date_format=%5BY.%5Dn.j)](https://git.io/streak-stats)

- [myDiary](#mydiary)
- [2022](#2022)
  - [January](#january)
# 2022

## January

### 01/03

<details>
    <summary>点击展开</summary>



今天突发奇想，想做一下学习记录，当作小日记之类的（主要是想和博客分开，博客记录的都是一些专题，这里更想分享记录一些好玩的有趣的或者提高生产力的东西），一方面可以看看自己学习的进度和效率，一方面通过日记也可以倒逼自己不摸鱼（尽量...

**整了个花活**

Github连续贡献记录：可以统计总贡献/当前连续贡献天数/最长连续贡献天数，倒逼自己每天都记录的神器

项目地址：https://github.com/DenverCoder1/github-readme-streak-stats

md生成器：http://github-readme-streak-stats.herokuapp.com/demo/

使用方式：生成器里username改成自己的github名字，其他的按个人喜好修改，把markdown复制到你的md里就完事了

**整了个花活\*2**

vscode快速生成github readme的目录：https://github.com/yzhang-gh/vscode-markdown
1. vscode里搜索拓展：markdown all in one
2. 用vscode打开md

3. 用该拓展创建目录

>  各级标题多了可以试试




**github和本地git远程关联**

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

**继续整理sql注入专题总结**

今天总算把报错注入全搞定了，之前还真不知道居然有这么多种姿势，总结了一下其实很多都是因为各种函数的参数格式不正确导致的，或许将来某一天有新的函数的时候，也可以按这个方式找找新的利用姿势也说不定

</details>

### 01/04

**整了个花活**

<details>
    <summary>点击展开</summary>
没错这就是花活了，因为想着一篇日记还挺不少的，想到之前好像在github的readme看别人有代码折叠的功能，于是想着能不能把内容折叠起来方便找，就搜了一下，没想到还真的可以，不过typora的md语法和github的GFW还是有点区别的，这个虽然在github的readme上可以折叠，但是在typora里面是不可以折叠的，究其原因应该是typora的折叠属于h5标签，而h5标签里不支持md语法导致的吧（我猜的



</details>

