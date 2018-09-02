> 本文以 *macOS* 为基  <small>( 此文隐藏了大量细节, 若有需求可提 issue 或以其他方式联系我 )</small> 

### Installer <small>(ver: 8u181)</small>

| Type | Link | 
| :--- | :---: | 
| Environment | [*Java*](https://www.java.com/zh_CN/download/mac_download.jsp) <br>[*JRE*](https://www.oracle.com/technetwork/java/javase/downloads/jre8-downloads-2133155.html) <br>[*JDK*](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html) |
| Editor | [*Android Studio*](https://developer.android.com/studio/#downloads) <br>[*Visual Studio Code*](https://code.visualstudio.com/#alt-downloads) | 

### Env path
- 在无自定义安装路径的情况下 在 ```~/.zshrc``` 里键入 
    > ```JAVA_HOME=/Library/Java/JavaVirtualMachines/jdk1.8.0_181.jdk/Contents/Home```<br>```CLASSPATH=.:$JAVA_HOME/lib/dt.jar:$JAVA_HOME/lib/tools.jar```<br>```PATH=$JAVA_HOME/bin:$PATH:```
    
    > ```export JAVA_HOME```<br>```export CLASSPATH```<br>```export PATH```
- 再提几句
    1. 若你使用的是默认的 *Bash*，你需要将上述文字写入 ```~/.bashrc``` 
    2. 写入后 键入 ```source ~/.bashrc``` 

### about *VSCode*
- 安装插件 
    - *Language Support for Java(TM) by Red Hat*
    - *Code Runner*
- 将以下写入 **User Settings**
    > ```"java.home": "/Library/Java/JavaVirtualMachines/jdk1.8.0_181.jdk/Contents/Home"```<br>```“java.errors.incompleteClasspath.severity": "ignore",```

### about *Android Studio* 
- 期间下载 Android *SDK* 时注意配置 Proxy  <small>( 你需要 *SSR* 或其他方式越墙 )</small>

### 此文没有讲哪些内容 ?
> 在我补充之前 你需要自己查阅资料噢 🙂

- 环境变量配置 之 *Windows* & *Linux* 端
- 越墙  <small>( 下载 Android *SDK* 时需要噢 )</small>
- VSCode 的基础使用
- Android Studio 的基础使用 

<hr> 

### 参考链接
- [快速使用 VSCode 进行 Java 编程](https://juejin.im/post/5ac193cd6fb9a028d208161c)