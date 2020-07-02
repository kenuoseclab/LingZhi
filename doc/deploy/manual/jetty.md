#### 手工修改

##### 1.安装Agent.jar

从git的release处下载agent.jar文件，然后在Jetty的安装目录中创建文件夹iast，如`/opt/jetty/iast`，复制下载的agent.jar文件到创建的iast目录中

agent.jar在启动的过程中需要在iast目录中释放配置文件，所以需要在Linux下修改iast目录的权限，e.g: `chmod 777 -R /opt/jetty/iast`

##### 2.部署
1.进入jetty的主目录

2.打开`bin/jetty.sh`文件，找到`Add jetty properties to Java VM options.`所在行

3.在改行的下面插入`JAVA_OPTIONS+=( "-javaagent:/opt/jetty/iast/agent.jar=token=<iast-token>")`

4.重启jetty服务器

#### 自动修改
进入tomcat容器的主目录，找到`bin/jetty.sh`文件，使用下面的shell命令修改jetty.sh文件

`sed "$(cat jetty.sh |grep -n \"Add jetty properties to Java VM options\"|cut -d ":" -f1) aJAVA_OPTS=\"\$JAVA_OPTS\ \"-javaagent:/opt/jetty/iast/agent.jar=token=<iast-token>" -i jetty.sh`
