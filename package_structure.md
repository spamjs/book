# Package Structure

- mypackage
    - mypackage.mymodule.js
    - mypackage.mymodule.html
    - mypackage.mymodule.css
    - module.json

### module.json
```
{
  "name": "mypackage/mymodule",
  "mypackage/mymodule": {
  	"on": ["extmodule/someodule"],
    "css": ["mypackage.mymodule.css"],
    "js": ["mypackage.mymodule.js"],
    "html": ["mypackage.mymodule.html"]
  }
}

```

*module.json* contains relative path to all the files, in package, which is then scanned by bootloader and final resources file sis created which is used by client to load module files on demand.

One package can have multiple bundles for example *mypackage/mymodule/bundle1* and *mypackage/mymodule/bundle2*

and can be used independently just like other package names.


