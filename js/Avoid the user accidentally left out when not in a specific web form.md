# Avoid the user accidentally left out when not in a specific web form

透過onbeforeunload Event 當window, body, frameset 物件「被卸載之前」會先引發這個事件


下面這方法只有ie有效
```javascript
window.document.body.onbeforeunload = function()
{
    return '您尚未將編輯過的表單資料送出，請問您確定要離開網頁嗎？';
}
```
進行表單送出時不能出現這個離開網頁的提示框,所以你還必須在表單的 Submit按鈕特別加上一段 JavaScript 將 事件取消。
<input type="submit" value="送出" onclick="window.document.body.onbeforeunload=null;return true;" />


以下ie/firefox/chroma 接可以

```javascript
window.onbeforeunload = function (e) {
    var e = e || window.event;

    // For IE and Firefox
    if (e) {
        e.returnValue = 'Any string';
    }

    // For Safari/Chroma
    return 'Any string';
};
 ```
注意在 Firefox 4 及以後，返回值不會顯示
