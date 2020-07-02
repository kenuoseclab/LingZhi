> Jar包启动方式

#### 手动安装

##### 1.安装Agent.jar

从git的release处下载agent.jar文件，然后在Spring Boot的安装目录中创建文件夹iast，如`/opt/web/iast/`，复制下载的agent.jar文件到创建的iast目录中

agent.jar在启动的过程中需要在iast目录中释放配置文件，所以需要在Linux下修改iast目录的权限，e.g: `chmod 777 -R /opt/web/iast/`

##### 2.部署Agent

配置启动参数`java -javaagent:/opt/web/iast/agent.jar -jar XXX.jar`
