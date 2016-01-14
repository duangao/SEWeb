# SEWeb 文档


---

# 用户手册

## 简介
- 本系统采用Java 语言 Spring框架开发，数据库使用MySQL，软件采用MIT lisence，可访问[这里](https://github.com/lyhlgf/SEWeb)查看项目源代码；
- 本系统采用Bootstrap前端模板搭建，使用了Unify、Inspinia等多个主题的组件搭建。
- 本系统用于南京大学软件工程课程使用。

## 学生用户使用说明

###  注册要求

- 使用真实的学号进行注册；
- 使用真实的邮箱进行注册，邮箱会用在注册审核以及作业提交成功的提示中，确保该邮箱信息正确。
- 点击注册后，等待管理员审核，审核结果会通过邮箱通知；
- 若发现自己学号已被注册，请联系管理员。

### 通知查看

- 权限要求：任意权限均可；
- 首页只显示最新的3条通知，完整的通知可参加“通知”界面

### 资料下载
- 权限要求： 注册成功后方可下载资料和课件；

### 作业提交
- 权限要求： 注册成功后方可提交作业；
- 提交作业的具体说明：
    - 每次作业提交的说明中会给出作业提交的关键字，而提交的作业命名方式：关键字+学号+姓名
    - 请**注意查看作业提交的截止日期**，并在该日期前完成提交，提交成功会收到提示邮件；
    - 若实在无法按时提交，最多可以延迟2次作业的时间进行提交。比如第3次的作业最晚在第5次作业的规定截止日期前提交；

### 个人信息和密码修改
- 光标停留在在右上角自己的用户名处，可以看到弹出的修改个人信息字样，点击后按照提示进行个人信息和密码的修改；
- 修改邮箱、姓名等信息也需要输入正确的密码；

### 疑问咨询
- 如对上述内容有任何疑问，请按照首页提供的联系方式联系老师或者助教；
- 如使用系统中发现任何bug或者有更好的交互建议，可以联系开发人员[^footnote]或者在[Github](https://github.com/lyhlgf/SEWeb)下提交issuse。

## 管理员使用说明

## 管理员账户获取方式
- 管理员账户由老师指定，**不需要**进行注册；
> 老师指定的助教账户不应该和学生学号冲突；
- 除指定管理员账户外，其它权限助教同老师一致；

## 当前选课人员查看
- 可以查看当前选课的所有人员名单；
- 待审核的学生需要进行“通过”和“拒绝”的审核，审核后会自动发送对应的邮件通知该学生；

## 通知发布、修改、删除
- 使用管理员账户登录后，打开通知页面即可进行新通知的建立，已有通知的修改和删除。

## 资料的上传、修改、删除
- 使用管理员账户登陆后，打开资料页面，可以上传新的资料，或者修改已有的资料内容和删除已有资料。
- 每次可上传多个文件。
- 上传文件的磁盘位置: C:\Users\user\Resources

## 作业发布和查看
- 管理员发布作业，并提供该作业的关键字和截止日期，并且可以上传该次作业有关的附件。
- 查看已经提交的作业
    - 正常截止日期前提交的作业的文件夹命名为"关键字"，而超期1次提交的文件夹为"关键字\_01"，超期两次提交的作业所在文件夹命名为"关键字\_02";
- 已提交作业目录为   C:\Users\user\Homework

## 个人信息修改
同学生的操作步骤。

## 学生选课记录查询和审核
- 光标停留在右上角用户名处，点击学生管理。
- 页面中会分别显示:待审核列表、已审核的学生列表、助教列表（教师特有）
- 可以按照页面提示信息进行相应操作。


 [^footnote]: 开发人员联系方式：
            xxx  xxxxx@xx.com
            

# 开发人员文档

## 项目架构
采用MVC架构。

### Model
- 工程目录下src/model中存放模型，定义和数据库中表结构一致的类，以及xxxMapper类将数据库表和Java类成员进行映射；
- src/Common目录下存放xxxDAO类，用于在controller中和数据库交互；

### View
- web/static/目录下存放模板的css和javacript文件；
- web/WEB-INF目录下存放配置文件，开发者需要修改其中的数据库账户和密码字段。
- web/jsp目录下存放本网站所有网页。

### Controller
- src/Controller中存放本网站相关url的全部controller

## 项目搭建

### 环境介绍
- 操作系统： Windows 7、8、10均可 
- Java版本： 1.8.0_65，http://www.oracle.com/technetwork/cn/java/javase/downloads/index.html
- Tomcat版本：9.0.0 http://tomcat.apache.org/download-90.cgi
- IDE： IntelliJ IDEA Ultimate https://www.jetbrains.com/idea/#chooseYourEdition
- 数据库：MySQL 以及 MySQL对应的jdbc驱动  https://www.mysql.com/downloads/ https://www.mysql.com/products/connector/

### 部署
- 在IDEA 中 配置jdk 和 tomcat的目录； 
> File - Project Structure - Project 设置jdk根目录； 
> Run - Edit configurations - 添加tomcat server 并选择其所在根目录

- 在MySQL当中建立数据库和表，详细的数据库命令参加参见database.sql文件
> 数据库中需要至少插入“教师”用户，database.sql中插入的教师账户为1111，密码为root

- 修改Web/WEB-INF/SEWeb-servlet.xml文件中本地数据库用户名和密码；
- Run  login.jsp






