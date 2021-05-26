```
##
TFX
duanxz
20210507 15:37
```



### mysql

[mysql_download](MySQL8.0.24安装教程)

[MySQL8.0.24安装教程](https://blog.csdn.net/weixin_44651062/article/details/116205589?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522162036970616780261997359%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=162036970616780261997359&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-1-116205589.first_rank_v2_pc_rank_v29&utm_term=mysql8.0.24%E5%AE%89%E8%A3%85%E6%AD%A5%E9%AA%A4%E5%9B%BE%E8%A7%A3&spm=1018.2226.3001.4187)



```
## 版本变更可能导致安装方式和使用方式的不同，需注意稳定性
## if：
mysql -u root -p error 2003（HY000）：cant connect to mysql server on localhost:3306
```



[Can''t connect to MySQL server on localhost (10061)解决方法](https://www.jb51.net/article/26505.htm)



```
## 需要管理员身份运行

net stop mysql	
net start mysql

#users: root
#password:

#注意服务的维护，避免服务过程中出现断电丢失数据的情况
```



### Mysql Workbench

[Mysql Workbench_download](https://dev.mysql.com/downloads/workbench/)

[MySQL Workbench使用图文教程](https://www.jianshu.com/p/c3dcd4d9ce69)



```
## 表格生成语句

CREATE TABLE `tfx_colleague`.`tfx_colleague` (
  `id` INT NOT NULL DEFAULT 人员id,
  `name` VARCHAR(32) NULL DEFAULT '人员姓名',
  `gender` VARCHAR(8) NULL DEFAULT '性别',
  `birth` VARCHAR(64) NULL DEFAULT '出生年份',
  `main_point` VARCHAR(128) NULL DEFAULT '主攻方向',
  `remark` VARCHAR(45) NULL DEFAULT '其他',
  PRIMARY KEY (`id`))
ENGINE = InnoDB
DEFAULT CHARACTER SET = utf8
COLLATE = utf8_bin;
```



### Dbeaver

[Dbeaver_download](https://dbeaver.io/download/)

```
## 由于网络限制（可能是跨域导致），installer下载失败。
```



### git 

[git_download](https://git-scm.com/downloads)

```
git config --global user.name <用户名>
git config --global user.email <邮箱地址>
```

[git基础命令](https://www.jianshu.com/p/93318220cdce)

```
另需注意.gitignore的使用
```



