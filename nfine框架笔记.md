###　关闭iframe页签时自动刷新首页
  1. /home/index.cshtml页面创建函数switchToHomePage()
  ```js
    function switchToHomePage() {
          var oiframes = document.getElementsByClassName('NFine_iframe');
          //刷新/Home/Default消息内容
          for (var i = 0; i < oiframes.length; i++) {//循环所有iframe
              if (oiframes[i].src.indexOf("/Home/Default") > 0) //找到/home/default && oiframes[i].style.display =='iniline'
              {
                  var iwindow = oiframes[i].contentWindow;        //获取iframe contentWindow
                  var idoc = iwindow.document;        //获取contentWindow document对象
                  var a = idoc.getElementById('refMsg');
                  a.click();      //通过iframe中一个a元素点击事件刷新消息内容
              }
          }
      }
  ```
  2. indextab.js页面143行，创建tab页签a标签时增加点击函数，调用index.cshtml页面函数switchToHomePage()
  ```js
    var str = '<a href="javascript:;" onclick="switchToHomePage()" class="active menuTab" data-id="' + dataUrl + '">' + menuName + ' <i class="fa fa-remove"></i></a>';
  ```
  3. 首页iframe页面内，创建a，被index获取，并调用其onclick函数
  
