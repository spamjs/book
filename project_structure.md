# Project Structure

### Directoy Structure
- **app** - *Node Server Application*
    - **controller**
    - **view**
    - **data**
    - **helper.json**
- **node_modules** - *Node components are installed here*
- **src** - *Client-Project Source Files*
    - **external**
        - **components** - *Bower Components are installed here*
    - **myapp.js** - *Entry module for client-application*
- **dist** - *generated files*
- **index.html**
- **bower.json**
- **package.json**
- **GruntFile.js**


##npm modules
- grunt-bootloader
- dummy-json
- connect-livereload
- grunt-contrib-uglify
- grunt-contrib-watch
- underscore

##bower modules
 - webmodules-foo
 - webmodules-bootloader
 - spamjs-view
 - spamjs-bootconfig


##GruntFile.js options
```javascript
    ...

    bootloader: {
      options: {
        indexBundles: ["webmodules/bootloader", "myproject/app"],
        src: "./",
        dest: "dist",
        resourceJson: "dist/resource.json",
        resourcesInline : true,
        livereloadUrl: "http://localhost:8081/livereload.js",
        bootServer: {
          port: 8087,
          indexMatch : /^\/olp\//
        }
      }
    },

    ....

    grunt.loadNpmTasks('grunt-contrib-cssmin');
    grunt.loadNpmTasks('grunt-bootloader');

    ...

    grunt.registerTask('scan', ['cssmin','bootloader:scan:skip']);
    grunt.registerTask('build', ['cssmin','bootloader:bundlify']);
    grunt.registerTask('start-cdn-server', ['bootloader:server', 'watch']);

    ...

```

##index.html

```html
<script src="http://my-static-content.com/dist/bootloader_bundled/webmodules.bootloader.js">
    bootloader({
        debug : false,
        indexBundle : "myproject/app",
        version: "2"
    });
</script>

```




