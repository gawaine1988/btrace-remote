#btrace 远程追踪工具
本工具根据btrace的1.3.11版本修改，加入了远程追踪代码的功能。

## 使用方法
在使用本工具的时候需要进行以下几个步骤：

1. 在远程服务器通过instrument代理的premain方式启动btrace-agent.jar代理。参数命令如下：`java -javaagent:agent_jar_path[=options] java_app_name`。其中agent_jar_path是btrace-agent.jar的文件位置。
2. 启动本地的btrace追踪程序。示例如下：`btrace [-ip <ip>] [-cp <classpath>] <pid> <btrace-script> [<args>]`。参数信息：
  * -ip 远程服务器ip地址。
  * -cp btrace编译期间需要的类和jar包的路径
  * <pid> 被绑定的java进程号。本工具中可以随便填写一个数字，不影响程序运行。
  * <btrace-script> 待运行的btrace脚本，该脚本可以是java或者class文件。

