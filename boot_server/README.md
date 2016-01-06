# Boot Server

#####in GruntFile.js
```javascript
    //Server Config is part of boot config
    bootloader: {
      options: {
        indexBundles: ["webmodules/bootloader"],
        src: "./",
        dest: "build/dist",
        resourcesFile: "resources/resource.json",
        livereloadUrl: "http://localhost:8081/livereload.js",
        bootServer: {
          port: 8087
        }
      }
    }
    //load tasks
    grunt.loadNpmTasks('grunt-bootloader');
    //Set alias for server start
    grunt.registerTask('start-server', ['bootloader:server']);
```
#### To start server
```
grunt start-server
```




