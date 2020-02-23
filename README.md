一键生成官网(全)

准备工作：

1：阿里云服务器一台(centos7.4 64 最少1核2G)并开通oss,并准备好解析好的域名

2: 安全组开放80端口 22端口

3：远程登陆服务器

4：命令行键入(大概60分钟左右完成安装)

wget -P /root https://babyrita.oss-cn-beijing.aliyuncs.com/lnmp/quyeweb/new_blog.zip 

&& wget -P /root https://babyrita.oss-cn-beijing.aliyuncs.com/lnmp/quyeweb/shell.zip 

&& wget -P /root https://babyrita.oss-cn-beijing.aliyuncs.com/lnmp/quyeweb/ziliao.zip 

&& yum -y install unzip && unzip shell.zip && unzip ziliao.zip 
&& chmod +x /root/shell/* 
&& echo host_name > host_name.txt && /root/shell/lnmp-install.sh

命令中host_name换成你的域名

完成后Ctrl+c退出
或者直接从git上下载new_blog.zip shell.zip ziliao.zip 放在root目录下unzip 解压后执行下面命令：

yum -y install unzip && unzip shell.zip 
&& unzip ziliao.zip 
&& chmod +x /root/shell/* 
<<<<<<< Updated upstream
&& echo host_name > host_name.txt 
=======
&& echo test.perktrees.com > host_name.txt 
>>>>>>> Stashed changes
&& /root/shell/lnmp-install.sh


5：后台操作(oss账号与密码配置，保证图片可以上传oss，不放自家服务器比较安全) 
后台地址为：host_name/admin 前台地址为：http://host_name
账号密码为：admin 123456





集成的thinkphp5代码介绍

1：基于php7.0.30+thinkphp5及前端layui框架（lnmp架构mysql5.6.40，存储引擎innodb）

2：后台基础功能介绍

（1）权限控制可控制到增删改查

（2）集成phpexcel导入导出功能

（3）文章系统（单图上传，多图上传，百度编辑器）

（4）laydate日期时间控制

3：api接口基础功能介绍
 
（1）版本控制
 
（2）接口数据：AES加密（对称加密，app接口用此加密方式，速度快，就可以了，app包必须加密）本框架AES暂时支持至php7.0如升至php7.1以上，可能
还需要做处理！！！

4：wap端建议用vue.js
  
（1）版本控制
 
（2）接口数据：RSA加密（非对称加密，安全性高，速度慢）
  
（3）如果有比较高的安全性要求可用https加密

5：application下的config.php 整体架构配置都放这个文件
   application下的database.php数据库配置
   
application下的common.php一些常用的公共函数
   index.php放在根目录下
  
 robots.txt暂时放开所有权限，如果有不想被收录的可以自行设置！
   
memcache.php可以在线查看memcache里面的数据！！！建设线上去掉，或者设置不可访问！！！
   
本架构路由，本着兼容，采取混和模式，不过本人建议最好还是都用rewrite模式！！！
  
 第三方扩展类库可放在extend和vendor，他们的区别自己看手册！！！

6：基本架构lnmp+memcache+redis（memcache主要存放session，redis主要存放一些不频繁更新的大内容数据比如：文章内容等）index模块下的index控制器里面有相关调用
方法，可以直接拿去用！！！

7：接口文档采用第三方--showdoc
   访问地址为：showdoc.xxxx.com

8：blog.babyrita.com有关于Php优化,mysql优化及相关mysql基础知识点的内容，相关开发人员在码代码时，注意Php优化，建表时，写sql多参照blog.babyrita.com中的内容进行优化，
写完代码，有空要再多想是不是有可以再优化的地方！！

等等，集成了太多东西，我自己都忘了！
   
   

<<<<<<< Updated upstream
更多详情请看：http://www.wnwblog.com
=======
更多详情请看：http://www.wnwblog.com
>>>>>>> Stashed changes
