# Module

Module is an independant entity existing in your project with its own dependency declared in module itself.

To define a module we will follow foo.js specification

```javascript
_define_("myproject.app",function(app){

    app.say_hello = function(){
        console.log("Another Hello World!");
    };

});
```

To get any module we use \_module\_ function

```javascript
_define_("myproject.app",function(app){

    var date_util = _module_("utils.date")

    app.say_hello = function(){
        console.log("Hello World! at time "+ date_util.get_time());
    };

});
```
To extend form parent module

```javascript

_define_("parent.app",function(app){

    app.say_hello = function(){
        console.log("I m parent Module");
    };

});

_define_("myproject.app","parent.app",function(app){

    var date_util = _module_("utils.date")

    app.say_hello = function(){
        console.log("Say hello to my parent app");
        this.parent().say_hello();
    };

});
```





