> Resin 4

#### 手动修改

##### 1.安装Agent.jar

从git的release处下载agent.jar文件，然后在Resin的安装目录中创建文件夹iast，如`/opt/Resin/iast`，复制下载的agent.jar文件到创建的iast目录中

agent.jar在启动的过程中需要在iast目录中释放配置文件，所以需要在Linux下修改iast目录的权限，e.g: `chmod 777 -R /opt/Resin/iast`

##### 2.部署agent
1.进入Resin的主目录，

2.打开`conf/cluster-default.xml`文件，定位到`<server-default>`所在的行，

3.在该行下面插入`<jvm-arg>-javaagent:/opt/Resin/iast/agent.jar=token=<iast-token></jvm-arg>`

4.重启Resin
