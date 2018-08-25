## ajax向控制器传数组
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
