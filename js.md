
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
