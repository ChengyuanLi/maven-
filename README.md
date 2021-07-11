# maven-软件管理工具
### 改进项目的开发和管理
1. pom：pom.xml文件*，项目对象模型。maven将项目作为模型。可以控制maven构建项目的过程 + jar依赖。
2. 目录结构：规范的结构
3. 坐标：表资源的唯一字符串
4. 依赖管理：管理项目中使用的jar
5. 仓库管理：资源存放的位置
6. 生命周期：构建项目的构成 从清理到部署
7. 插件和目标：maven构建的工具是插件。

### mvn compile 
- -> 编译 src/main 下面的所有.java文件
- -> 寻找build success
- -> 出现target目录

### 修改本地资源存放目录
- maven/conf/settings.xml 在`<localRepository>`中指定目录

### 仓库
1. 仓库中包含maven使用的jar和项目使用的jar
2. 仓库的分类：
  - 本地仓库：
  - 远程仓库：
    1. 中央仓库：所有开发人员共享：https://repo.maven.apache.org
    2. 中央仓库的镜像：减轻中央仓库访问压力。
    3. 私服：公司内部资源
3. 仓库的使用：不需要人为参与
   例：需要使用mysql驱动：maven检查：本地 -> 私服 -> 镜像 -> 中央仓库
 
 ### pom.xml
- 基本信息（坐标）
  - modelVersion：Maven模型版本
  - groupId：唯一值：公司域名倒写 `com.baidu.appolo`
  - artifactId: 项目名称
  - version: 版本号
  - packaging；打包类型
    
    ```xml
    <groupId>com.1609</groupId>
    <artifactId>maven</artifactId>
    <version>1.0.0</version>
    ```
 
 - 依赖
  - dependencies / dependency：相当于import，管理依赖
    
    ```xml
    <dependencies>
      <dependency>
        <groupId>xxxxx</groupId>
        <artifactId>xxxxx</artifactId>
        <version>xxxxx</version>
      </denpendency>
    </dependencies>
    ```
  - properties属性
    - 定义编码方式，当前项目版本号
    
  - build
    - 构建相关配置 ，jdk编译版本
  
  - parent 继承
    -与java类似，子项目需要的父项目
 
### maven主要命令
- mvn clean
- mvn compile
- mvn test-compile
- mvn test
- mvn package
- mvn install
- mvn deploy
