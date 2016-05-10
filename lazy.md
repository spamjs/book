# lazy.js

###lazy.promise(callback)
 returns value as a promise

###lazy.once(callback)
 executes function only once and caches the response for use any time it is called


###lazy.debounce (callback, wait)
 extended version of debounce which returns promise, which resolves everytime function is executed.

###lazy.repeat(callback, wait)
lazy verison of setInterval


Examples

```javascript
define({
    name : "lazyTest",
    modules : ["lazy"]
}).as(function(test,lazy){

    return {
        getData : lazy.promise(function(){
            return { name : "lalit" }
        }),
        _ready_ : function(){
            this.getData().done(function(valueObj){
                //valueObj
            })
        }
    };

})

```
