# 出现 java.lang.OutOfMemoryError: PermGen space 错误的原因及解决方法

1 错误描述
------

在正常启动 Tomcat  的时候，报出如下错误：

![out](http://img.blog.csdn.net/20170407154921966)

2 错误原因
------

通过观察上面的错误描述，咱们可以知道错误原因： 

> java.lang.OutOfMemoryError: PermGen space

此错误，为**内存溢出错误**。

3 解决方法
------

进入`Run/Debug Configuration`页面，修改虚拟机参数为：

**`-Xms1024M -Xmx2048M -XX:PermSize=1028M -XX:MaxPermSize=2056M`** 

具体如何配置，如下图所示：

![vm](http://img.blog.csdn.net/20170407155427445)

----------

**温馨提示**：正常情况下，将虚拟机参数修改为上述大小后基本就能解决问题，否则也可以将参数继续增大。
