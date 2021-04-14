# Bootstrap-Table

## 如何使用
使用時需要bootstrap,bootstrap-table,jquery,fontawesome-all.css


```html
<link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css">
<link rel="stylesheet" href="https://use.fontawesome.com/releases/v5.6.3/css/all.css">
<link rel="stylesheet" href="https://unpkg.com/bootstrap-table@1.16.0/dist/bootstrap-table.min.css">

<script src="https://code.jquery.com/jquery-3.3.1.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.7/umd/popper.min.js"></script>
<script src="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/js/bootstrap.min.js"></script>
<script src="https://unpkg.com/bootstrap-table@1.16.0/dist/bootstrap-table.min.js"></script>
```

### 使用html

<img src="img\img_1.png" alt="Smiley face">


在table 增加屬性
```html
<table
  id="table"
  data-toggle="table"
  data-url="https://examples.wenzhixin.net.cn/examples/bootstrap_table/data">
  <thead>
    <tr>
      <th data-field="id">ID</th>
      <th data-field="name">Item Name</th>
      <th data-field="price">Item Price</th>
    </tr>
  </thead>
</table>
```

使用js
```html
<table id="sort-table">      
</table>
  
<script>



function getUserTable() {
    $('#sort-table').bootstrapTable({
      url: "https://examples.wenzhixin.net.cn/examples/bootstrap_table/data",
      dataType: "json",//default:json    
      uniqueId:'id',
      method: 'get',   //default:get    
      striped: true,               
      pagination : true,  
      pageSize : 15,     
      sidePagination: "client", //client/server
      
      //可於ToolBar上顯示的按鈕
      showColumns : true, //顯示/隱藏哪些欄位
      showColumnsToggleAll:true, //在欄位選擇開啟開關全部欄位 
      showToggle : true, //名片式/table式切換
      showPaginationSwitch : true, //分頁/不分頁切換
      showRefresh : true, //重新整理
      search : true, //查詢                       

      columns: [
          {   field:'checkbox', 
              title:'選取', 
              align:'center', 
              width:80, 
              visible:true, 
              checkbox:true
          },
          {   
              field:'id', 
              title:'ID',                               
              visible:false, 
              
          },
          {
              field: 'name',
              title: 'Name',
              sortable: true,
          },
          {
              field: 'price',
              title: 'price',
              sortable: true,
          },        
      ]
    },
  ) 
}


$(document).ready(function () {
    getUserTable();
});

</script>
```

## 問題記錄

### 設定formatter 導致filterControl 出不來

設定searchFormatter :false 
```
      columns: [   
          {
              field: 'project',
              title: 'Project',
              sortable: true,
              filterControl:"select",               
              align:"center",
              formatter: 'ProjectFormatter',
              searchFormatter :false,                
          },
``





