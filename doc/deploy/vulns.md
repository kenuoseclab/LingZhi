> 为了快速体验IAST的漏洞检测效果，我们将逐步提供不同类型的测试用例，用于更快的进行测试。

| 漏洞类型 | docker地址 |
|  ----  | ----  |
| 命令执行/路径穿越 | owef/iast-demo01:v1 |

靶场将逐步完善，欢迎表哥提供优秀的Java靶场地址，靶场通过审核后，表弟将为表哥奉上查克拉。

#### iast-demo01快速接入
1.安装并启动docker

2.拉取最新的容器：`docker pull owef/iast-demo01:v1`

3.启动容器：`docker run -itd -p 8080:8080 --name iast-demo01 owef/iast-demo01:v1`

4.访问靶场地址：http://localhost:8080/iast-test01/cmd.jsp?cmd=id