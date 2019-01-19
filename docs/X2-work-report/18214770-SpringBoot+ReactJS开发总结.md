# 18214770 SpringBoot+ReactJS开发总结

SpringBoot是SrpingMVC简化封装，Spring JPA(Hibernate) 进一步省略了很多写SQL的时间。SrpingBoot JPA+MySQL+注解结合Swagger库可以很快速实现一个API服务器，SrpingBoot下很多常见的库也是非常实用，可以盘点一下我们在项目中用到的更多实用的技术：

1. lombok @Data注解可以自动生成实体类的gettter setter tostring等方法，减少重复工作，也会让实体类看上去更美观
2. Srping JpaRepository 仅需声明方法就可以完成实体类与数据库字段间的映射（甚至自动生成数据库，无需手动建表）
3. Spring @CreatedBy @CreatedDate @LastModifiedBy @LastModifiedDate 这四个字段如字面意思，实体类若增加这四个注解，配合SpringSecurity可以实现记录功能：即谁创建、创建时间、最后修改者、最后修改实现，一切无需手动实现，接近一键配置非常方便。
4. MongoDB 因其分布式高可拓展行，非常适合做文件存储。
5. Spring @PathVariable 将RESTFUL风格URL中的参数映射到某种数据类型
6. Spring @RequestBody 映射JSON格式参数请求，自动映射到某种数据类型
7. Spring @RequestParam 映射表单参数请求，自动映射到某种数据类型
8. JWT(jsonwebtoken) 适合配合SrpingSecurity做权限验证的API服务


ReactJS 数据驱动UI的理念着实很新颖，只用更新数据，让UI跟随数据变化，这样开发的逻辑变得清晰，组件化的方法也减轻了重复工作，提升效率。不过也带来了代码上的混乱，很难在很快的时间内掌握ReactJS如何使用，特别是加上一堆包和组件后。我们SimpleCourse用到的包如下：

