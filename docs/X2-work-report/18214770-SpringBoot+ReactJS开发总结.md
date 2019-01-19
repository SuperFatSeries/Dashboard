# 18214770 SpringBoot+ReactJS开发总结
我参与到了项目后台与课程前端的开发工作中，分别用到两个比较熟知的框架————SpringBoot和ReactJS

SpringBoot是目前最主流的后台开发框架，是SrpingMVC的简化封装，Spring JPA(Hibernate) 进一步省略了很多写SQL的时间。SrpingBoot JPA+MySQL+注解结合Swagger库可以很快速实现一个API服务器，SrpingBoot下很多常见的库也是非常实用，可以盘点一下我们在项目中用到的更多实用的技术：

1. lombok @Data注解可以自动生成实体类的gettter setter tostring等方法，减少重复工作，也会让实体类看上去更美观
2. Srping JpaRepository 仅需声明方法就可以完成实体类与数据库字段间的映射（甚至自动生成数据库，无需手动建表）
3. Spring @CreatedBy @CreatedDate @LastModifiedBy @LastModifiedDate 这四个字段如字面意思，实体类若增加这四个注解，配合SpringSecurity可以实现记录功能：即谁创建、创建时间、最后修改者、最后修改实现，一切无需手动实现，接近一键配置非常方便。
4. MongoDB 因其分布式高可拓展行，非常适合做文件存储。
5. Spring @PathVariable 将RESTFUL风格URL中的参数映射到某种数据类型
6. Spring @RequestBody 映射JSON格式参数请求，自动映射到某种数据类型
7. Spring @RequestParam 映射表单参数请求，自动映射到某种数据类型
8. JWT(jsonwebtoken) 适合配合SrpingSecurity做权限验证的API服务


ReactJS 是前端三大框架之一，数据驱动UI的理念着实很新颖，只用更新数据，让UI跟随数据变化，这样开发的逻辑变得清晰，组件化的方法也减轻了重复工作，提升效率。不过也带来了代码上的混乱，很难在很快的时间内掌握ReactJS如何使用，特别是加上一堆包和组件后。我们SimpleCourse课程前端基于Ant Design Pro 开发）另一部分课程管理由另一位同学用Vue+Element-Admin搭建）。Ant Design Pro是蚂蚁金服企业级开箱即用的中台前端/设计解决方案，深入了解其架构后，我们用到常用包如下：

1. dva 由阿里架构师 sorrycc 带领 team 完成的一套前端框架，在作者的 github 里是这么描述它的：”dva 是 react 和 redux 的最佳实践
2. umi 一套可插拔的企业级 react 应用框架，同样由dva作者 sorrycc 完成。他在Umi中引入了 UI 工具 antd，打包工具 roadhog，路由 react-router和状态管理器 dva，做到了可插拔机制。

antd 给出的结构包括 Model、Service 和 View三层:

### View层
负责数据展示

### Model层 
`model`包括:
- `namespace` 命名空间
- `state` 存放`Service`获取到的数据(通过`connect`与View层链接起来)
- `reducers` 存放改变`View`的动作，通常只是返回state到`View层`
- `effects` 与后台交互(先从`Service`导入方法)，处理异步请求
- `subscriptions`订阅监听

### Service层 
负责与服务端通信


总的来说，SpringBoot + MongoDB + MySQL (JWT + Spring Security) & React + dva/VueJS 可以构建一套带有权限管理的完善的应用系统。这些技术的引入大大增加了开发难度，我们小队最终还是坚持了下来，我对这次项目的工作比较满意，这其中我的感觉是收益颇多，还有一大堆一知半解的技术等待去深入理解、学习。希望今后能完善这个系统，真正用到实际中去，简化学生&助教的工作。

