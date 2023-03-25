docker-compose创建的用户需要先使用root用户登陆以后给它赋予相关的权限才可以使用它进行数据库的连接

grant all privileges on dbname.tablename to 'username'@'ip';

比如想给用户user赋予数据库test所有的表的权限并且不限制root用户的连接地址，代码如下

grant all privileges on test.* to 'user'@'%';

flush privileges; # 刷新权限