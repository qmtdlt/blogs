1. new 一个空洞json，作为参数变量
```js
  var a = JSON.parse('{}');
```
2. iframe,一个页面包含多个ifream，即包含多个html文档，父页面调用iframe中的对象
```js
  var oiframe = document.getElementById('iframeId');    //获取iframe对象
  var iwindow = oiframe.contentWindow;        //获取iframe contentWindow
  var idoc = iwindow.document;        //获取contentWindow document对象
  var a = idoc.getElementById('refMsg');      
  a.click();      //通过iframe中一个a元素点击事件刷新消息内容
```
