# Table Option



## code
<a href = "https://live.bootstrap-table.com/code/Eddie02582/6721">link</a>
```html
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
       pageSize : 15,    
     	 height:500,
       buttons:buttons,
       buttonsPrefix:"btn-sm btn",
       //cardView:true,
       columns: 
       			[ 
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

    function buttons () {
      return {
        btnUsersAdd: {
          text: 'Highlight Users',
          icon: 'fa-users',
          event: function () {
            alert('Do some stuff to e.g. search all users which has logged in the last week')
          },
          attributes: {
            title: 'Search all users which has logged in the last week'
          }
        },
        btnAdd: {
          text: 'Add new row',
          icon: 'fa-plus',
          event: function () {
            alert('Do some stuff to e.g. add a new row')
          },
          attributes: {
            title: 'Add a new row to the table'
          }
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
    function buttons () {
      return {
        btnUsersAdd: {
          text: 'Highlight Users',
          icon: 'fa-users',
          event: function () {
            alert('Do some stuff to e.g. search all users which has logged in the last week')
          },
          attributes: {
            title: 'Search all users which has logged in the last week'
          }
        },
        btnAdd: {
          text: 'Add new row',
          icon: 'fa-plus',
          event: function () {
            alert('Do some stuff to e.g. add a new row')
          },
          attributes: {
            title: 'Add a new row to the table'
          }
        }
      }
    }   
  
  $(function() {
    initTable()  
  })

</script>

```









