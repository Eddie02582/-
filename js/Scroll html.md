# how to scroll body 



```javascript
  

       // ���o�ؼа϶���y�y��
       var target_top = $("#id").offset().top;

       // ���obody���� �o�ؼg�k�b�U�s�����W�̫O�I
       var $body = (window.opera) ? (document.compatMode == "CSS1Compat" ? $('html') : $('body')) : $('html,body');

       // ���ʱ��b�L�ʵe�ĪG
     		//$body.scrollTop(target_top);

       // ���ʱ��b���ʵe�ĪG
     		$body.animate({
     			  scrollTop: target_top
     		}, 800)
```


