# 项目框架模板

将自己常用的框架、工具类提取出来的一个小demo，可以当做项目模板，在项目启动时，快速构建
各个模块负责各自自己的依赖以及一些公共约定和工具类
          
##### common 
包含一些公共约定，如Exception、返回值
#####  common-logger 
包含日志工具类
#####  common-mybatis 
定义了mybatis的公共接口BaseMapper 以及基于BaseMapper的BaseService
#####  common-spring 
包含一些spring工具类
#####  common-redisson 
java redis工具redisson依赖
#####  common-springmvc 
定义了公共Controller，进行了全局的异常拦截;   
RateLimitInterceptor限流拦截器   
RequestInfoInterceptor request信息拦截器，输出到日志，方便开发   
#####  common-metrics 
集成了dropwizard metrics,可以使用注解对应用进行监控，
如果需要使用servlet查看监控数据的话,需要在web.xml中配置metrics servlet和listener。
例子可见web-springmvc-mybatis web.xml

#####  common-feign
 feign是一个调用远程http接口的java服务端工具，就像调用本地方法一样方便
 这里封装了feign的日志记录，gson序列化，form提交和一个简单的复杂均衡器
 按照这种模式，可以很轻易的构建自己的负载均衡算法

###项目模板
##### web-springmvc-mybatis 
一个springmvc+mybatis的模板 
添加了基于redis 的spring cache,spring session

##### http-remote-feign
使用feign调用远程项目的http接口，就像调用本地service一样,用于测试和分布式项目的远程访问都挺好用的
