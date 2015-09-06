# Module

Module is an independant entity existing in your project with its own dependency declared in module itself.

To define a module we can follow prototype based pattern


```javascript
define({
    name : "myproject.app"
}).as(function(app){

    return {
        say_hello : function(){
            console.log("Another Hello World!");
        }
    };

});
```

Or alternatilvely we can use namespace based pattern, usually used for static/global modules where you dont want to create instances for example global services/utilities

```javascript
define({
    name : "myproject.app"
}).as(function(app){

    app.say_hello = function(){
        console.log("Another Hello World!");
    };

});
```




