## Summary

File downloading in browser

## Getting and Using

`npm install f-download`

### Usage

`import download from 'f-download`

or

`const download = require('f-download')`

### Parameters

download(data, fileName, mimeType);

- **data** - The Blob, File, String, or dataURL containing the soon-to-be File's contents.
- **fileName** - The name of the file to be created. Note that older browsers (like FF3.5, Ch5) don't honor the file name you provide, instead they automatically name the downloaded file.
- **mimeType** - The MIME content-type of the file to download. While optional, it helps the browser present friendlier information about the download to the user, encouraging them to accept the download.

## Example Usage

#### text string

    download("hello world", "dlText.txt", "text/plain");

#### text dataURL

    download("data:text/plain,hello%20world", "dlDataUrlText.txt", "text/plain");

#### text blob

    download(new Blob(["hello world"]), "dlTextBlob.txt", "text/plain");

#### text url

    download("/robots.txt");

#### text UInt8 Array

    var str= "hello world",	arr= new Uint8Array(str.length);
    str.split("").forEach(function(a,b){

arr[b]=a.charCodeAt();
});

    download( arr, "textUInt8Array.txt", "text/plain" );

#### html string

    download(document.documentElement.outerHTML, "dlHTML.html", "text/html");

#### html Blob

    download(new Blob(["hello world".bold()]), "dlHtmlBlob.html", "text/html");

#### image from URL

    download("/diff6.png");

#### Image via ajax for custom filename

    var x=new XMLHttpRequest();
    x.open( "GET", "/diff6.png" , true);
    x.responseType="blob";
    x.onload= function(e){download(e.target.response, "awesomesauce.png", "image/png");};
    x.send();

## Compatibility

It works with major popular browsers and IE 10+.
