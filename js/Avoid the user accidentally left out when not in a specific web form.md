# Avoid the user accidentally left out when not in a specific web form

�z�Lonbeforeunload Event ��window, body, frameset ����u�Q�������e�v�|���޵o�o�Өƥ�


�U���o��k�u��ie����
```javascript
window.document.body.onbeforeunload = function()
{
    return '�z�|���N�s��L������ưe�X�A�аݱz�T�w�n���}�����ܡH';
}
```
�i����e�X�ɤ���X�{�o�����}���������ܮ�,�ҥH�A�٥����b��檺 Submit���s�S�O�[�W�@�q JavaScript �N �ƥ�����C
<input type="submit" value="�e�X" onclick="window.document.body.onbeforeunload=null;return true;" />


�H�Uie/firefox/chroma ���i�H

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
�`�N�b Firefox 4 �ΥH��A��^�Ȥ��|���
