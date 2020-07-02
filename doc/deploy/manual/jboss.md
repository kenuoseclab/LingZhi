> JBossAS 6

#### Linux-手动修改

##### 1.安装Agent.jar

从git的release处下载agent.jar文件，然后在JBoss的安装目录中创建文件夹iast，如`/opt/jboss/iast`，复制下载的agent.jar文件到创建的iast目录中

agent.jar在启动的过程中需要在iast目录中释放配置文件，所以需要在Linux下修改iast目录的权限，e.g: `chmod 777 -R /opt/jboss/iast`

##### 2.部署
进入JBoss容器的主目录，在`bin/run.sh`文件中找到`# Setup JBoss specific properties`所在行，在该行的下面插入如下行：

`JAVA_OPTS="$JAVA_OPTS "-javaagent:/opt/jboss/iast/agent.jar=token=<iast-token>`
其中，token为火线IAST页面中的Agent Token。

> JBossAS 7、JBossWildfly

#### Linux-手动修改
进入JBoss容器的主目录，根据当前服务器的启动类型：standalone、domain修改对应的配置文件

##### 1.安装Agent.jar

从git的release处下载agent.jar文件，然后在JBoss的安装目录中创建文件夹iast，如`/opt/jboss/iast`，复制下载的agent.jar文件到创建的iast目录中

agent.jar在启动的过程中需要在iast目录中释放配置文件，所以需要在Linux下修改iast目录的权限，e.g: `chmod 777 -R /opt/jboss/iast`

**Standalone模式**
打开`bin/standalone.sh`文件，定位`# Display our environment`所在的行，在其上方插入自定义配置，如下：

`JAVA_OPTS="$JAVA_OPTS "-javaagent:/opt/jboss/iast/agent.jar=token=<iast-token>`

其中，token为火线IAST页面中的Agent Token。

**domain模式**

当前版本为社区版本，不建议在domain模式下安装Agent。
