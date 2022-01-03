# myDiary

[![GitHub Streak](https://github-readme-streak-stats.herokuapp.com/?user=vvmdx&theme=gruvbox&date_format=%5BY.%5Dn.j)](https://git.io/streak-stats)

# 2022

## January

### 01/03

今天突发奇想，想做一下学习记录，当作小日记之类的（主要是想和博客分开，博客记录的都是一些专题，这里更想分享记录一些好玩的有趣的或者提高生产力的东西），一方面可以看看自己学习的进度和效率，一方面通过日记也可以倒逼自己不摸鱼（尽量...

**整了个花活**

Github连续贡献记录：可以统计总贡献/当前连续贡献天数/最长连续贡献天数，倒逼自己每天都记录的神器

项目地址：https://github.com/DenverCoder1/github-readme-streak-stats

md生成器：http://github-readme-streak-stats.herokuapp.com/demo/

使用方式：生成器里username改成自己的github名字，其他的按个人喜好修改，把markdown复制到你的md里就完事了

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

   

**继续整理sql注入专题总结**

今天看了

