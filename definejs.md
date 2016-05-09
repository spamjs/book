# define.js
To define any module we use define function.


##Define Module
#####MyFirstModule.js
```javascript
define({
    name : "MyFirstModule"
}).as(function( MyFirstModule){

    return {
        sayGoodMorning : function(name){
            console.log("Good Morning, " + name);
        },
        sayGoodNight : function(name){
            console.log("Good Night, " + name);
        }
    };

});
```
Using *MyFirstModule*

```javascript
module("MyFirstModule", function(MyFirstModule){
    MyFirstModule.sayGoodMorning("Lalit");
});

//Or we can also create instance of MyFirstModule, which follows prototype-chain

module("MyFirstModule", function(MyFirstModule){
    var myMod = MyFirstModule.instance();
    myMod.sayGoodMorning("Lalit");
});
```

##Inheritence
To extend module from another module

```javascript
define({
    name : "MySecondModule",
    extend : ["MyFirstModule"]
}).as(function( MySecondModule){

    return {
        saySomething : function(isMorning,name){
            if(isMorning){
                return this.parent().sayGoodMorning.call(this,name);
            } else {
                return this.parent().sayGoodNight.call(this,name);
            }
        }
    };

});

```

##Module depenedncy

```javascript
define({
    name : "MyThirdModule",
    using : ["MySecondModule","TimeUtil"]
}).as(function( MyThirdModule, MySecondModule, TimeUtil){

    return {
        greet : function(name){
            return MySecondModule.saySomething(name,TimeUtil.isMoring())
        }
    };

});

```


