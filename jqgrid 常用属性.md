

### 常用属性
```Js
rownumbers: true, // 添加左侧行号
pager: '#contractBaseinfo_YX_pager',//底部内容：翻页等
width: window.innerWidth,//宽度
height: window.innerHeight - 223,//高度
sortname: 'ContractName',//默认排序字段
sortorder: "desc",//正逆序
multiselect: true,//复选框
rowList: [100, 200, 500, 1000],//每页行数选项
shrinkToFit: false,//自动内部滚动条
autoScroll: true,//内部滚动条
onSelectRow: function (Id) {}//单击行
ondblClickRow: function (row) {}//双击行
forceFit : true,//编辑单元格
cellsubmit: "clientArray",//编辑单元格
cellEdit: true,//编辑单元格
rowNum:-1,//不分页，显示全部
 
```
### reload
```js
 例1：$("#otherInfo").jqGrid('setGridParam', {}).trigger('reloadGrid');
 例2：$("#filmTable").jqGrid('setGridParam', {
            url: "/IntentionManage/ContractManage/GetContractDetailYx?ContractNumber=" + $("#ContractNumber").val(),
            mtype: 'POST',
        }).trigger('reloadGrid');
```

### 获取数据
```js
var id=$('#gridTable').jqGrid('getGridParam','selrow');//获取行id
var ids=$('#gridTable').jqGrid('getGridParam','selarrrow');//获取所有选中行id
var rowData = $("#gridTable").jqGrid('getRowData',rowId);//根据id获取行数据
```
### 处理查询条件累积问题
```js
//清空表格  数据
$('#filmListTable').jqGrid('clearGridData');  

 /*
 * 先清空条件
 * jqgrid postData setGridParam 调用多次时查询条件会累加
 */
 //获取查询条件
 var postData = $('#filmListTable').jqGrid("getGridParam", "postData");
 //循环，清空查询条件
 $.each(postData, function (k, v) {
      delete postData[k];
  });
//重新获取查询条件
getCondition();//g_SearrchCondition
      
//执行查询
$("#filmListTable").jqGrid('setGridParam', {
    url: "/IntentionManage/ContractManage/GetDetailAll?isCg=" + iscg,
    mtype: 'POST',
    postData: g_SearrchCondition,
}).trigger('reloadGrid');
//查询结束后全局变量查询条件置空（一个空json）
g_SearrchCondition = JSON.parse('{}');
