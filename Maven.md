#Maven的基本命令
mvn compile编译

mvn test测试

mvn clean清除

mvn package打包

#Maven的Q&A
##Q:No compiler is provided in this environment. Perhaps you are running on a JRE rather than a JDK
在windows下，不使用集成IDE时，Maven选择的编译器通过JAVA_HOME这个环境变量控制，出现以上错误时，往往是JAVA_HOME没有选择./java/jdk1.8.0_121/jre导致的。注意，这里必须使用./java/jdk1.8.0_121/jre而不能使用./java/jre
