# cdnplz
A tool for uploading file to cdn.

# How to use?

```javascript
const cdnplz = require('cdnplz');

try{
    new cdnplz({
        tpl_suffix: 'jade',   //the suffix of template file
        tpl_path: 'app/view', //the root path of template file
        static_path: '.',  //the path of the static file
        output_path: 'output/view/', //the output path of template file
        file_encoding: 'utf8',
        cdn_provider: 'yourCdnProvider',//the cdn provider provided by user
        cdn_options: {//the options of the cdn provider
            https: true
        }
    }).start();
}catch(e){
    console.log(e);
}
```

# you should provide a cdn provider

```javascript
const cdnProvider = require('yourCdnProvider');

module.exports = {
    upload: function(filePath, options){
        return cdnProvider.upload(filePath, options);
    }
}
```
Cdn provider should return a object which has a `upload` method, and this `upload` method takes `filePath` and `options` as parameters, returns a Promise. The data resolved by the Promise must be a Object like this:
```
{ 
  './static/img/logo.png': 'https://p1.ssl.qhimg.com/t010a4bf91e826708df.png' ,
  './static/js/main.js': 'https://s0.ssl.qhimg.com/static/c870687eb082c330.js'
} 
```

# qiniu cdn Provider

https://github.com/webzhao/cdnplz-qiniu


