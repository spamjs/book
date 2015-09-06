# define.js
To define any module we use define function.

```javascript

define({
    name : "MyFirstModule",
    extend : "ParentModule" //Optional,
    using : ["Module1", "Module2", "Module3"] // Optional
}).as(function( MyFirstModule, Module1, Module2, Module3){


    return {
        sayGoodMorning : function(name){
            console.log("Good Morning, " + name);
        },
        sayGoodNight : function(){
            console.log("Good Night, " + name);
        }
    };

});
```

To use module **MyModuleName**

```javascript
define({
    name : "MySecondModule",
    using : ["MyFirstModule","TimeUtil"]
}).as(function( MySecondModule, MyFirstModule, TimeUtil){

    return {
        saySomething : function(name){
            if(TimeUtil.isMorning()){
                return MyFirstModule.sayGoodMorning(name);
            } else {
                return MyFirstModule.sayGoodNight(name);
            }
        }
    };

});

```

Alternativly we could have done this also.

```javascript
define({
    name : "MyThirdModule",
    using : ["TimeUtil"]
}).as(function( MyThirdModule, TimeUtil){

    var MyFirstModule = module("MyFirstModule");

    return {
        greet : function(name){
            if(TimeUtil.isMorning()){
                return MyFirstModule.sayGoodMorning(name);
            } else {
                return MyFirstModule.sayGoodNight(name);
            }
        }
    };

});
```

This one is usefule when we are resolving module name at run-time. _module_ function also accepts second argument optionally, as callback.

```javascript

    module("MyFirstModule", function(MyFirstModule){
        MyFirstModule.sayGoodMorning(name);
    });


```

As we can see this is asyncronous, useful incase all modulesare not loaded initally and being loaded on asynchronously-on-demand also known as lazy-loading.

Usually modules are for global use, but we can create instance of any module, which internally follows prototype chanining.

```javascript

    var MyFirstModule = module("MyFirstModule");
    var myFirstInstance = MyFirstModule.instance();

```
Prototype chaning for this example would be like as

```
    myFirstInstance --> MyFirstModule --> ParentModule
```







