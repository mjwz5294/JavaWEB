﻿
SSM项目基本整合,对于IDEA可以直接拉取下来使用.很方便

基本使用工具,下次再介绍

Spring，mybatis，ehcache，aspectjrt，druid，fastjson，slf4j，logback，
httpclient，commonlang，commonbean，commonio，commonfile，


一、druid：
1、数据库连接池，参考：https://www.cnblogs.com/xdp-gacl/p/4002804.html
（1）数据库连接池负责分配,管理和释放数据库连接,它允许应用程序重复使用一个现有的数据库连接,而不是重新建立一个。数据库连接池在初始化时将创建一定数量的数据库连接放到连接池中, 这些数据库连接的数量是由最小数据库连接数来设定的.无论这些数据库连接是否被使用,连接池都将一直保证至少拥有这么多的连接数量.连接池的最大数据库连接数量限定了这个连接池能占有的最大连接数,当应用程序向连接池请求的连接数超过最大连接数量时,这些请求将被加入到等待队列中
（2）最小连接数:是连接池一直保持的数据库连接,所以如果应用程序对数据库连接的使用量不大,将会有大量的数据库连接资源被浪费.
（3）最大连接数:是连接池能申请的最大连接数,如果数据库连接请求超过次数,后面的数据库连接请求将被加入到等待队列中,这会影响以后的数据库操作
（4）如果最小连接数与最大连接数相差很大:那么最先连接请求将会获利,之后超过最小连接数量的连接请求等价于建立一个新的数据库连接.不过,这些大于最小连接数的数据库连接在使用完不会马上被释放,他将被放到连接池中等待重复使用或是空间超时后被释放.
2、自己编写数据库连接池，关键在于：使用动态代理技术构建连接池中的连接。当用户使用完Connection，调用Connection.close()方法时，Collection对象应保证将自己返回到LinkedList中,而不要把conn还给数据库。
3、开源数据库连接池：现在很多WEB服务器(Weblogic, WebSphere, Tomcat)都提供了DataSoruce的实现，即连接池的实现。通常我们把DataSource的实现，按其英文含义称之为数据源，数据源中都包含了数据库连接池的实现。
4、配置Tomcat数据源：在实际开发中，我们有时候还会使用服务器提供给我们的数据库连接池，比如我们希望Tomcat服务器在启动的时候可以帮我们创建一个数据库连接池，那么我们在应用程序中就不需要手动去创建数据库连接池，直接使用Tomcat服务器创建好的数据库连接池即可。--------JNDI技术
5、小结：动态代理技术，静态代码块，JNDI技术，
（1）静态代码块：https://www.cnblogs.com/jswang/p/7699643.html，https://www.cnblogs.com/Qian123/p/5713440.html
（2）动态代理技术：https://www.cnblogs.com/fengmingyue/p/6092151.html
6、druid重点学习如何使用，参考：https://www.imooc.com/article/25523
（1）除了有数据库连接池功能，还提供了一些扩展功能，尤其是监控功能
（2）配置方面，web.xml的配置中比较陌生的，也就是这个地方了

二、web.xml中的配置
1、SpringMVC配置，主要就是提供SpringMVC配置文件的位置，然后在该文件中做具体配置
2、druid配置
3、fastjson的配置

三、mybatis整合：https://blog.csdn.net/winter_chen001/article/details/77249029
    idea搭建ssm框架：https://www.cnblogs.com/hackyo/p/6646051.html
    
四、aspectj：https://zhidao.baidu.com/question/394893890.html，因为spring直接使用AspectJ的注解功能，就是说spring自带的AOP使用了aspectjweaver.jar里的某些类。所以要加上这个jar包

五、缓存：https://www.cnblogs.com/qlqwjy/p/7788912.html

六、日志系统：https://blog.csdn.net/chen3749102/article/details/52795786

