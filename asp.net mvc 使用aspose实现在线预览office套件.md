### asp.net mvc 使用aspose实现在线预览office套件

1. 右键solution，add existting item,找到对应三个动态库，rename 文件加为dllimport
2. 右键references，点击底部按钮browse，找到本地三个动态库，全选确认，点击按钮OK
3. nuget添加Antlr3.Runtime,Optimization
4. 拷贝Content、css、Files、Images、Js、Scripts资源文件加
5. 复制controller函数
6. 复制view函数，注意_layout文件
7. 关于@Script报错问题：/view/web.config文件增加<add namespace="System.Web.Optimization"/>
8. 关于弹出页面不能显示html问题：端口号未与网站默认端口保持一致，修改端口号后正常，能够预览文件
9. 考虑怎样不使用BundleConfig.cs方式，导致前端不灵活
10. 运行程序查看index.cshtml文件，找到程序引用的css，js文件手动引用文件，去掉BundleConfig.cs后依然正常执行

https://github.com/qmtdlt/blogs/blob/master/copydemo.7z
