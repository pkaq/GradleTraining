title: 多模块项目的构建-水平布局和分层布局
---
　　如果你阅读了前面的内容，那么你已经掌握了分层布局。没错，Gradle 默认即是采用的分层布局。只需要正确的配置 `settings` 文件即可。
　　某些情况下，若是出于一些不可描述的原因需要进行水平布局，那么 Gradle 也提供了良好的支持。如果你之前曾经翻阅过 `Settings` 接口的手册，那么或许你已经发现`Settintgs`接口提供了一个`includeFlat`方法，借助此方法即可实现水平布局的多模块项目。
  ```groovy
  includeFlat  'base'
  ```
  
由于此处`main`即是根项目，所以无需再包含`main`
  
完整示例 ->　[ > 水平布局的多模块项目示例 < ](https://github.com/GradleCN/GradleSide/tree/master/16-multi-project-flat)

心法在于两点:

 1.根项目与被依赖的项目(在水平意义上的子项目,视觉上根项目的兄弟项目)保持平级。 
 2.配置根项目的  setting.gradle  ， 采用  includeFlat  来描述子项目路径(由于采用的是水平布局,默认根路径就是当前根项目的上级路径,所以无需用../上跳)
