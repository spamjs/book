# Controller

Controller are modules kept in ***app/controller*** folder

##### app/controller/MainController.js
```javascript
module.exports = function(router){

  router.on({
    "url" : "/createseassion/{fname}/{lname}"
  },function(lname,fname){
    this.user.role = "USER";
    this.user.set("fname",fname);
    this.user.set("lname",lname);
    return this.view("test.html",{ fname : fname,lname : lname});
  });

  router.on({
    "url" : "/json/public/{fname}/{lname}"
  },function(lname,fname){
    return this.json("test.json",{
        fname :  this.user.get("fname"),
        lname : this.user.get("lname")
    });
  });

  router.on({
    "url" : "/json/authorised/{fname}/{lname}",
    "roles" : ["USER"]
  },function(lname,fname){
    return this.json({
        fname :  this.user.get("fname"),
        lname : this.user.get("lname")
    });
  });

};

```

### Properties Aviable in Controller Methods
* **this.user** - session user for request
    * this.user.set("key","value");
    * this.user.get("key");
    * this.user.role - *role for user*
* **this.session** - current session
    * this.sesssion.set("key","value");
    * this.session.get("key");
* **this.cookies** - browser cookies manager
    * this.cookies.set("key","value");
    * this.cookies.get("key");




