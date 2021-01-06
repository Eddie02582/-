# Bootstrap-Table

## 如何使用
需要使用以下才能使用

```html
<link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css" integrity="sha384-ggOyR0iXCbMQv3Xipma34MD+dH/1fQ784/j6cY/iJTQUOhcWr7x9JvoRxT2MZw1T" crossorigin="anonymous">
<link rel="stylesheet" href="https://use.fontawesome.com/releases/v5.6.3/css/all.css">
<link rel="stylesheet" href="https://unpkg.com/bootstrap-table@1.16.0/dist/bootstrap-table.min.css">

<script src="https://code.jquery.com/jquery-3.3.1.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.7/umd/popper.min.js"></script>
<script src="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/js/bootstrap.min.js"></script>
<script src="https://unpkg.com/bootstrap-table@1.16.0/dist/bootstrap-table.min.js"></script>
```

## Example
<img src="img\img_1.png" alt="Smiley face">


在table 增加屬性
```html
<!-- data-show-toggle 在toolbar增加cardview切換鈕

data-show-columns="true" 在toolbar開啟欄位選擇
data-show-columns-toggle-all="true"  在欄位選擇開啟開關全部欄位 

data-show-refresh="true"  在toolbar增加refresh鈕

data-click-to-select 設定第一欄為checkedbox,需搭配data-checkbox="true"
data-checkbox-header="false" 在header 關閉checkbox功能(關閉全選功能)

data-pagination="true" 設定分頁
data-show-pagination-switch="true" 在toolbar增加分頁切換鈕 -->

<table id="sort-table" 
        data-toggle="table"	
		data-url="https://examples.wenzhixin.net.cn/examples/bootstrap_table/data"		
		height = "450"
        data-pagination="true"       
        data-show-fullscreen="true"
        data-show-toggle="true"         
        data-show-columns="true"
		data-show-columns-toggle-all="true"   
        data-show-fullscreen="true"
        data-show-refresh="true"   
		data-checkbox-header="false"
		data-click-to-select="true"        
        data-pagination="true" 
        data-show-pagination-switch="true"  
		data-checkbox-header="false"
		data-click-to-select="true"         
        data-search="true"
       >
    <thead>
      <tr>
        <th data-field="state" data-checkbox="true"></th>
        <th data-field="id" data-sortable="true">ID</th>
        <th data-field="name" data-sortable="true">Item Name</th>
        <th data-field="price" data-sortable="true">Item Price</th>
      </tr>

    </thead>

</table>
```












