**复习一下自动配置原理？**

SpringBoot帮我们配置了什么？能不能修改？能修改哪些配置？能不能扩展？xxx

```java
xxxAutoConfiguration 帮我们给容器中自动配置组件
xxxPropertites 配置类类配置文件的内容
```

### 1、SpringBoot对静态资源的映射规则；

```java
可以设置和静态资源有关的参数，比如缓存时间
@ConfigurationProperties(
    prefix = "spring.resources",
    ignoreUnknownFields = false
)
public class ResourceProperties {
    private static final String[] CLASSPATH_RESOURCE_LOCATIONS = new String[]{"classpath:/META-INF/resources/", "classpath:/resources/", "classpath:/static/", "classpath:/public/"};
```



```java
public void addResourceHandlers(ResourceHandlerRegistry registry) {
            if (!this.resourceProperties.isAddMappings()) {
                logger.debug("Default resource handling disabled");
            } else {
                Duration cachePeriod = this.resourceProperties.getCache().getPeriod();
                CacheControl cacheControl = this.resourceProperties.getCache().getCachecontrol().toHttpCacheControl();
                if (!registry.hasMappingForPattern("/webjars/**")) {
                    this.customizeResourceHandlerRegistration(registry.addResourceHandler(new String[]{"/webjars/**"}).addResourceLocations(new String[]{"classpath:/META-INF/resources/webjars/"}).setCachePeriod(this.getSeconds(cachePeriod)).setCacheControl(cacheControl));
                }

                String staticPathPattern = this.mvcProperties.getStaticPathPattern();
                if (!registry.hasMappingForPattern(staticPathPattern)) {
                    this.customizeResourceHandlerRegistration(registry.addResourceHandler(new String[]{staticPathPattern}).addResourceLocations(WebMvcAutoConfiguration.getResourceLocations(this.resourceProperties.getStaticLocations())).setCachePeriod(this.getSeconds(cachePeriod)).setCacheControl(cacheControl));
                }

            }
        }

// 获取欢迎页
@Bean
        public WelcomePageHandlerMapping welcomePageHandlerMapping(ApplicationContext applicationContext, FormattingConversionService mvcConversionService, ResourceUrlProvider mvcResourceUrlProvider) {
            WelcomePageHandlerMapping welcomePageHandlerMapping = new WelcomePageHandlerMapping(new TemplateAvailabilityProviders(applicationContext), applicationContext, this.getWelcomePage(), this.mvcProperties.getStaticPathPattern());
            welcomePageHandlerMapping.setInterceptors(this.getInterceptors(mvcConversionService, mvcResourceUrlProvider));
            return welcomePageHandlerMapping;
        }
```

1)、所有 /webjars/**，都去classpath:/META-INF/resources/webjars/找资源；

webjars：以jar包的方式引入的静态资源；

https://www.webjars.org/

![](images\Snipaste_2020-01-05_17-37-05.png)

http://localhost:8080/webjars/jquery/3.4.1/jquery.js

```java
通过maven引入资源依赖的的时候只需写webjars下面的资源即可访问
    <dependency>
        <groupId>org.webjars</groupId>
        <artifactId>jquery</artifactId>
        <version>3.4.1</version>
    </dependency>
```

2）"/**" 访问当前项目的任何资源，都去下面路径查找

```java
private static final String[] CLASSPATH_RESOURCE_LOCATIONS = new String[]{
    "classpath:/META-INF/resources/", 
    "classpath:/resources/", 
    "classpath:/static/", 
    "classpath:/public/"};

还有当前项目根目录 "/"
```

3）欢迎页，静态资源目录下的index.html页面，被"/**映射"