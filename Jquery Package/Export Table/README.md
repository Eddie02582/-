# Export Table

介紹兩種方法
<ol>
    <li>encodeURIComponent</li>
    <li>FileSaver</li>
</ol>



## use encodeURIComponent

使用outerHTML取得table的html代碼,透過encodeURIComponent轉換成網址,並產生一個<a> element,作為暫時下載的element


####
 ``` javascript
    function Table2Excel(table_id,name) {
      
      var table = document.getElementById('table').outerHTML  
      
      var uri = 'data:text/csv;charset=utf-8,' + encodeURIComponent(table);         
      
      var download_link = document.createElement('a'); // create element
      download_link.href = uri;  
      download_link.download = name + ".xlsx"; 
      document.body.appendChild(download_link);
      
      download_link.click();
      document.body.removeChild(download_link);
    }   
```
如果使用class 產生的table,匯出會沒有格式,可以改使用innerHTML在自行添加
 ``` javascript
    var table = document.getElementById(table_id).innerHTML //get innerHTML        
    table = "<table border=\"1\">" + table + "</table>"; 	//give tag    
```


## FileSaver

<a href = https://github.com/eligrey/FileSaver.js/>參考 eligrey </a>


#### Include script

```html
<script src="FileSaver.js"></script>
```

#### html Add javasctipt
 ``` html
<script>
function ExportTable2Excel(table_id,name) {
          
    var table= document.getElementById(table_id).innerHTML
    var data={'table': table}; 
    table= "<table border=\"1\">" + table + "</table>";    
    var filename = name+".xlsx"; 
    
    var blob = new Blob([table], {
            type: "text/csv;charset=utf-8"
    });          
    saveAs(blob,filename);
  
  }  
</script>
```

















