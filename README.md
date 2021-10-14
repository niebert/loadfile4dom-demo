# LoadFile4DOM - Demo File - Wikiversity
`LoadFile4DOM` is a library that allows to load files into an web application that run completely in a browser without the need to submit data to a remote server for processing. With this library the users are able load files into your browser application and process the data in the browser and provide the output to the user, without submitting any data to a remote server. The files in the repository are the demo files for the [learning resource AppLSAC/Load in Wikiversity](https://en.wikiversity.org/wiki/AppLSAC/Load). You can check out the demo directly or by downloading a ZIP of the repository from https://www.github.com/niebert/loadfile4dom-demo  
* **[Demo LoadFile4DOM](https://niehausbert.gitlab.io/loadfile4dom)**
* **[Demo LoadFile4DOM on GitHub](https://niebert.github.io/loadfile4dom-demo)** the [GitHub repository `loadfile4dom-demo`](https://www.github.com/niebert/loadfil4dom-demo) just contains the demo files without the development environment. For the [Wikiversity learning environment about AppLSAC](https://en.wikiversity.org/wiki/AppLSAC) the demo files are used for understanding the basic concept of the load process of an [AppLSAC](https://en.wikiversity.org/wiki/AppLSAC). So downloading just
the demo files is used for playing around and modifying the HTML/JS/CSS files to understand the [Load Process into a browser](https://en.wikiversity.org/wiki/AppLSAC/Load) without submitting the data to a remote server.
<!-- BEGIN: src/readme/abstract.md -->

* **(Analogy - Load in Desktop Applications)** In standard desktop application like [LibreOffice](https://www.libreoffice.org/) users are able to load files and process/edit the document. `LoadFile4DOM` does the same for WebApps and loads data (e.g. text files) for processing or editing into WebApp (which is defined by HTML and Javascript-Code). `LoadFile4DOM` provides Load Dialog and programmers define withn `onload` handlers, what to do with the uploaded file (see [list of examples](https://niehausbert.gitlab.io/loadfile4dom)).
* **(File Access to Local Filesystem)** For security reason browsers are not allowed to access the local file system. On the other hand sending user data to a remote server can be avoided by processing the data in the browser without submitting the data to a remote server.\nSee a first example, in which users can load a textfile into textarea.\nWhen you have the text in the textarea you can process the content in the browser and show the results to the user in the textarea.
<!-- END: src/readme/abstract.md -->

<!-- BEGIN: src/readme/headerinto.md -->
The following table of contents is generated with `node doctoc README.md`.
<!-- END:   src/readme/headerinto.md -->
<hr>
<h2>Table of Contents</h2>

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->


- [Demo Files LoadFile4DOM](#demo-files-loadfile4dom)
- [Installation `LoadFile4DOM`](#installation-loadfile4dom)
  - [Installation for Browsers](#installation-for-browsers)
  - [NodeJS - Update `LoadFile4DOM` with new Features](#nodejs---update-loadfile4dom-with-new-features)
  - [NodeJS Testing Library `LoadFile4DOM` with JSDom](#nodejs-testing-library-loadfile4dom-with-jsdom)
- [Quick Start for Library-Users](#quick-start-for-library-users)
- [Usage](#usage)
  - [File Extensions](#file-extensions)
  - [Return Types](#return-types)
  - [Image Thumb](#image-thumb)
  - [Format of the Returned Filehash](#format-of-the-returned-filehash)
  - [Load Images](#load-images)
  - [Load Files into JSON/Javascript](#load-files-into-jsonjavascript)
  - [Load LibreOffice Files in WebApp](#load-libreoffice-files-in-webapp)
  - [ZIP-Files](#zip-files)
- [Scan Files in `docs/` Folder](#scan-files-in-docs-folder)
  - [Create `docs/index.html` for Demos as HTML](#create-docsindexhtml-for-demos-as-html)
  - [Create `src/readme/demos.md` for Demos in Markdown](#create-srcreadmedemosmd-for-demos-in-markdown)
- [Wikiversity](#wikiversity)
- [Build Process of `npm run build`](#build-process-of-npm-run-build)
  - [Define Filename for build in `package.json`](#define-filename-for-build-in-packagejson)
  - [Compress after Build](#compress-after-build)
- [API for Javascript Class: `LoadFile4DOM`](#api-for-javascript-class-loadfile4dom)
  - [Diagram](#diagram)
  - [Attributes: `LoadFile4DOM`](#attributes-loadfile4dom)
    - [Attribute `aDoc : Document`](#attribute-adoc--document)
    - [Attribute `aOptions : Hash`](#attribute-aoptions--hash)
    - [Attribute `aFileLoader : Hash`](#attribute-afileloader--hash)
    - [Attribute `aLoadFileHolder : Object`](#attribute-aloadfileholder--object)
    - [Attribute `defaults_options :  `](#attribute-defaults_options---)
    - [Attribute `type2accept :  Hash`](#attribute-type2accept---hash)
    - [Attribute `defaults_loader :  `](#attribute-defaults_loader---)
    - [Attribute `aLoaderCount :  Integer`](#attribute-aloadercount---integer)
- [Build and Compress with Browserify, Watchify, UglifyJS](#build-and-compress-with-browserify-watchify-uglifyjs)
  - [Browserify and Watchify](#browserify-and-watchify)
  - [Global Installation of Browserify, Watchify, UglifyJS and DocToc](#global-installation-of-browserify-watchify-uglifyjs-and-doctoc)
  - [Package Installation of Browserify and Watchify - Alternative](#package-installation-of-browserify-and-watchify---alternative)
  - [Start Watching the Files with Watchify](#start-watching-the-files-with-watchify)
  - [Source JS file and development bundle output](#source-js-file-and-development-bundle-output)
- [Acknowledgement](#acknowledgement)
- [Libraries required for  `LoadFile4DOM`](#libraries-required-for--loadfile4dom)
- [Libraries for Building and Developement](#libraries-for-building-and-developement)
- [NPM Library Information](#npm-library-information)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## Demo Files LoadFile4DOM
Demo files scanned with `scan_demos4readme.sh` - Last Update: 20.10.2019
Generated file `./src/readme/demos.md` was included into `README.md` after calling `npm run build`
* [Demo 1: Load File into Text Area](https://niehausbert.gitlab.io/loadfile4dom/demo1_load_into_textarea.html)
* [Demo 2: Load Files into ZIP file with JSZip](https://niehausbert.gitlab.io/loadfile4dom/demo2_load_files2zip.html)
* [Demo 3: Load Files into ZIP file with JSZip - minimal example](https://niehausbert.gitlab.io/loadfile4dom/demo3_load_files2zip.mini.html)
* [Demo 4: Load Images into ZIP file and display in DOM](https://niehausbert.gitlab.io/loadfile4dom/demo4_load_images2zip.html)
* [Demo 5: Load Files into base64 encoded JSON](https://niehausbert.gitlab.io/loadfile4dom/demo5_file2base64_json.html)
* [Demo 6: Load ZIP File and add multiple Files to ZIP](https://niehausbert.gitlab.io/loadfile4dom/demo6_load_zip_add_files.html)
* [Demo 7: Load ZIP and add multiple Files to ZIP - minimal example](https://niehausbert.gitlab.io/loadfile4dom/demo7_load_zip_add_files.mini.html)
* [Demo 8: Load JSON into Handlebars Template Engine](https://niehausbert.gitlab.io/loadfile4dom/demo8_load_json4handlebars.html)
For further information see [Wikiversity](https://en.wikiversity.org/wiki/AppLSAC)


## Installation `LoadFile4DOM`
The library was designed to used in a browser (WebApp). So use the installation for your browser by using a bundle `dist/loadfile4dom.js` (ee example `https://niehausbert.gitlab.io/loadfile4dom`).

### Installation for Browsers
If you want to use the library `loadfile4dom.js` in a browser, please copy the file `dist/loadfile4dom.js` into your library folder of WebApp that you want to test with a browser (e.g. `js/loadfile4dom.js`). If you want expand existing examples check the basic example in `docs/index.html` first and play around with that HTML-file. If you want to import the library with `script`-tag do it in the standard way with:
```html
<script src="js/loadfile4dom.js"></script>
```
Now it is possible to use the constructor of `LoadFile4DOM`
```javascript
var  lf4d = new LoadFile4DOM();
```
Now we define a hash that contains the options for the `init()`-call.
```javascript
var vOptions = {
  'debug': false
};
lf4d.init(doccument, vOptions);
```
After the `init()` call the loaders are defined (see section about Usage). `debug=true` shows the holder and the `<input type="file" ...>` elements in the browser view of the HTML page. Default settings is false.

Keep in mind that injection of the Load Dialogs must be performed when the document was loaded, so we need to call the `create()` method when the `onload` event was triggered by the browser. This is done by:
```html
<body onload="lf4d.create()">
```

### NodeJS - Update `LoadFile4DOM` with new Features
This sections is for developers that want to extend or modify the features of `LoadFile4DOM`.

Assume you want to expand the file handler for `zip`-files in a way, that it will return an instance of `JSZip` directly. Currently `LoadFile4DOM` with the loadtype `zip` will just take care, that only `zip` files with correct MIME type `application/zip` can be selected with `zip`-Loader. To extend the `LoadFile4DOM` module we require multiple file instead of the raw binary of the zip-file. So we update the method `handle_zip()`.

Lets call your new NPM module `loadzip4dom` and we create an empty directory with that name and call as usual a `package.json` with:
```JavaScript
npm init
```
use as entry point `src/main.js`
and add the module `LoadFile4DOM` to dependencies of your new package by:
```javascript
npm install --save loadfile4dom
```
Now we create a directory `src` and a file `src/main.js` can `require` the added module to the

Now the module is installed and you can to use the constructor `LoadFile4DOM` in your new Node NPM module with the following require-call:
```javascript
// require all the modules you need for the new browserified library ...

const  LoadFile4DOM = require('loadfile4dom');
LoadFile4DOM.prototype.handle_zip = function (...) {
  // write a new ZIP file handler e.g. using JSZip
  //
}
//... export the instance with new feature
module.exports = LoadFile4DOM;
```
You find a UML file of
Due to the fact that the library was designed for WebApps that run in a regular browser, the library requires `Document Object Model (DOM)` to create a load dialog for loading files in a browser also your new module must be [browserified](http://browserify.org/) e.g. into the module `LoadZip4DOM` - see [AppLSAC](https://en.wikiversity.org/wiki/AppLSAC) in Wikiversity for further details.


### NodeJS Testing Library `LoadFile4DOM` with JSDom
In order to test new feature we require in `test`-script the library [`jsdom`](https://www.npmjs.com/package/jsdom).

To test and expand the Library with additional feature we create in test-scripts like `tests/test.js` as a DOM content. Wit `jsdom` module we can analyse if the library properly  inject the required HTML elements into the DOM of browser without for testing the modification of the code with the HTML file `docs/index.html` and an appropriate `script`-tag `<script src="js/loadfile4dom.js"></script>` in the browser.

The following code shows the test script `tests/test.js` that can be executed with `node tests/test.js` of with `npm run buildtest`.

```javascript
// emulate the DOM with 'jsdom'
const jsdom = require('jsdom');
const { JSDOM } = jsdom;

const  LoadFile4DOM = require('../src/main.js');
let  lf4d = new LoadFile4DOM();
// define options for LoadFile4DOM holder in the DOM

```
We need to feed a DOM content, that `LoadFile4DOM` works with. The sample DOM tree in the test script `tests/test.js` was defined as. Modify the content according to your test settings.
```javascript
const vDOM = new JSDOM(`<!DOCTYPE html>
<html>
  <body>
    <textarea id="mytxtfile" row="5" cols="80"></textarea>
    <div id="myloaderid" style="display:none">
    </div>
  <body>
</html>`);
// create a reference for the window.document
let doc = vDOM.window.document;
```
Now we have an emulated DOM with the reference to the `document` object, that allows the test the DOM element injection.
```javascript
let vOptions = {
  'id4loadfile': 'myloaderid',
  'debug': true
};
lf4d.init(doc, vOptions)
```
* (optional) `'debug':true` shows the injected `<input type='file' ...>` that are injected into the DOM tree by `LoadFile4DOM`.
* (optional) `'id4loadfile': 'myloaderid'` the ID of the `div` element to which the all loaders (e.g. for `text`, `images`, `json`, `zip` are injected.
* All loaders are created by one instance of `LoadFile4DOM` to assure a conflict free ID management of generated `<input type='file' ...>` elements in the DOM.
* if you have an `iframe` in your DOM it has an own `document` object. You might want to create another instance for injecting loaders in the iFrame document as well.

**Remark:** Keep in mind that you should create an instance of `LoadFile4DOM` every different `document` object you are injecting Load Dialog to. In general one instance should be sufficient in most use-cases for  `LoadFile4DOM`.
<!-- BEGIN: src/readme/usage.md -->

## Quick Start for Library-Users
Just copy the `docs/`-folder or rename to `myloadfile4dom` and adapt the examples to your needs.
Check out the examples:
* [Load file into textarea](https://niehausbert.gitlab.io/loadfile4dom/loadtextarea.html)
* [Load files into ZIP](https://niehausbert.gitlab.io/loadfile4dom/upload2zip.html)
* [Load Images into DOM and into ZIP](https://niehausbert.gitlab.io/loadfile4dom/loadimages.html)
* [Load JSON into Template Engine Handlebars4Code](https://niehausbert.gitlab.io/loadfile4dom/handlebars4code.html)
Check the javascript source in HTML file. [Download ZIP file of LoadFile4DOM](https://gitlab.com/niehausbert/loadfile4dom/-/archive/master/loadfile4dom-master.zip)

## Usage
You can have one or more `LoadFile4DOM` nodes in your webbased application. The following code shows how to create `LoadFile4DOM` node (see [Demos Examples](https://niehausbert.gitlab.io/loadfile4dom))
```javascript
var lf4d = new LoadFile4DOM();
var options = {
  "id4loadfile": "allmyloaddialogs"
};
lf4d.init(document,options);
var txtfile = lf4dom.get_options("mytxtfile","all");
// set the onload handler for the loaded files
//txtfile.returntype = "file" and not "filehash" so data contains the textstring
txtfile.onload = function (data,err) {
  if (err) {
    console.error(err);
  } else {
    // do something with the file content in data e.g. store  in a HTML textarea (e.g. <textarea id="mytextarea" ...>
    document.getElementById("mytextarea").value = data.file;
  }
}
lf4d.create_load_dialog(txtfile);
```
The Load Dialogs are created with the `onload` event handler in the body tag of your HTML file.

```html
   <body onload="lf4d.create()">
```

Now you can define an `onclick` event in a button to open the load menu similar to the upload feature of web sites.
```html
<input type="button" onclick="lf4d.open_dialog('mytxtfile')" value="Load TXT File">
```
or with a `button`-tag with
```html
<button onclick="lf4d.open_dialog('myhtmlfile')"> Load HTML File</button>
```
Furthermore you can open the menu with an `onclick` event on a link by
```html
This is a <a href="#" onclick="lf4d.open_dialog('myhtmlfile')">link to open the menu</a> in a HTML file.
```

### File Extensions
It is possible to set a mandatory file extension for the loaded files. This mandatory file extension will be checked for all loaded files. The following code creates a `DIV` tag in the DOM with the ID `allmyloaddialogs`. This ID can be used for debugging and learning about `LoadFile4DOM`, because by `document.getElementById('allmyloaddialogs')`  programmers can analyse what is injected in the DOM tree for the generated loaders (see [Demos Examples](https://niehausbert.gitlab.io/loadfile4dom)).

In this example the file extensions can be set with `txtfile.file_extension = ".txt"` after generating the default options for a new text file loader with the ID `mytextfile`.

```javascript
//--- Create a LoadFile4DOM instance ---
// you need one instance for all loaders
var lf4d = new LoadFile4DOM();
var options = {
  "id4loadfile": "allmyloaddialogs"
};
lf4d.init(document,options);

//-----------------------------------------------
//----- Create a new Loader "mytxtfile" ---------
//-----------------------------------------------
var txtfile = lf4d.get_loader_options("mytxtfile","text");
// set mandatory file extensions
txtfile.file_extension = ".txt";
// set the onload handler for the loaded files
txtfile.onload = function (data,err) {
  // define file handler

}
lf4d.create_load_dialog(txtfile);
```
Mandatory file extensions are helpful especially for `zip`-files:
* [Geogebra files](https://www.geogebra.org) are `zip`-files and they have the file extension `.ggb`. The corresponding [MIME](https://en.wikipedia.org/wiki/Media_type) type for `ggb`-files is `application/vnd.geogebra.file`
* [LibreOffice Writer files](https://www.libreoffice.org/discover/writer/) are `zip`-files and they have the file extension `.odt`. The corresponding [MIME](https://en.wikipedia.org/wiki/Media_type) type for `ODT` is
`application/vnd.oasis.opendocument.text`

The file extension check is implemented in the method `LoadFile4DOM.error_file_type()`.

### Return Types
The onload handler could get different processed JSON objects as return types.
* `file` is
  * just the text for file type `text`
  * the parsed JSON for file type `json`
  * binary version (blob) of loaded file
* `filehash` contains also the filename if browser return the name of the file. This is not standard and might result in an unexpected behavior if not used in Firefox or Chrome. `filehash` return a hash with
```javascript
   data = {
     "name": "myloadedfile.txt",
     "file": "the content of the loaded text file",
     "mime_type":"text/plain"
   }
```
  * here the attribute `data.file` contains the text of file, or
  * **Loader Type: `json`** `data.file` contains the parsed JSON for the loader file type `json`
  * `data.file` contains the base64 content of loaded file
  * `mime_type` contain the [MIME type of the file](https://en.wikipedia.org/wiki/Media_type)
* `tag` as return type creates an image tag as string for the DOM that contain the image. This is applicable for filetype `image_thumb`.

### Image Thumb
The loader type `image_thumb` is appropriate for loading thumbnail images and return an image tag with the thumbnail size that can be appended to the DOM. Append the image tag to DOM uses the returned a string for the tag to append to the `innerHTML` of a DIV element (see [Demos Examples](https://niehausbert.gitlab.io/loadfile4dom)).

For the following example we assume that the following `div` element with the id `outlist` is located somewhere in the document body of the DOM (Document Object Model) of the browser document (i.e. loaded HTML page).
```html
<div id="outlist"></div>
```
The following Loader of the type `image_thumb`. The default image size of the thumbnail is defined by `file2image.width = 200` to a width of 200 pixel.
```javascript
//--- Create a LoadFile4DOM instance ---
// you need one instance for all loaders
var lf4d = new LoadFile4DOM();
var options = {
  "debug": false // if true, it will show the hidden <input type="file" ...> loaders in DOM
};
lf4d.init(document,options);
//-----------------------------------------------
//----- Create a new Loader "file2image" --------
//-----------------------------------------------
var file2image = lf4d.get_loader_options("addfile2image","imagethumb");
file2image.returntype = "tag";
file2image.width = 200;
// Define what to do with the loaded data
file2image.onload = function (data,err) {
  if (err) {
    // do something on error, err contains error message
    console.error(err);
  } else {
    // do something with the file content in data e.g. store  in a HTML textarea (e.g. <textarea id="mytextarea" ...>
    console.log("CALL: file2image.onload()");
    var vNode = document.getElementById("outlist");
    if (vNode) {
      vNode.innerHTML = vNode.innerHTML + "<br>" + data.tag + " ";
    } else {
      console.error("ERROR: DOM Element 'outlist' does not exist!");
    }

  }
};
// create the load dialog 'file2image'
lf4d.create_load_dialog(file2image);
```

### Format of the Returned Filehash
The `data` hash contains the following properties:
```javascript
data = {
  "name": "myimage.png",
  "file": "uASo3hSODBFl9fsdf...",
  "mime_type": "image/png",
  "tag": "<img src='....' width='200'>"
};
```
The `data.file` attribute can be used to store the images into ZIP. The main property to display the image is the `data.tag` attribute.   
* The property `data.name` contains the filename of the loaded file if the browser provides the filename (without path) of the loaded file.
* The property `data.file` contains the base64 encoded content of the image
* The property `data.mime_type` contains the [MIME](https://en.wikipedia.org/wiki/Media_type) type of the image.
* The property `data.tag` contains the HTML tag of the thumbnail image.

### Load Images
The loader of type `image` create an `new Image()` object and populates the attributes `width`, `height` (see [Demos Examples](https://niehausbert.gitlab.io/loadfile4dom)).

```javascript
img = new Image();
// populate i...

data = {
  "name": "myimage1.png",
  "file": "base64,uASo3hSODBFl9fsdf...",,
  "mime_type": "image/png",
  "img": "<img src='....' width='640'>"
};
```

### Load Files into JSON/Javascript
If you want to create digital product that is dependent on binary data, you can check the example [Load Files into JSON](https://niehausbert.gitlab.io/loadfile4dom/files2jslib.html). The [Demo](https://niehausbert.gitlab.io/loadfile4dom/files2jslib.html) creates a JSON file or Javascript file with all the loaded files the filenames and the MIME types.

E.g. if you want to create a LibreOffice document and populate the content of the generated content of the WebApp then you need a ZIP file of the Office document in which the file `content.xml` is replaced. Due to security limitations the browser cannot access binary content from the filesystem without permission (standard application on your operating system have permissions to write to the filesystem). By storing only required files in a JSON file or Javascript files an arbitrary access to the filesystem is still not available (good for privacy) and only the binary files need for the WebApp are stored in a JSON or a Javascript library.

The following JSON can be created with the [Load to JSON Demo](https://niehausbert.gitlab.io/loadfile4dom/files2jslib.html).  To create a [JSON with an array of files](https://niehausbert.gitlab.io/loadfile4dom/files2json.html) the resulting JSON could look like this.
All file have a MIME-type and a file name for the file. This is helpful for saving file from the WebApp by application of the library `filesaver.js`. Even binary files can be stored in this JSON file by base64 encoding. This assures that no binary data gets lost, because every byte of the binary data is encode in two characters. Finally the binary data is represented by `base64` encoded string, which consumes more memory but can be summitted and stored in data structures that are designed for strings (see [Demos Examples](https://niehausbert.gitlab.io/loadfile4dom)).

The results of the demo is e.g. the following JSON for 2 added files:
* the first file is a LibreOffice-ODT document `my_office_doc.odt`, which is in fact a ZIP-file with a special file and folder structure, that can be handled and modified with `JSZip`. The binary data was `base64` encoded.
* the second file is a standard text file with a new line `\n` and tab character `\t`. The text file is not encoded in `base64`, so that the file content can be used directly in the WebApp resp. DOM tree, e.g. by storing the content in a HTML textarea for further editing by the user of the WebApp.

```json
[
    {
        "name": "my_office_doc.odt",
        "file": "bW96THo0MAAGDwAA8....",
        "mime_type": "application/vnd.oasis.opendocument.text"
    },
    {
        "name": "my_comments.txt",
        "file": "this are \t my comment\nloaded from a file",
        "mime_type": "text/plain"
    }
]
```
If you want to store the JSON listed above as a Javascript library and load the data in the main HTML document e.g. `index.html`, you can add the following lines in `index.html`.
```html
<script>
   var vDataJSON = {
     "files" : null
   };
</script>
<script src="myfiles.js"></script>
```
In the library `myfiles.js` is just a slightly modified JSON file, that looks like this.
```javascript
// this is a content of 'myfiles.js'
var  vDataJSON.files = [
    {
        "name": "my_office_doc.odt",
        "file": "bW96THo0MAAGDwAA8....",
        "mime_type": "application/vnd.oasis.opendocument.text"
    },
    {
        "name": "my_comments.txt",
        "file": "this are \t my comment\nloaded from a file",
        "mime_type": "text/plain"
    }
]
```
**Remark:** Please keep in mind, that the content of file attribute `file` for the LibreOffice document is actually a very long string. The displayed content `bW96THo0MAAGDwAA8....` in this tutorial is not a real ODT-file. To create usable Javascript libraries with stored binary and text files use the demo WebApp (see [AppLSAC](https://en.wikiversity.org/wiki/WebApps_with_LocalStorage_and_AppCache)).

### Load LibreOffice Files in WebApp
Assume we store LibreOffice file `libreoffice_template.odt` in a JSON and load the JSON data as library in WebApp. The stored ODT `libreoffice_template.odt` has the MIME type `application/vnd.oasis.opendocument.text` but it is in fact a ZIP file. So creating a LibreOffice file with a WebApp can use a stored ZIP file as template and add user defined content from an editor to the LibreOffice file `my_office_doc.odt`, add images to the document by using the stored  just needs `my_office_doc.odt` as template for the layout of generated LibreOffice document in the WebApp. `JSZip` can be used to process `libreoffice_template.odt` and replace the file `content.xml` in the ZIP.

```javascript
zip.file("content.xml", my_new_content);
```

When you upload files to a JSON the

### ZIP-Files
Saving binary data into a zip-file with `JSZip` the first conclusion is to use
```javascript
zip.file("myimage.png", imgData); // NOT WORKING
```
where `imgData` is a `base64` encoded string. `JSZip` reads `imgData` as string and this implies that the file get corrupted. It is necessary to provide an option to `JSZip` that you want to save an (unicode) string. The example above will not work, because `imgData` is a binary and not a textual content. To avoid that the `zip`-file receives a corrupted content, it is necessary to pass the binary option to the zip handler (see [Demos Examples](https://niehausbert.gitlab.io/loadfile4dom)).

```javascript
zip.file("myimage.png", imgData, {base64: true})
```
See [ZIP-Example](https://niehausbert.gitlab.io/loadfile4dom/upload2zip.html)



<!-- JSON-schema `docs/schema` and the JSON data in the folder `docs/db/` to the schema for your requirements. If you want to create your own JSON schema use the [JSON2Schema tool](https://niebert.github.io/JSON2Schema).

-->

<!-- END:   src/readme/usage.md -->
## Scan Files in `docs/` Folder
The folder `docs/` contains demo HTML files, that show the application of `LoadFile4DOM` in the library `loadfile4dom.js`.

### Create `docs/index.html` for Demos as HTML
The shell script scans all demo HTML files in the folder `docs/` and creates the `index.html`. The script `

### Create `src/readme/demos.md` for Demos in Markdown
The script runs in `bash` shell for Linux and OSX. On OSX there exists a non-GNU compatible `sed` command. For compatible install `gsed` with `brew install gnu-sed` and adapt the `sed` call with the variable `sed` on GNU Linux and to `gsed` on OSX. Adapt following line according to your operating system:
```bash
### GNU Linux
SED_CMD="sed"
### OSX
SED_CMD="gsed"
```
**Remark:** Call if `gsed` on the command line in OSX. If `gsed` is not installed, use [Homebrew](https://brew.sh/) https://brew.sh/ to install the GNU compatible `gsed` with `brew install gnu-sed`.
## Wikiversity
This piece of software was created on GitLab as support material for the learning resource about privacy-friendly webbased applications `AppLSAC`](https://en.wikiversity.org/wiki/AppLSAC) on Wikiversity. An `AppLSAC` run completely in the browser without the need to submit any user generated data to a server. This package `LoadFile4DOM` is designed to learn about the first step:
* **(Load)** Load File into a browser for processing with an HTML5-WebApp (AppLSAC-1 or AppLSAC-2). The library `LoadFile4DOM` serves to cover the loading feature.
* **(Process)** Processing data can be done with any Javascript-libraries of your choice that can perform its task without submission of user generated data to a remote server. `HandleBars4Code` processes a JSON as input (UML for Javascript) to generate the JavaScript library or the `README.md` documentation for a package.
* **(Save)** If users want to save the processed results, it is recommended to look at the [FileSaver.js](https://github.com/eligrey/FileSaver.js) library provided by Eli Grey.
<!-- BEGIN: src/readme/build_process.md -->

## Build Process of `npm run build`
The build process is called by `npm run build` which in turn call `build.js`. If you want to call the build process of `build.js` separately just call `build.js` with `node build.js` from the shell/console.

The templates for building the output are stored in the folder `src/`.

After the build process the `README.md` is generated and if you want to have the table of contents in the file for the concatenation of  files in `src/readme/` listed in `files4build.js` then you must run the DocToc generator for `README.md` by `doctoc README.md` from the shell to update the table of contents in `README.md`.

### Define Filename for build in `package.json`
In `package.json` defines the filename for the automated build for
* `README.md` for readme for the repository (parts in `src/readme`),
* `index.html` for the web demo (parts in `src/html`),
* `main.css` for the style sheet (part in `src/css`) and
* `./src/main.js` is generated from the parts in `src/libs`
the sources in `src/`.
To specify these filenames add the following `build` section to the `package.json`:
```javascript
"build": {
  "readme": "README.md",
  "html": "docs/index.html",
  "css": "docs/css/main.css"
}
```
If you want to edit the generated file check the files that are selected for including into the generated files (see `files4build.js`) and set the files to a preliminary build name (e.g. like `index_build.html` instead of `index.html` to compare generated file `index_build.html` with the older version `index.html` for debugging

### Compress after Build
After building (concat the file parts) and replacement of package variables (e.g. see [`build4code`](https://www.npmjs.com/package/build4code) like  `loadfile4dom` for package name) in the generated documents the module is browserified by the command
```javascript
uglifyjs dist/loadfile4dom.js --compress -o dist/loadfile4dom.min.js
```
This command is called after `build.js` and the final step of the build process is the [`doctoc`](https://www.npmjs.com/package/doctoc) call to update the table of contents in the `README.md`. All steps of the `npm run build` command are defined in the `script` section of the `package.json` file.
<!-- END:   src/readme/build_process.md -->

## API for Javascript Class: `LoadFile4DOM`
The complete documentation of the API can be found in the  [GitLab-Wiki](https://gitlab.com/niehausbert/loadfile4dom/wikis/API-Documentation).

### Diagram

|  LoadFile4DOM               |
| ---------------------------- |
|  + `aDocNaNDocument`<br> + `aOptionsNaNHash`<br> + `aFileLoaderNaNHash`<br> + `aLoadFileHolderNaNObject`<br> + `defaults_options`<br> + `type2accept`<br> + `defaults_loader`<br> + `aLoaderCount` |
|  + `init(pDoc:Document,pOptions:Hash)`<br> + `getTimeStamp():Integer`<br> + `create_input_tags()`<br> + `create()`<br> + `get_holder():Object`<br> + `create_load_dialog(pOptions: )`<br> + `create_holder()`<br> + `open_dialog(pID:String)`<br> + `set_defaults(options: , defaults: )`<br> + `get_loader_options(pID: ,pFileType: ,pOptions: ):Hash`<br> + `get_input_attributes(pID: ,pFileType: )`<br> + `error_file_type(pLoader: ,pFileToLoad: )`<br> + `handle_text(pLoader: ,pFileReader: ,pFileToLoad: )`<br> + `handle_json(pLoader: ,pFileReader: ,pFileToLoad: )`<br> + `handle_image(pLoader: ,pFileReader: ,pFileToLoad: )`<br> + `handle_image_thumb(pLoader: ,pFileReader: ,pFileToLoad: )`<br> + `handle_data(pLoader: ,pFileReader: ,pFileToLoad: )`<br> + `handle_audio(pLoader: ,pFileReader: ,pFileToLoad: )`<br> + `handle_video(pLoader: ,pFileReader: ,pFileToLoad: )`<br> + `handle_file_type(pLoader: ,pFileReader: ,pFileToLoad: )`<br> + `handle_single_file(pLoader: )`<br> + `handle_multiple_files(pLoader: )`<br> + `handle_file(pID: )`<br> + `log(pMessage: )`<br> + `set_onload()`    |


### Attributes: `LoadFile4DOM`
For class `LoadFile4DOM` the following attributes are defined:

#### Attribute `aDoc : Document`
This attribute stores a reference to the document object of the browser. Reference provided with the init-method
* Visibility: `public`
* Class: `Document`
* Default Init: `null` set by `my_instance.aDoc = null;`
* Access of attribute in the code of methods by `this.aDoc = null;`

#### Attribute `aOptions : Hash`
This hash stores the options of the init method - e.g. "id4loadfile" as DIV container for the input elements in the DOM that holds all created file loaders i.e. holding the input-file-tags for load a JSON file
* Visibility: `public`
* Class: `Hash`
* Default Init: `null` set by `my_instance.aOptions = null;`
* Access of attribute in the code of methods by `this.aOptions = null;`

#### Attribute `aFileLoader : Hash`
This attribute stores the number of file loaders created with instance
* Visibility: `public`
* Class: `Hash`
* Default Init: `{}` set by `my_instance.aFileLoader = {};`
* Access of attribute in the code of methods by `this.aFileLoader = {};`

#### Attribute `aLoadFileHolder : Object`
This attribute stores the reference to the DIV node of the file holder node in the DOM that is created by `this.create_holder()`
* Visibility: `public`
* Class: `Object`
* Default Init: `{
    "id": "holder4loadfile",
    "dom": null,
    "timeout": 0,
    "var4dom": "undef_call_var",
    "debug": false
}` set by `my_instance.aLoadFileHolder = {
    "id": "holder4loadfile",
    "dom": null,
    "timeout": 0,
    "var4dom": "undef_call_var",
    "debug": false
};`
* Access of attribute in the code of methods by
```javascript
this.aLoadFileHolder = {
    "id": "holder4loadfile",
    "dom": null,
    "timeout": 0,
    "var4dom": "undef_call_var",
    "debug": false
};
```

#### Attribute `defaults_options :  `
the attribute stores the default options for LoadFile4DOM
* Visibility: `public`
* Class: ` `
* Default Init:
```javascript
{
    "id": "loadfile_holder_div",
    "dom": null,
    "setonload": false,
    "timeout": 1000,
    "debug": false
}
```
set by
```javascript
my_instance.defaults_options = {
    "id": "loadfile_holder_div",
    "dom": null,
    "setonload": false,
    "timeout": 1000,
    "debug": false
};
```
* Access of attribute in the code of methods by
```javascript
this.defaults_options = {
    "id": "loadfile_holder_div",
    "dom": null,
    "setonload": false,
    "timeout": 1000,
    "debug": false
};
```

#### Attribute `type2accept :  Hash`
the attribute maps the type to the accept tag of files of the input-file-tag
* Visibility: `public`
* Class: `Hash`
* Default Init:
```javascript
{
    "all": "*",
    "audio": "audio/*",
    "audiourl": "text/*",
    "data": "*",
    "image": "image/*",
    "imagethumb": "image/*",
    "json": "application/json",
    "text": "text/*",
    "texturl": "text/*",
    "video": "video/*",
    "videourl": "text/*",
    "url": "text/*",
    "zip": "application/zip"
}
```
set by
```javascript
my_instance.type2accept = {
    "all": "*",
    "audio": "audio/*",
    "audiourl": "text/*",
    "data": "*",
    "image": "image/*",
    "imagethumb": "image/*",
    "json": "application/json",
    "text": "text/*",
    "texturl": "text/*",
    "video": "video/*",
    "videourl": "text/*",
    "url": "text/*",
    "zip": "application/zip"
};
```
* Access of attribute in the code of methods by
```javascript
this.type2accept = {
    "all": "*",
    "audio": "audio/*",
    "audiourl": "text/*",
    "data": "*",
    "image": "image/*",
    "imagethumb": "image/*",
    "json": "application/json",
    "text": "text/*",
    "texturl": "text/*",
    "video": "video/*",
    "videourl": "text/*",
    "url": "text/*",
    "zip": "application/zip"
};
```

#### Attribute `defaults_loader :  `
the attribute stores the default loader tags if not options are provided
* Visibility: `public`
* Class: `Hash`
* Default Init:
```javascript
{
    "filetype": "text",
    "id": "loader123456789",
    "name": "defaultloader",
    "value": "Dialog Loader Button",
    "accept": "text/*",
    "onchange": "console.log('open dialog click on 'defaultloader')",
    "multiple": true
}
```
set by
```javascript
my_instance.defaults_loader = {
    "filetype": "text",
    "id": "loader123456789",
    "name": "defaultloader",
    "value": "Dialog Loader Button",
    "accept": "text/*",
    "onchange": "console.log('open dialog click on 'defaultloader')",
    "multiple": true
};
```
* Access of attribute in the code of methods by
```javascript
this.defaults_loader = {
    "filetype": "text",
    "id": "loader123456789",
    "name": "defaultloader",
    "value": "Dialog Loader Button",
    "accept": "text/*",
    "onchange": "console.log('open dialog click on 'defaultloader')",
    "multiple": true
};
```

#### Attribute `aLoaderCount :  Integer`
the attribute stores the number of created loaders to create unique loader IDs in the DOM together with the method getTimeStamp()
* Visibility: `public`
* Class: `Integer`
* Default Init: `0` set by `my_instance.aLoaderCount = 0;`
* Access of attribute in the code of methods by `this.aLoaderCount = 0;`
## Build and Compress with Browserify, Watchify, UglifyJS
The NodeJS modules can use `require()`-command. Browsers cannot execute the `require()`-command and other node specific programming features.
* `Browserify` loads the file `./src/main.js` as input file and resolves e.g. the `require()`-command and creates an output file in `dist/loadfile4dom.js`
* `Watchify` observes any changes in the source files in `src/` and starts on the event of changes the build process of the file `./src/main.js` as input file and creates an output file in `dist/loadfile4dom.js`.
* `UglifyJS` compresses the code in `dist` and takes the file `dist/loadfile4dom.js` and generates the compressed library in `dist/loadfile4dom.min.js`. The same is applied for `docs/js/loadfile4dom.js` and the output is `docs/js/loadfile4dom.min.js`. The compression of the source code can be perform without a total build by `npm run compress`.
* The main browserify command creates a standalone library that can be used in the browser and it assign `LoadFile4DOM` to the `window` object by
```shell
  browserify src/main.js --standalone window > dist/loadfile4dom.js
```

### Browserify and Watchify
Browserify and Watchify are used in this repository to control the WebApp-javascript development with the required Javascript libraries installed with [NPM Node.js](https://docs.npmjs.com/getting-started/installing-node) and similar framework world that greatly improve your javascript workflow: Using them, you no longer need to micro-manage your script tags but instead you just declare the libraries each of your client-side modules is using - or you can even create your own reusable modules! Also, installing (or updating) javascript libraries is as easy as running a single command!
* [Additional Information about Browserify and Watchify on GitHub](https://spapas.github.io/2015/05/27/using-browserify-watchify/)
* [Youtube Video about Browserify and Watchify by Kyle Robinson Young 2015/04/16](https://www.youtube.com/watch?v=CTAa8IcQh1U)
In this repository Browserify and Watchify are used for javascript code development with [NPM Node.js](https://docs.npmjs.com/getting-started/installing-node).

### Global Installation of Browserify, Watchify, UglifyJS and DocToc
Requirement: [NPM](https://docs.npmjs.com/getting-started/installing-node) is intalled. Now call for global installation of Browserfy, Watchify, UglifyJS and DocToc by:

`npm install -g browserify watchify uglify-js doctoc`

This is recommended because your will not install Browserfy, Watchify and UglifyJS for all your repositories separately.
* ***Browserfy*** converts `node_modules` in a single library, that can be imported in WebApp. Browserify resolves dependencies and included the required libraries into the bundled javascript code.
* ***Watchify*** watches changes in the source code and runs the build process whenever it detects changes in the your source code.
* ***UglifyJS*** compresses the source code of `dist/class_editor_uml.js` into ```class_editor_uml.min.js``` to reduce download time and WebApp performance during load.
* ***DocToc*** is used to create a helpful table of contents in the README (see [DocToc-Installation]https://github.com/thlorenz/doctoc#installation) for further details on [NPM DocToc](https://www.npmjs.com/package/doctoc) ). Run `doctoc README.md` for updating the table of contents.
* ***jsLint*** is used to check the Javascript code, quality of code can be improved by application of jsLint

### Package Installation of Browserify and Watchify - Alternative
If your prefer that  browserify and watchify is installed with your `npm install` command, save these to modules to your dev-dependecies in your `package.json` by calling

* (Install Browsersify) `npm install browserify --save-dev`
* (Install Watchify) `npm install watchify --save-dev`
* (Install UglifyJS) `npm install uglify-js --save-dev`
* (Install DocToc) `npm install doctoc -g`
* (Install jshint) `npm install jslint -g`

The difference between `--save` and `--save-dev` is, that development dependencies are installed with `npm install` because they are required for the development process of the code but they are not added to the generated Javascript-bundle that are used in the WebApp ClassEditorUML. The `--save-dev` commands for `browserify` and `watchify` will install the two modules with all the the dependencies in `node_modules` and add the dev-dependencies to your `package.json`.
```json
"devDependencies": {
  "browserify": "^14.5.0",
  "watchify": "^3.9.0",
  "uglify-js": "^2.6.2",
  "doctoc":"^1.3.0",
  "lint": "^1.1.2"  
}
```
In the current repository `Browserfy` and `Watchify` are expected to be installed globally, because the `package.json` does not contain the dev-dependencies mentioned above.

### Start Watching the Files with Watchify
Watchify will trigger the `npm run build` process if files were change due to alteration of code. To start watching the files, run the npm-watch script by `npm run watch`, which is defined in `package.json`

### Source JS file and development bundle output
The main JS source file for the build process is `src/main.js`. The output library (resp. output file of build process) is stored in distrubtion library for browser based web-development in `dist/loadfile4dom.js`. Compressed code is generated with `UglifyJS`. It takes the `dist/loadfile4dom.js` as input file and creates the compressed file `dist/loadfile4dom.min.js`.
The compression of `dist/loadfile4dom.js` into `dist/loadfile4dom.min.js` uses `uglify-js` module and can be started by

  `npm run compress`

## Acknowledgement
Special thanks to the following individual developers and teams of OpenSource JavaScript projects:
* [HandleBars](http://handlebarsjs.com/) the code generation in Javascript was developed by Yehuda Katz.
* [JSON-Editor](https://github.com/jdorn/json-editor) by Jeremy Dorn. The JSON Editor takes a JSON Schema and uses it to generate an HTML form. The JSON-Editor is partially used to edit JSON file of the [ClassEditorUML](https://niebert.github.io/ClassEditorUML) `UML` for Javascript.
* Developer [Mihai Bazon](http://lisperator.net/) create UglifyJS, a great tool to handle and parse Javascript Code and minify the Javascript code (see [Source Code of UglifyJS](https://github.com/mishoo/UglifyJS2)).
* The wrapper for UglifyJS is written [Dan Wolff](http://danwolff.se/). His UglifyJS-Online example is used to minify/compress the exported Javascript code of generated JS Classes (For Online Example of the [UglifyJS-Wrapper](https://skalman.github.io/UglifyJS-online/) see source code on https://github.com/Skalman/UglifyJS-online for the Online-Version of the Wrapper.
* Developers of ACE Code Editor https://ace.c9.io (Javascript Editing uses the Editor in iFrames)
* [FileSaver.js](https://github.com/eligrey/FileSaver.js) Developer Eli Grey provided the `FileSaver.js` that is used to store created `JSCC` files to the local filesystem. `JSCC` uses the same mechanism of browsers, that allows a `Save as...` in the context menu of a web pages or image. So not uncontrolled write access to your file system is implemented, because users have to select the locations in which the user whats to store the file (e.g. JSON, Javascript or HTML).
* [JointJS](https://github.com/clientIO/joint) JointJS is a JavaScript diagramming library. It can be used to create either static diagrams. JointJS is used in this project to create UML-diagrams, that are interactive diagramming in conjunction and application builder in Javascript.
* [Inheritage for JavaScript with protoypes](http://phrogz.net/js/classes/OOPinJS2.html) by Gavin Kistner
* [3 ways to define a JavaScript class](https://www.phpied.com/3-ways-to-define-a-javascript-class/) by Stoyan Stefanov
* [JQuery](https://jqueryui.com) is used for the theme and standard operations in the Document Object Model (DOM) of HTML-pages. The [JQuery-Themeroller](https://jqueryui.com/themeroller/) was used to create a JQuery theme for JSCC.

## Libraries required for  `LoadFile4DOM`
The following libraries are necessary for `loadfile4dom.js`:


## Libraries for Building and Developement
The following libraries are necessary for building the `loadfile4dom`.
These libraries are not included in `loadfile4dom.js`, but e.g. are required in `build.js`.
* Lib: `build4code` Version: `^0.3.13`
* Lib: `concat-files` Version: `^0.1.1`
* Lib: `doctoc` Version: `^1.3.0`
* Lib: `jsdom` Version: `^13.1.0`
* Lib: `shelljs` Version: `^0.8.3`
* Lib: `uglify-js` Version: `^3.6.0`

## NPM Library Information
* Exported Module Variable: `LoadFile4DOM`
* Package:  `loadfile4dom`
* Version:  `1.2.19`   (last build 2021/10/14 11:32:13)
* Homepage: `https://gitlab.com/niehausbert/loadfile4dom#readme`
* License:  MIT
* Date:     2021/10/14 11:32:13
* Require Module with:
```javascript
    const vLoadFile4DOM = require('loadfile4dom');
```
* JSHint: installation can be performed with `npm install jshint -g`
<!-- BEGIN: src/readme/tail.md -->
<!-- END:   src/readme/tail.md -->
