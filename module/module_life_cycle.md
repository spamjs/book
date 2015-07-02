# Module Life Cycle

Each module has its own events which gets triggered during its life cycle.

```javascript
_define_("myproject.app",function(app,_app_){

    app._config_ = function(appConfig){
        console.log("App can be configured now");
    };

    app._define_ = function(){
        console.log("App has been defined");
    };

    app._ready_ = function(){
        console.log("Document is ready for DOM operations");
    };

    app._extended_ = function(childModule,childProto){
        console.log("App is being extend by "+childModule.module);
    };

    app._instance_ = function(params){
        console.log("App instance is being created");
        //Note 'this' here referes to instance bing created. So _instance_ can be seen as contructor function.
    };

});
```
