## 1. ajax向控制器传数组
### 前端代码
```js
$.ajax({
  url:"",
  datetype:'json',
  type:'POST',
  traditional:true,
  data:{
    'ids':idsList//idsList为数组类型
  },
  success:function()
  {}
})
```

### 控制器代码
```C#
[HttpPost]
public ActionResult funcName(List<T> ids)
{
  return View();
}
```

## 2 服务器端文件复制粘贴操作
> 说明：文件操作时需要使用绝对路径，相对路径时创建路径 System.IO.Directory.CreateDirectory、路径判断System.IO.Directory.Exists等函数粗线错误；提示权限问题

### 取绝对路径
```C#
  using System.Web.Mvc;
  string Path = Server.MapPath("");
  string physicalPath = Path.Substring(0, Path.LastIndexOf("Zfbz"));
```

### 文件复制操作
```C#
public static bool copyFile(string sourcePath, string targetPath, string fileName, string physicalPath)
{
    string sourceFile = System.IO.Path.Combine(sourcePath, fileName);
    targetPath = physicalPath + targetPath;
    sourceFile = physicalPath + sourceFile;
    string destFile = System.IO.Path.Combine(targetPath, fileName);

    if (!System.IO.Directory.Exists(targetPath))
    {
        System.IO.Directory.CreateDirectory(targetPath);
    }

    System.IO.File.Copy(sourceFile, destFile, true);
    return true;
}
```
