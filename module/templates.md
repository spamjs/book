# Templates

Using jsutils.files alos gives you additional apis, which are actually more useful.


## jsutils.file.loadTemplate(templateSrc,templateData)
```javascript

    /**
     * @params templateSrc {String|Function|Promise}
     * @params templateData {Map|String|Promise}
     */
    module("jsutils.file").loadTemplate(
        "path_to_my_file.html",{
            name : "Lalit"
        }
    ).done(function(resp){
        resp.html // output html
        resp.data //final data
    });

```

## jsutils.file.loadTemplate(options)
```javascript

    /**
     * @params options
     *      src {String|Function|Promise} - to return html source to be used
     *      data {Map|String|Promise} - to return data to be used
     *      html {String|Function|Promise} (optional)- to return html to be used
     *
     */
    module("jsutils.file").loadTemplate({
        src : "path_to_my_file.html",
        data : {
            name : "Lalit"
        }
    }).done(function(resp){
        resp.html // output html
        resp.data //final data
    });

```


###jQuery.loadTemplate(templateSrc,templateData)
```javascript

    jQuery("#myDiv").loadTemplate(
        "path_to_my_file.html",{
            name : "Lalit"
        }
    )

```
