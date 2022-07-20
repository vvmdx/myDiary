# July

## 07-20

### 虚拟机数据库连接问题

虚拟机数据库用`mysqld-nt`注册服务，免安装版数据库，想宿主机navicat连接，提示`Host xxx is not allowed to connect to this mysql server`

需要进入虚拟机的mysql但是虚拟机没装`mysql.exe`

解决：

1. 官网下载一个`noinstall`版本的mysql，下完了进去把`bin`目录的`mysql.exe`拉到虚拟机里

2. 虚拟机`mysql -uroot -p`进入mysql

   ```mysql
   # 切换到mysql数据库
   use mysql;
   # 查看host是否是localhost，是的话就不允许远程连接
   select user,password,host from user where user='root';
   # 修改
   update user set host='%' where user='root';
   # 刷新配置
   flush privileges;
   ```

3. 至此宿主机就可以直接使用navicat连接虚拟机mysql了