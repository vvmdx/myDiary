# May

## 05-08

### Typora版本过期问题

某次电脑重启后打开一个typora的md时弹出这个窗口`This beta version of Typora is expired, please download and install a newer version.`

解决方法：把系统时间修改为2022/03/09之前

![image-20220508112705728](https://cdn.jsdelivr.net/gh/vvmdx/myImageForPicgo@main//img/image-20220508112705728.png)

然后再打开typora就可以了，不过要记得进程里随时都有至少一个typora，不然关掉后又不行了（即使偏好设置里取消了自动更新）

### ubuntu20.04 忘记密码

太久没开虚拟机给忘了密码了

方法：

1. 开机按紧shift，进GRUB界面
2. 键盘上下键切换到第一个`recovery code`，按`e`进入编辑状态（记住不是回车）
3. 上下键找到`ro recovery nomodeset`部分，把那个字段`ro`后的都删了，把`ro`改为`rw single init=/bin/bash`，Ctrl + X
4. `passwd`修改root密码，`passwd user`修改普通用户密码（user为用户名）
5. `exit`或`exec /sbin/init`退出或重启即可



## 05-31

### windows cmd/powershell 控制台乱码

如果是中文乱码的话解决方法网上都搜得到，进cmd执行`CHCP 65001`就行了

这里主要是说因为颜色控制产生的乱码

参考：https://blog.csdn.net/qq_33866817/article/details/107449610

1. 下一个东西https://github.com/adoxa/ansicon/releases

2. 下载压缩包，解压后进入x64文件夹（64位系统）

3. 此处打开cmd，执行两条命令

   ```
   ansicon.exe -i
   ansicon.exe -l
   ```

4. python打印个有颜色的命令验证

   ```
   print('\033[1;32m'+'green'+'\033[0m')
   ```

   <img src="https://cdn.jsdelivr.net/gh/vvmdx/myImageForPicgo@main//img/image-20220531232451066.png"/>

   