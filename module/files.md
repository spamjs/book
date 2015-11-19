# Files

###### package#module - jsutils/file#jsutils.file

## jsutils.file.getJSON
load JSON file from server and applies _dummyJSON_ if data is passed.

#####my_server/my_json_file.json
```json
{
	"people": {
		"id" : "{{data.id}}"
	}
}
```


#####Client Side Code
```javascript
var fileUtil = module("jsutils.file");

fileUtil.getJSON("my_server/my_json_file.json",{
    id : 100
}).done(function(resp){
	//formatted json
});
```

#####Formatted Output
```json
{
	"people": {
		"id" : "100"
	}
}

```

##jsutils.file.getHTML
load HTML file from server, applies _underscore_ templating on it.

#####my_server/my_html_file.html
```html
<div>
    <strong>Your Score is {{data.score}}</strong>
</div>
```

#####Client Side Code
```javascript
var fileUtil = module("jsutils.file");

fileUtil.getHTML("my_server/my_html_file.html",{
    score : 85
}).done(function(resp){
	//formatted html
});
```

#####Formatted Output
```html
<div>
    <strong>Your Score is 85</strong>
</div>

```

### Include Nested HTML
If template contains include tag, then nested HTML template is applied.  Data can be passed as you wish to nested template.

#####my_server/my_html_file2.html
```html
<div>
    <strong>Hi, {{data.name}}</strong>
    <include src="my_html_file.html" data=data.details />
</div>
```


#####Client Side Code
```javascript
var fileUtil = module("jsutils.file");

fileUtil.getHTML("my_server/my_html_file2.html",{
	 	name : "Lalit",
	 	details : {
	 		score : "85"
		}
	}).done(function(resp){
	//formatted html
});
```

#####OUTPUT
```html
<div>
		<strong>Hi, Lalit</strong>
		<div>
			<strong>Your Score is 85</strong>
		</div>
</div>
```
