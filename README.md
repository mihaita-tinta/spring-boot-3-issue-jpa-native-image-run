# Run application

This is a simple application generated via start.spring.io

To create the executable, run:

```shell
mvn clean install
```
Run as an executable jar works:
```shell
java -jar target/jpa-native-0.0.1-SNAPSHOT.jar
```
```text
2023-01-04T11:56:40.456+02:00  INFO 17741 --- [           main] o.s.b.w.embedded.tomcat.TomcatWebServer  : Tomcat started on port(s): 8080 (http) with context path ''
2023-01-04T11:56:40.496+02:00  INFO 17741 --- [           main] com.example.demo.JpaNativeApplication    : Started JpaNativeApplication in 7.797 seconds (process running for 8.852)
```

# Run as a docker image

Create the image works:

```shell
mvn spring-boot:build-image
[INFO]     [creator]     Setting default process type 'web'
[INFO]     [creator]     Saving docker.io/library/jpa-native:0.0.1-SNAPSHOT...
[INFO]     [creator]     *** Images (ccd6b7ecd18c):
[INFO]     [creator]           docker.io/library/jpa-native:0.0.1-SNAPSHOT
[INFO]     [creator]     Reusing cache layer 'paketo-buildpacks/syft:syft'
[INFO]     [creator]     Adding cache layer 'cache.sbom'
[INFO] 
[INFO] Successfully built image 'docker.io/library/jpa-native:0.0.1-SNAPSHOT'
[INFO] 
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  50.488 s
[INFO] Finished at: 2023-01-04T12:04:23+02:00
[INFO] ------------------------------------------------------------------------
```

Running the image works:

```shell
docker run docker.io/library/jpa-native:0.0.1-SNAPSHOT

Setting Active Processor Count to 4
Calculating JVM memory based on 7319436K available memory
For more information on this calculation, see https://paketo.io/docs/reference/java-reference/#memory-calculator
Calculated JVM Memory Configuration: -XX:MaxDirectMemorySize=10M -Xmx6909253K -XX:MaxMetaspaceSize=102982K -XX:ReservedCodeCacheSize=240M -Xss1M (Total Memory: 7319436K, Thread Count: 50, Loaded Class Count: 15768, Headroom: 0%)
Enabling Java Native Memory Tracking
Adding 124 container CA certificates to JVM truststore
Spring Cloud Bindings Enabled
Picked up JAVA_TOOL_OPTIONS: -Djava.security.properties=/layers/paketo-buildpacks_bellsoft-liberica/java-security-properties/java-security.properties -XX:+ExitOnOutOfMemoryError -XX:ActiveProcessorCount=4 -XX:MaxDirectMemorySize=10M -Xmx6909253K -XX:MaxMetaspaceSize=102982K -XX:ReservedCodeCacheSize=240M -Xss1M -XX:+UnlockDiagnosticVMOptions -XX:NativeMemoryTracking=summary -XX:+PrintNMTStatistics -Dorg.springframework.cloud.bindings.boot.enable=true

  .   ____          _            __ _ _
 /\\ / ___'_ __ _ _(_)_ __  __ _ \ \ \ \
( ( )\___ | '_ | '_| | '_ \/ _` | \ \ \ \
 \\/  ___)| |_)| | | | | || (_| |  ) ) ) )
  '  |____| .__|_| |_|_| |_\__, | / / / /
 =========|_|==============|___/=/_/_/_/
 :: Spring Boot ::                (v3.0.1)

2023-01-04T10:04:49.260Z  INFO 1 --- [           main] com.example.demo.JpaNativeApplication    : Starting JpaNativeApplication v0.0.1-SNAPSHOT using Java 17.0.5 with PID 1 (/workspace/BOOT-INF/classes started by cnb in /workspace)
2023-01-04T10:04:49.265Z  INFO 1 --- [           main] com.example.demo.JpaNativeApplication    : No active profile set, falling back to 1 default profile: "default"
2023-01-04T10:04:50.079Z  INFO 1 --- [           main] .s.d.r.c.RepositoryConfigurationDelegate : Bootstrapping Spring Data JPA repositories in DEFAULT mode.
2023-01-04T10:04:50.184Z  INFO 1 --- [           main] .s.d.r.c.RepositoryConfigurationDelegate : Finished Spring Data repository scanning in 91 ms. Found 1 JPA repository interfaces.
2023-01-04T10:04:50.830Z  INFO 1 --- [           main] o.s.b.w.embedded.tomcat.TomcatWebServer  : Tomcat initialized with port(s): 8080 (http)
2023-01-04T10:04:50.845Z  INFO 1 --- [           main] o.apache.catalina.core.StandardService   : Starting service [Tomcat]
2023-01-04T10:04:50.846Z  INFO 1 --- [           main] o.apache.catalina.core.StandardEngine    : Starting Servlet engine: [Apache Tomcat/10.1.4]
2023-01-04T10:04:50.961Z  INFO 1 --- [           main] o.a.c.c.C.[Tomcat].[localhost].[/]       : Initializing Spring embedded WebApplicationContext
2023-01-04T10:04:50.964Z  INFO 1 --- [           main] w.s.c.ServletWebServerApplicationContext : Root WebApplicationContext: initialization completed in 1616 ms
2023-01-04T10:04:51.008Z  INFO 1 --- [           main] com.zaxxer.hikari.HikariDataSource       : HikariPool-1 - Starting...
2023-01-04T10:04:51.221Z  INFO 1 --- [           main] com.zaxxer.hikari.pool.HikariPool        : HikariPool-1 - Added connection conn0: url=jdbc:h2:mem:mydb user=SA
2023-01-04T10:04:51.224Z  INFO 1 --- [           main] com.zaxxer.hikari.HikariDataSource       : HikariPool-1 - Start completed.
2023-01-04T10:04:51.238Z  INFO 1 --- [           main] o.s.b.a.h2.H2ConsoleAutoConfiguration    : H2 console available at '/h2-console'. Database available at 'jdbc:h2:mem:mydb'
2023-01-04T10:04:51.394Z  INFO 1 --- [           main] o.hibernate.jpa.internal.util.LogHelper  : HHH000204: Processing PersistenceUnitInfo [name: default]
2023-01-04T10:04:51.445Z  INFO 1 --- [           main] org.hibernate.Version                    : HHH000412: Hibernate ORM core version 6.1.6.Final
2023-01-04T10:04:51.625Z  WARN 1 --- [           main] org.hibernate.orm.deprecation            : HHH90000021: Encountered deprecated setting [javax.persistence.sharedCache.mode], use [jakarta.persistence.sharedCache.mode] instead
2023-01-04T10:04:51.804Z  INFO 1 --- [           main] SQL dialect                              : HHH000400: Using dialect: org.hibernate.dialect.H2Dialect
2023-01-04T10:04:52.478Z  INFO 1 --- [           main] o.h.e.t.j.p.i.JtaPlatformInitiator       : HHH000490: Using JtaPlatform implementation: [org.hibernate.engine.transaction.jta.platform.internal.NoJtaPlatform]
2023-01-04T10:04:52.487Z  INFO 1 --- [           main] j.LocalContainerEntityManagerFactoryBean : Initialized JPA EntityManagerFactory for persistence unit 'default'
2023-01-04T10:04:52.768Z  WARN 1 --- [           main] JpaBaseConfiguration$JpaWebConfiguration : spring.jpa.open-in-view is enabled by default. Therefore, database queries may be performed during view rendering. Explicitly configure spring.jpa.open-in-view to disable this warning
2023-01-04T10:04:53.168Z  INFO 1 --- [           main] o.s.b.w.embedded.tomcat.TomcatWebServer  : Tomcat started on port(s): 8080 (http) with context path ''
2023-01-04T10:04:53.198Z  INFO 1 --- [           main] com.example.demo.JpaNativeApplication    : Started JpaNativeApplication in 4.582 seconds (process running for 5.485)
```
# Create native image

Create the image works:
```shell
mvn -Pnative spring-boot:build-image
```

```text
[INFO]     [creator]     Setting default process type 'web'
[INFO]     [creator]     Saving docker.io/library/jpa-native:0.0.1-SNAPSHOT...
[INFO]     [creator]     *** Images (53d63af9e59b):
[INFO]     [creator]           docker.io/library/jpa-native:0.0.1-SNAPSHOT
[INFO]     [creator]     Reusing cache layer 'paketo-buildpacks/bellsoft-liberica:native-image-svm'
[INFO]     [creator]     Reusing cache layer 'paketo-buildpacks/syft:syft'
[INFO]     [creator]     Adding cache layer 'paketo-buildpacks/native-image:native-image'
[INFO]     [creator]     Reusing cache layer 'cache.sbom'
[INFO] 
[INFO] Successfully built image 'docker.io/library/jpa-native:0.0.1-SNAPSHOT'
[INFO] 
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  09:00 min
[INFO] Finished at: 2023-01-04T12:01:39+02:00
[INFO] --------------------------------------------
```

Running the image gives an error:
```shell
docker run docker.io/library/jpa-native:0.0.1-SNAPSHOT

  .   ____          _            __ _ _
 /\\ / ___'_ __ _ _(_)_ __  __ _ \ \ \ \
( ( )\___ | '_ | '_| | '_ \/ _` | \ \ \ \
 \\/  ___)| |_)| | | | | || (_| |  ) ) ) )
  '  |____| .__|_| |_|_| |_\__, | / / / /
 =========|_|==============|___/=/_/_/_/
 :: Spring Boot ::                (v3.0.1)

%PARSER_ERROR[d] %PARSER_ERROR[p] 1 --- [%PARSER_ERROR[t]] %PARSER_ERROR[logger] : %PARSER_ERROR[m]%PARSER_ERROR[n]%PARSER_ERROR[d] %PARSER_ERROR[p] 1 --- [%PARSER_ERROR[t]] %PARSER_ERROR[logger] : %PARSER_ERROR[m]%PARSER_ERROR[n]%PARSER_ERROR[d] %PARSER_ERROR[p] 1 --- [%PARSER_ERROR[t]] %PARSER_ERROR[logger] : %PARSER_ERROR[m]%PARSER_ERROR[n]%PARSER_ERROR[d] %PARSER_ERROR[p] 1 --- [%PARSER_ERROR[t]] %PARSER_ERROR[logger] : %PARSER_ERROR[m]%PARSER_ERROR[n]%PARSER_ERROR[d] %PARSER_ERROR[p] 1 --- [%PARSER_ERROR[t]] %PARSER_ERROR[logger] : %PARSER_ERROR[m]%PARSER_ERROR[n]%PARSER_ERROR[d] %PARSER_ERROR[p] 1 --- [%PARSER_ERROR[t]] %PARSER_ERROR[logger] : %PARSER_ERROR[m]%PARSER_ERROR[n]%PARSER_ERROR[d] %PARSER_ERROR[p] 1 --- [%PARSER_ERROR[t]] %PARSER_ERROR[logger] : %PARSER_ERROR[m]%PARSER_ERROR[n]%PARSER_ERROR[d] %PARSER_ERROR[p] 1 --- [%PARSER_ERROR[t]] %PARSER_ERROR[logger] : %PARSER_ERROR[m]%PARSER_ERROR[n]%PARSER_ERROR[d] %PARSER_ERROR[p] 1 --- [%PARSER_ERROR[t]] %PARSER_ERROR[logger] : %PARSER_ERROR[m]%PARSER_ERROR[n]%PARSER_ERROR[d] %PARSER_ERROR[p] 1 --- [%PARSER_ERROR[t]] %PARSER_ERROR[logger] : %PARSER_ERROR[m]%PARSER_ERROR[n]%PARSER_ERROR[d] %PARSER_ERROR[p] 1 --- [%PARSER_ERROR[t]] %PARSER_ERROR[logger] : %PARSER_ERROR[m]%PARSER_ERROR[n]%PARSER_ERROR[d] %PARSER_ERROR[p] 1 --- [%PARSER_ERROR[t]] %PARSER_ERROR[logger] : %PARSER_ERROR[m]%PARSER_ERROR[n]
org.springframework.beans.factory.BeanCreationException: Error creating bean with name 'entityManagerFactory': Instantiation of supplied bean failed
        at org.springframework.beans.factory.support.AbstractAutowireCapableBeanFactory.obtainInstanceFromSupplier(AbstractAutowireCapableBeanFactory.java:1236) ~[com.example.demo.JpaNativeApplication:6.0.3]
        at org.springframework.beans.factory.support.AbstractAutowireCapableBeanFactory.obtainFromSupplier(AbstractAutowireCapableBeanFactory.java:1210) ~[com.example.demo.JpaNativeApplication:6.0.3]
        at org.springframework.beans.factory.support.AbstractAutowireCapableBeanFactory.createBeanInstance(AbstractAutowireCapableBeanFactory.java:1157) ~[com.example.demo.JpaNativeApplication:6.0.3]
        at org.springframework.beans.factory.support.AbstractAutowireCapableBeanFactory.doCreateBean(AbstractAutowireCapableBeanFactory.java:561) ~[com.example.demo.JpaNativeApplication:6.0.3]
        at org.springframework.beans.factory.support.AbstractAutowireCapableBeanFactory.createBean(AbstractAutowireCapableBeanFactory.java:521) ~[com.example.demo.JpaNativeApplication:6.0.3]
        at org.springframework.beans.factory.support.AbstractBeanFactory.lambda$doGetBean$0(AbstractBeanFactory.java:326) ~[com.example.demo.JpaNativeApplication:6.0.3]
        at org.springframework.beans.factory.support.DefaultSingletonBeanRegistry.getSingleton(DefaultSingletonBeanRegistry.java:234) ~[com.example.demo.JpaNativeApplication:6.0.3]
        at org.springframework.beans.factory.support.AbstractBeanFactory.doGetBean(AbstractBeanFactory.java:324) ~[com.example.demo.JpaNativeApplication:6.0.3]
        at org.springframework.beans.factory.support.AbstractBeanFactory.getBean(AbstractBeanFactory.java:200) ~[com.example.demo.JpaNativeApplication:6.0.3]
        at org.springframework.context.support.AbstractApplicationContext.getBean(AbstractApplicationContext.java:1130) ~[com.example.demo.JpaNativeApplication:6.0.3]
        at org.springframework.context.support.AbstractApplicationContext.finishBeanFactoryInitialization(AbstractApplicationContext.java:905) ~[com.example.demo.JpaNativeApplication:6.0.3]
        at org.springframework.context.support.AbstractApplicationContext.refresh(AbstractApplicationContext.java:584) ~[com.example.demo.JpaNativeApplication:6.0.3]
        at org.springframework.boot.web.servlet.context.ServletWebServerApplicationContext.refresh(ServletWebServerApplicationContext.java:146) ~[com.example.demo.JpaNativeApplication:3.0.1]
        at org.springframework.boot.SpringApplication.refresh(SpringApplication.java:730) ~[com.example.demo.JpaNativeApplication:3.0.1]
        at org.springframework.boot.SpringApplication.refreshContext(SpringApplication.java:432) ~[com.example.demo.JpaNativeApplication:3.0.1]
        at org.springframework.boot.SpringApplication.run(SpringApplication.java:308) ~[com.example.demo.JpaNativeApplication:3.0.1]
        at org.springframework.boot.SpringApplication.run(SpringApplication.java:1302) ~[com.example.demo.JpaNativeApplication:3.0.1]
        at org.springframework.boot.SpringApplication.run(SpringApplication.java:1291) ~[com.example.demo.JpaNativeApplication:3.0.1]
        at com.example.demo.JpaNativeApplication.main(JpaNativeApplication.java:10) ~[com.example.demo.JpaNativeApplication:na]
Caused by: java.lang.IllegalStateException: No available JtaPlatform candidates amongst [org.hibernate.engine.transaction.jta.platform.internal.NoJtaPlatform, org.hibernate.service.jta.platform.internal.NoJtaPlatform]
        at org.springframework.boot.autoconfigure.orm.jpa.HibernateJpaConfiguration.getNoJtaPlatformManager(HibernateJpaConfiguration.java:213) ~[com.example.demo.JpaNativeApplication:3.0.1]
        at org.springframework.boot.autoconfigure.orm.jpa.HibernateJpaConfiguration.configureJtaPlatform(HibernateJpaConfiguration.java:150) ~[com.example.demo.JpaNativeApplication:3.0.1]
        at org.springframework.boot.autoconfigure.orm.jpa.HibernateJpaConfiguration.customizeVendorProperties(HibernateJpaConfiguration.java:139) ~[com.example.demo.JpaNativeApplication:3.0.1]
        at org.springframework.boot.autoconfigure.orm.jpa.JpaBaseConfiguration.entityManagerFactory(JpaBaseConfiguration.java:132) ~[com.example.demo.JpaNativeApplication:3.0.1]
        at org.springframework.boot.autoconfigure.orm.jpa.JpaBaseConfiguration__BeanDefinitions.lambda$getEntityManagerFactoryInstanceSupplier$3(JpaBaseConfiguration__BeanDefinitions.java:84) ~[na:na]
        at org.springframework.util.function.ThrowingBiFunction.apply(ThrowingBiFunction.java:68) ~[com.example.demo.JpaNativeApplication:6.0.3]
        at org.springframework.util.function.ThrowingBiFunction.apply(ThrowingBiFunction.java:54) ~[com.example.demo.JpaNativeApplication:6.0.3]
        at org.springframework.beans.factory.aot.BeanInstanceSupplier.lambda$get$2(BeanInstanceSupplier.java:208) ~[na:na]
        at org.springframework.util.function.ThrowingSupplier.get(ThrowingSupplier.java:59) ~[com.example.demo.JpaNativeApplication:6.0.3]
        at org.springframework.util.function.ThrowingSupplier.get(ThrowingSupplier.java:47) ~[com.example.demo.JpaNativeApplication:6.0.3]
        at org.springframework.beans.factory.aot.BeanInstanceSupplier.invokeBeanSupplier(BeanInstanceSupplier.java:220) ~[na:na]
        at org.springframework.beans.factory.aot.BeanInstanceSupplier.get(BeanInstanceSupplier.java:208) ~[na:na]
        at org.springframework.beans.factory.support.AbstractAutowireCapableBeanFactory.obtainInstanceFromSupplier(AbstractAutowireCapableBeanFactory.java:1225) ~[com.example.demo.JpaNativeApplication:6.0.3]
        ... 18 common frames omitted

```
