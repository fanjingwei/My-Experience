# Maven的基本命令

mvn compile编译

mvn test测试

mvn clean清除

mvn package打包

mvn tomcat7:redeploy

mvn tomcat7:deploy

mvn tomcat7:undeploy

# Maven自动部署到tomcat
https://www.cnblogs.com/amosli/p/6086515.html

https://www.cnblogs.com/xyb930826/p/5725340.html

https://blog.csdn.net/sinat_25295611/article/details/79136450

# Maven的Q&A

**Q:** No compiler is provided in this environment. Perhaps you are running on a JRE rather than a JDK

**A:** 在windows下，不使用集成IDE时，Maven选择的编译器通过JAVA_HOME这个环境变量控制，出现以上错误时，往往是JAVA_HOME没有选择./java/jdk1.8.0_121/jre导致的。注意，这里必须使用./java/jdk1.8.0_121/jre而不能使用./java/jre

**Q:** tomcat访问http://127.0.0.1:8080/manager/html打不开
**A:** 一是要改..\webapps\manager\META-INF\context.xml中的allow，改为：allow="127\.\d+\.\d+\.\d+|::1|0:0:0:0:0:0:0:1|\d+\.\d+\.\d+\.\d+"/>；二是要在..\conf\tomcat-users.xml中增加<user username="admin" password="admin" roles="tomcat,manager,manager-script,admin-gui,manager-gui" />其中admin-gui,manager-gui不能丢

**Q:** 使用maven自动部署到tomcat为啥出现不了war包
**A:** 需要修改pom.xml中的packaging标签为：<packaging>war</packaging>
