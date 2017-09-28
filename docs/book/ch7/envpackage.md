### 通过一种奇葩的快捷方式给web工程打不同环境包

　　通常而言，开发环境和生产环境参数有着较大的差异，在上古时代，猿们通过打包时或者开发时手工修改配置文件的方式来区分生产环境和开发环境。显然这种方式是比较低效且lowbee的。那么，我们可以将不同环境的配置文件各建一份，通过Gradle来进行不同环境的打包。比如如下几种方式

- 根据不同环境的参数建立不同的环境文件，打包时只打包相应的环境文件
- 把环境参数配置到x.properties文件中，打包时从文件中读取相应参数动态修改配置文件

　　下面的姿势是选取的第一种，在`src/main/resources`按不同环境建立相应的folder,打包时将不需要环境文件排除掉。当然我这里只是一个示例，实际情况可以自行修改代码实现，比如如果不想保留环境目录直接把环境文件打包到`src/main/resources`，则直接把环境目录追加到srcDir下即可

　　执行下面的命令打相关环境的包
```bash
gradle -q -Penv=pro
```

　　可以修改`gradle.properties`中的`env`默认值

`gradle.properties`
```groovy
env=dev
```

`build.gradle`
```groovy
apply plugin: 'java'

sourceSets {  	
    main {
        resources {
            sourceSets.main.resources.srcDirs.each   { 		
				it.listFiles().each {
	       		 	 if(it.isDirectory() && it.name != "${env}") {
	           		 	println "exclude ${it.name}"	   
	           		 	exclude "${it.name}"
	       		 	}
	       		}           		
            }
        }
    }
}
```