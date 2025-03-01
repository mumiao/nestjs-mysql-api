## 一、项目介绍

* 1、项目前端采用`react`开发的。前端项目地址
  * [`github`地址](https://github.com/kuangshp/nestjs-mysql-api-react)
  * [码云地址](https://gitee.com/k_2021/nestjs-mysql-api-react)
  * 如果你不会`react`，你可以参考[前端vue基础项目模板](https://github.com/kuangshp/vue3-admin)来完成
* 2、采用`angular`模块化开发方式来构建项目，如果你想用`java`的`mvc`方式来开发`nestjs`项目你可以查看`v1`分支。
* 3、项目是基于`mysql`数据库，项目中全部采用`typeorm`来操作数据库，弱化了原生`sql`，避免前端的小伙伴没有`sql`基础。
* 4、实现用户名、手机号码、邮箱任一的方式实现登录。
* 5、使用自定义`token`的方式进行登录鉴权，采用自定义装饰器结合守卫来实现对接口鉴权拦截访问。
* 6、实现单点登录功能，同一时间只能一个地方登录
* 7、如果你要演示菜单权限和接口权限，请自己创建账号、角色、分配菜单和接口权限。
* 8、使用`winston`做日志管理，并且根据小时来拆分日志
* 9、自定义装饰器实现对接口权限收集，如果这个接口要给角色分配权限的时候就直接加上装饰器，会自动在数据库生成数据

## 二、使用项目

* 1、本项目仅仅是实现了`rbac`的权限系统，对于其他的功能需要自己基于这个基础上去扩展

* 2、先在本地创建数据库

* 3、在项目的根目录的`.env`文件修改为你自己的数据库基本配置(地址、用户名、密码、数据库)

  ```properties
  DB_HOST=localhost
  DB_USERNAME=root
  DB_PASSWORD=123456
  DB_DATABASE=nestjs-mysql
  ```

* 4、安装依赖包

* 5、启动项目

  ```shell
  npm run start:dev
  ```

* 5、运行项目会自动初始化菜单数据和用户数据(账号:`admin`,密码:123456)

* 6、如果你想初始化别的数据,可以在`src/services/init-db`中写上你要初始化的数据

## 二、主要实现功能

- [x] 实现用户的登录、登录鉴权、单点登录、菜单权限、接口权限

- [x] 基于`RBAC`实现权限控制

- [x] 集成`swagger`文档

- [x] `ecosystem.config.js`是采用`PM2`的配置文件,项目开发完后直接运行命令一键部署

  ```shell
  npm run build
  # 开发环境
  npm run pm2:dev
  # 生产环境
  npm run pm2:prod
  ```

- [x] `winston`日志系统根据小时来划分日志管理,如果要实时查看日志，直接使用`PM2`查看日志

  ```shell
  pm2 log
  ```

- [x] 自定义装饰器，被装饰器装饰的接口会自动进行入库操作

## 三、技术解答

> 本项目还在持续集成新功能进来,最后会加上前端做一个`cms`系统的`api`,后期会拉分支使用`graphql`提供`api`

- 1、有关于`nestjs`的技术问题或索要关于`nestjs`的电子书可以直接加我微信加入技术交流群(微信号:332904234)<font color="#f00">备注:nest 开发</font>

  <img src="https://shuiping.oss-cn-shenzhen.aliyuncs.com/nest-mysql-api/wx.jpg" width="200" height="220" style="margin-left:0" />

- 2、如果你觉得本项目对你帮助很大,**给一个赞**
- 3、最近正在搞`Nestjs`微服务训练营，训练营后打算重构一版
