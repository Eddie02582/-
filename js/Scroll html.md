# how to scroll body 



```javascript
  

       // 取得目標區塊的y座標
       var target_top = $("#id").offset().top;

       // 取得body物件 這種寫法在各瀏覽器上最保險
       var $body = (window.opera) ? (document.compatMode == "CSS1Compat" ? $('html') : $('body')) : $('html,body');

       // 移動捲軸無動畫效果
     		//$body.scrollTop(target_top);

       // 移動捲軸有動畫效果
     		$body.animate({
     			  scrollTop: target_top
     		}, 800)
```


