###### Maven引入外部依赖
如果我们需要引入第三方库文件到项目中，该如何操作呢？
pom.xml的dependencies列表列出了我们的项目需要构建的所有外部依赖项。
要添加依赖项，我们一般是先在src文件夹下添加lib文件夹，然后将你的工程需要的jar文件复制到lib文件夹下。我们使用的是ldapjdk.jar，他是为LDAP操作的一个帮助库：<br/>
**如图**：https://www.runoob.com/wp-content/uploads/2018/09/11-external-project-structure.jpg

然后添加一下依赖到pom.xml文件中：
```
<dependencies>
    <dependency>
    <!--在这里添加你的依赖-->
        <groupId>ldapjdk</group>
        <!--库名称也可以自己自定义-->
        <artifactId>ldapjdk</artifactId>
        <!--库名称也可以自定义-->
        <version>1.0</version>
        <!--版本号-->
        <scope>system</scope>
        <!--作用域-->
        <systemPath>${basedir}\src\lib\ldapjdk.jar</systemPath>
        <!--项目根目录下的lib文件夹下-->
    </dependency>
</dependencies>
```
pom.xml文件的完整代码如下：
```
<project xmlns="http://maven.apache.org/POM/4.0.0" 
   xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
   xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 
   http://maven.apache.org/maven-v4_0_0.xsd">
   <modelVersion>4.0.0</modelVersion>
   <groupId>com.companyname.bank</groupId>
   <artifactId>consumerBanking</artifactId>
   <packaging>jar</packaging>
   <version>1.0-SNAPSHOT</version>
   <name>consumerBanking</name>
   <url>http://maven.apache.org</url>
   
   <dependencies>
      <dependency>
         <groupId>junit</groupId>
         <artifactId>junit</artifactId>
         <version>3.8.1</version>
         <scope>test</scope>
      </dependency>
 
      <dependency>
         <groupId>ldapjdk</groupId>
         <artifactId>ldapjdk</artifactId>
         <scope>system</scope>
         <version>1.0</version>
         <systemPath>${basedir}\src\lib\ldapjdk.jar</systemPath>
      </dependency>
   </dependencies>
 
</project>
```