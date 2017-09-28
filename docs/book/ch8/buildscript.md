title: 多模块项目脚本结构-build文件
---

　　在根项目下，除了 `settings.gradle` 文件之外，通常还需要提供一个 `build.gradle` 文件，该文件用以定义子模块行为以及描述项目的一些公共插件、属性、依赖等。
  
　　下面的示例中，定义了所有模块共享的group、版本号，所有子模块共享的插件，以及针对`main`项目的定制化配置。
```groovy
// 所有模块都采用统一的版本号以及groupName
allprojects {
    group = 'org.pkaq.gradle.multi'
    version = "0.1.0"
}

// 为所有子模块都应用java插件
subprojects {
   apply plugin: 'java'
}

//为main模块定义特定行为,采用war插件并且依赖base模块
project(':main'){	

	apply plugin: 'war'

	dependencies {
    	compile  project(':base')
	}

}
```

　　如果您阅读了上一小节，`settings`文件是对`Settings`接口的脚本化编程实现，那么此处同理，借由 `Project` API，可对模块的行为进行定制。
  
| 方法名 | 描述 |
|--------|--------|
|   allprojects     |    配置当前模块以及所有子模块行为    |
|   subprojects     |    配置所有子模块行为    |
|   project     |    配置指定子模块行为    |

　　可以查阅　[> Project DSL <](https://docs.gradle.org/current/dsl/org.gradle.api.Project.html) 了解 Project 接口的更多操作。
  
　　此时可以通过执行  `  gradle build  ` 来进行构建，这会按照依赖的顺序构建所有子模块，如果要单独构建某个子模块那么可以参照 `gradle :main:build` 的方式进行单独构建，正如你所见用`:`分隔项目和`task`即可。