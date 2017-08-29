```javascript

Function.prototype.bind = function (thisArg) {
    var fn = this,
    slice = Array.prototype.slice,
    args = slice.call(arguments, 1);
    return function() {
        return fn.apply(thisArg, arg.concat(slice.call(arguments)));
    };
}

```


```javascript

Array.prototype.map = function(callback){
    var obj = this;
    var value,mapped_value;
    var A = new Array(obj.length);
    
    for(var i = 0 ; i < obj.length; i++){
        value = obj[i];
        mapped_value = callback.call(null,value);
        A[i] = mapped_value;
    }
    return A;
};

var arr= [1,2,3];

var new_arr = arr.map(function(value){
    return value * value;
});

```