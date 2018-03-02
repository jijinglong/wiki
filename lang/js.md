
## Util

``` javascript
function toArray(obj) {
    var keys = Object.keys(obj);
    return keys.map(function (k) {
        return obj[k];
    });
}
```

``` javascript
function toNestedArray(table) {
    if (table.length === 0) {
        return [];
    }
    var fields = Object.keys(table[0]);
    var values = table.map(function (r) {
        return fields.map(function (f) {
            return r[f];
        });
    });
    return [fields].concat(values);
}
```

``` javascript
/**
 * 创建并下载文件
 * @param  {String} fileName 文件名
 * @param  {String} content  文件内容
 */
function createAndDownloadFile(fileName, content) {
    var aTag = document.createElement('a');
    var blob = new Blob([content]);
    // var blob = new Blob(['a,b,c\n'+'d,e,f\n'], {type: 'text/csv'});
    aTag.download = fileName;
    aTag.href = URL.createObjectURL(blob);
    aTag.click();
    URL.revokeObjectURL(blob);
}
```
