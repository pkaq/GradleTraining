## 下载和安装

### <div name="zero">.0.先决条件</div>
    
    * 翻墙
    * 翻墙
    * 翻墙
    
　　1.5以上版本的JDK,Gradle会采用你环境变量中设置的JDK目录(可以用java -version进行检查),你需要配置环境变量 JAVA_HOME 并将它指向你的JDK安装目录.

　　p.s:Gradle自带了Groovy库,所以无需事先安装Grvoovy,所有已经安装的Grvooy也将被Gradle忽略.
#### <div name="one">.1.下载</div>
　　从[Gralde官方网站](http://www.gradle.org/download)下载Gradle的最新发行包,下载后解压到任意目录即可（最好不要放在中文以及带有空格的目录中）
  
### <a name="two">.2.安装包结构</a>
   * Gradle 可执行文件
   * 用户手册 (有 PDF 和 HTML 两种版本)
   * DSL 参考指南
   * API 手册(Javadoc 和 Groovydoc)
   * 样例，包括用户手册中的例子，一些完整的构建样例和更加复杂的构建脚本
   * 源代码。仅供参考使用,如果你想要自己来编译 Gradle 你需要从源代码仓库中检出发行版本源码，具体请查看 Gradle 官方主页。
   
### <a name="three">.3.配置环境变量</a>
　　运行gradle必须将GRADLE_HOME/bin加入到你的PATH环境变量中.  
  
#### <div name="four">.4.测试安装</a>

  运行如下命令来检查是否安装成功.该命令会显示当前的JVM版本和Gradle版本.
```groovy
   gradle -v
```

### <div name="five">.5.Gradle升级</div>
  如果你采用的非windows系统，那么可以通过`ln -s gradle-version gradle`来创建一个软连接，之后直接解压新版本的Gradle替换目录即可，windows下建议初次安装时，将gradle-version文件夹重命名为gradle，后续升级直接清空此目录解压新版本文件到此目录即可，而无需更改环境变量。