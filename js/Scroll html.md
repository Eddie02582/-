# how to scroll body 



```javascript
    var locationY = 60;
    var $body = (window.opera) ? (document.compatMode == "CSS1Compat" ? $('html') : $('body')) : $('html,body');
    $body.animate({scrollTop:locationY},800);
    //$body.scrollTop(200)
```


