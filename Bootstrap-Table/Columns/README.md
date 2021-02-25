# Columns
columns 可以用來設定欄位格式設定,以下介紹常用的欄位

## field
設定該欄位的資料,需對應url裡面的名字
## title
設定該欄位的title
## visible
設定該欄位是否顯示
## formatter
使用方法formatter:function

## event


# code
<a href = "https://live.bootstrap-table.com/code/Eddie02582/6720">link</a>
```html
<script>
  var $table = $('#table')  
  
  function initTable() {
     $table.bootstrapTable({
       url: "json/data1.json",
       columns: [ 
          	{               
              title:'State',
              checkbox:true, 
              formatter:stateFormatter,
            },
          	{ 
              field :"id",
              title:'ID',
              visible:false, 
            },
            { 
              field :"name",
              title:'Item Name',
              valign:'middle',
              align:'center',
              formatter:nameFormatter,
              cellStyle:nameCellStyle,           
              
            },
          	{ 
              field :"price",
              title:'Item Price' 
            },   
           	{               
              title:'action',
              formatter:"operateFormatter",
          		events:"operateEvents",
            }, 
        ],
        
        
     })
     function nameFormatter(value, row) {
        var icon = row.id % 2 === 0 ? 'fa-star' : 'fa-star-and-crescent'
        return '<i class="fa ' + icon + '"></i> ' + value
    }  
    
    function stateFormatter(value, row, index) {
        if (index === 2) {
          return {
            disabled: true
          }
        }
        if (index === 5) {
          return {
            disabled: true,
            checked: true
          }
        }
        return value
    }  
    
    function nameCellStyle(value, row, index) {      
      	var color = row.id % 2 === 0 ? 'gray' : 'white';
        return {
            css: {
              'background-color':color
            }
        }      
    }
  } 
  
   window.operateEvents = {
      'click .like': function (e, value, row, index) {
        alert('You click like action, row: ' + JSON.stringify(row))
      },
      'click .remove': function (e, value, row, index) {
        $table.bootstrapTable('remove', {
          field: 'id',
          values: [row.id]
        })
      }
    }
  
    function operateFormatter(value, row, index) {
      return [
        '<a class="like" href="javascript:void(0)" title="Like">',
        '<i class="fa fa-heart"></i>',
        '</a>  ',
        '<a class="remove" href="javascript:void(0)" title="Remove">',
        '<i class="fa fa-trash"></i>',
        '</a>'
      ].join('')
    }
  
  $(function() {
    initTable()  
  })

</script>

```









