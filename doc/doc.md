# 2020年3月9日17:15:53
- 写一点小东西，要是有下载了这个源码的朋友，这里可以删了，因为自己还没有建立个人博客所以直接在这里写了好记录一些遇到很简单却很烦的小问题哈
- win10同时配置两个mysql(win10)
- 1 配置my.ini配置文件 主要是端口
- 2 管理员身份初始化数据库 mysqld --defaults-file=D:\MySQL\mysql-5.7.29-winx64\my.ini --initialize --console
- 3 初始化服务 mysqld install MySQL --defaults-file="D:\MySQL\mysql-5.7.29-winx64\my.ini"
- 4 启动服务 net start mysql
- 5 登录mysql  mysql -u root -p --protocol=tcp --host=localhost --port=3308（选择端口，有时候有点离谱 原本用(mysql -p3306 -uroot -p)命令是可以登录进去）提示输入密码 然后输入初始化密码却是错误 换一下用上面的命令就可以进去没有明白，我用mysql -uroot -p 这个命令很久没有出问题就今天测试出问题硬是登录不进去。
- 6 ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'newpassword';
