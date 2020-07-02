### 手动安装-Linux

##### 1.安装Agent.jar
从git的release处下载agent.jar文件，然后在Tomcat的安装目录中创建文件夹iast，如`/opt/tomcat/iast`，复制下载的agent.jar文件到创建的iast目录中

agent.jar在启动的过程中需要在iast目录中释放配置文件，所以需要在Linux下修改iast目录的权限，e.g: `chmod 777 -R /opt/tomcat/iast`

##### 2.部署Agent

1.进入`tomcat`所在目录

2.在`bin/catalina.sh`文件中定位到`elif [ "$1" = "run" ]; then`所在行

3.在该行的下面插入一行，内容如下：`JAVA_OPTS="$JAVA_OPTS "-javaagent:/opt/tomcat/iast/agent.jar=token=<iast-token>`

> iast-token从火线平台的灵芝IAST中获取
