###### Maven构建配置文件
构建配置文件是一系列的配置项的值，可以用来设置或者覆盖Maven构建默认值。
使用构建配置文件，你可以为不同的环境，比如说生产画境（Production）和开发环境（Development）环境，定制构建方式。
配置文件在pom.xml文件中使用activeProfiles或者profiles元素指定，并且可以通过各种方式触发。配置文件在构建时修改POM，并且用来给参数设定不同的目标环境（比如说，开发（Development），测试（Testing）和生产环境（Producation）中数据库服务器的地址）。
###### 构建配置文件的类型
构建配置文件大体上有三种类型：
| 类型                 | 在哪定义                                                     |
| -------------------- | ------------------------------------------------------------ |
| 项目级（PerProject） | 定义在项目的POM文件pom.xml中                                 |
| 用户级PerUser        | 定义在Maven的设置xml文件中（%USER_HOME%.m2/setting.xml）     |
| 全局（Global）       | 定义在Maven全局的设置xml文件中（%M2_HOME%/config/setting.xml） |
###### 配置文件激活
Maven的构建配置文件可以通过多种方式激活。
- 使用命令控制台输入显示激活。
- 通过maven设置。
- 基于环境变量（用户或者系统变量）。
- 操作系统设置（比如说，Windows系列）。
- 文件的存在或者缺失。

###### 配置文件激活实例
[详情查看]（https://www.runoob.com/maven/maven-build-profiles.html)