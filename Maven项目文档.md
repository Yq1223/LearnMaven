###### Maven项目文档
这里我们学习的是如何创建Maven项目文档。
比如我们在C:/MVN目录下，创建了consumerBanking项目，Maven使用下面的命令来快速创建java项目：
```
mvn archetype:generate -DgroupId=com.companyname.bank -DartifactId=consumerBanking -DarchetypeArtifactId=maven-archetype-quickstart -DinteractiveMode=false
```
修改pom.xml，添加以下配置（如果没有的话在配置，有则不需要配置）：
```
<project>
...
<build>
<pluginManagement>
    <plugins>
        <plugin>
            <groupId>org.apache.maven.plugins</groupId>
            <artifactId>maven-site-plugin</artifactId>
            <version>3.3</version>
        </plugin>
        <plugin>
            <groupId>org.apache.maven.plugins</groupId>
            <artifactId>maven-project-info-reports-plugin</artifactId>
            <version>2.7</version>
        </plugin>
    </plugins>
</build>
...
</project>
```
> *然运行 mvn site 命令时出现 java.lang.NoClassDefFoundError: org/apache/maven/doxia/siterenderer/DocumentContent 的问题， 这是由于 maven-site-plugin 版本过低，升级到 3.3+ 即可。*

打开consumerBanking 文件夹并执行以下mvn命令。
```
C:\MVN\consumerBanking> mvn site
```
Maven开始生成文档：
```
[INFO] Scanning for projects...
[INFO] -------------------------------------------------------------------
[INFO] Building consumerBanking
[INFO]task-segment: [site]
[INFO] -------------------------------------------------------------------
[INFO] [site:site {execution: default-site}]
[INFO] artifact org.apache.maven.skins:maven-default-skin: 
checking for updates from central
[INFO] Generating "About" report.
[INFO] Generating "Issue Tracking" report.
[INFO] Generating "Project Team" report.
[INFO] Generating "Dependencies" report.
[INFO] Generating "Continuous Integration" report.
[INFO] Generating "Source Repository" report.
[INFO] Generating "Project License" report.
[INFO] Generating "Mailing Lists" report.
[INFO] Generating "Plugin Management" report.
[INFO] Generating "Project Summary" report.
[INFO] -------------------------------------------------------------------
[INFO] BUILD SUCCESSFUL
[INFO] -------------------------------------------------------------------
[INFO] Total time: 16 seconds
[INFO] Finished at: Wed Jul 11 18:11:18 IST 2012
[INFO] Final Memory: 23M/148M
[INFO] -------------------------------------------------------------------
```
目录的结构图请看：https://www.runoob.com/wp-content/uploads/2018/09/12-site-project-structure.jpg
打开**C:\MVN\consumerBanking\target\site**文件夹。点击index.html就可以看到文档了。
如图所示：https://www.runoob.com/wp-content/uploads/2018/09/12-consumer-web-page.jpg
Maven使用一个名为++Doxia++的文档处理引擎来创建文档，它能够多种格式的源码读取成一种通用的文档模型。要为你的项目撰写文档，你可以将内容写成下面几种常用的，可被Doxia转化的格式。
| 格式  | 名述                    | 参数                                                     |
| ----- | ----------------------- | -------------------------------------------------------- |
| Apt   | 纯文本文档格式          | http://maven.apache.org/doxia/references/apt-format.html |
| Xdoc  | Maven 1.x的一种文档格式 | http://jakarta.apache.org/site/jakarta-site2.html        |
| FML   | FAQ文档适用             | http://maven.apache.org/doxia/references/fml-format.html |
| XHTML | 可扩展的HTML文档        | http://en.wikipedia.org/wiki/XHTML                       |