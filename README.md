# cdnplz
A tool to upload file to cdn.

# How to use?

```javascript
const cdnplz = require('cdnplz');

try{
    cdnplz.init({
        tpl_suffix: 'jade',   //模板文件后缀名
        tpl_path: 'app/view', //模板根目录
        static_path: '.',  //静态资源的目录
        output_path: 'output/view/', //输出目录
        file_encoding: 'utf8', //文件编码
        cdn_provider: 'qcdn',
        cdn_provider_upload: 'upload',
        plugins: {
            qcdn: {
                https: true
            }
        }
    });
}catch(e){
    console.log(e);
}
```
