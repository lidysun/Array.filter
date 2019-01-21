### W3C API（只兼容IE9及以上）
![这里写图片描述](https://img-blog.csdn.net/20180411173524896?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2xpZHlzdW4=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)
### 重写Array数组的filter方法

```
Array.prototype.filter = function(fn) {
    var newArray = [];
    var length = this.length;
    var i = 0;
    for(;i<length;i++){
        if(fn(this[i])){
            newArray.push(this[i])
        }
    }
    return newArray;
};
```
### 测试（IE7 8均测试通过）

```
console.log([1,2,7,12,44].filter(function(n){
    return n>10
}))
//[12,14]
```

```
console.log(
    [{
        type:1,
        name:'test1'
    },{
        type:2,
        'name':'test2'
    }].filter(function(n){
        return n.type == 1
    })
)
//[{type:1,name:'test1'}]
```

