Gradle在执行时提供了6个常用日志级别，并且提供了友好的参数可以让你随心所欲的控制控制台输出。

**日志级别**

| 日志级别 | 级别描述 |
|--------|--------|
|     ERROR   |    错误消息    |
| QUIET | 重要的信息消息 |
|WARNING | 警告消息| 
|LIFECYCLE | 进度信息消息 |
| INFO | 信息性消息 | 
| DEBUG | 调试消息|

**日志参数**

| 命令参数 | 级别描述 |
|--------|--------|
|没有日志选项 |LIFECYCLE 及更高 |
|-q or --quiet |QUIET 及更高 |
|-i or --info |INFO 及更高 |
|-d or --debug |DEBUG 及更高| 
|-s or --stacktrace | 打印关键堆栈信息 |
|-S or--full-stacktrace |打印全栈信息 |
