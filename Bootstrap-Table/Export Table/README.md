# Export
需使用tableExport.min.js

## Options

### showExport
將showExport設成true,就可以export table
```javascript
showExport : true,  
```
### exportOptions
可選用的選項
```javascript
    exportOptions: {
        fileName: 'Project Status'
    }, 
```
### exportTypes
Default:['json', 'xml', 'csv', 'txt', 'sql', 'excel']
```javascript
    exportTypes: ['json', 'xml', 'csv', 'txt', 'sql', 'excel']
```

### exportDataType
Default:basic,有'basic','all','selected' 可以選


### exportFooter
Default:false
```javascript
    exportFooter: false
```
## code
<a href = "https://live.bootstrap-table.com/code/Eddie02582/6720">link</a>
```html
<script src="https://unpkg.com/tableexport.jquery.plugin/tableExport.min.js"></script>
<table id="table"></table>          
<script>
  var $table = $('#table') 
  function initTable() {
     $table.bootstrapTable({
       url: "json/data1.json",
       showColumns : true,
       showColumnsToggleAll:true, //在欄位選擇開啟開關全部欄位
       showToggle : true, //名片式/table式切換
       showPaginationSwitch : true, //分頁/不分頁切換
       showRefresh : true, //重新整理
       showFullscreen: true,
       search : true, //查詢 
       pagination : true,         	 
       showExport : true,  
       exportOptions: {
            fileName: 'Project Status'
        },
       columns: 
       			[ 
              { 
                field :"id",
                title:'ID',
                visible:true, 
              },
              { 
                field :"name",
                title:'Item Name',   
              },
              { 
                field :"price",
                title:'Item Price' 
              }, 
        ],
     })    
  }   
 
  
  $(function() {
    initTable()  
  })

</script>

```









