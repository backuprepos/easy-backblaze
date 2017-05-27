`npm install --save easy-backblaze`

A simpler reimagination of the Backblaze API. Upload a file in **one** call, just like in S3! Because of the depth and complexity of simply uploading, for now, this package will focus only on uploading a file. 

``` javascript
var B2 = require('easy-backblaze');
var b2 = new B2('account_id', 'application_key');

b2.uploadFile({
    file: fileBuffer, // Buffer of a file, the result of fs.readFile()
    bucket: 'swooty', // Optional, a bucket name, defaults to the first bucket
    name: 'swiggity-swooty.mp4' // Optional, defaults to sha1 hash of file
}, function(err, res) {
    console.log('Done!', err, res);
});

// res = https://f001.backblazeb2.com/file/swooty/swiggity-swooty.mp4
```
