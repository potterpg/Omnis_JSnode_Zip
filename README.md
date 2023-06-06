# Omnis_JSnode_Zip
## Omnis Studio 10.22 Demo interface to the JS worker using Node jszip functions.

## JavaScript Worker Object
The JavaScript Worker Object allows you to execute JavaScript methods inside node.js by making the request in Omnis code by calling a Worker Object method, and receiving the results via a worker callback.

### Adding ZIP support
To add support for ZIP files. To do this, install the node.js jszip module by running the npm command in the jsworker folder:

```
npm i jszip
(the npm command is installed with node.js, available on the web)
```

Edit omnis_modules.js by adding an entry to the 'moduleMap' object for the zip module (or from Studio 11 it should be loaded automatically since it is in its own folder ‘omnis_zip’):
```
const moduleMap = {
zip: require('./omnis_zip.js'),
... // Other modules
};
```
Once the above has been installed, then the demo library will work for you.

This library is demo bringing all the methodMapClass function calls specified within omnis_zip.js into an Omnis object.<br>
This is referring to version '28-Mar-19	jmg_unmarked'
* $CreateZipObject - Creates a memory only zip object (newZip)
* $AddFiles - Add a file or files to the ZIP object (addFiles)
* $AddFolder - Add a folder to the ZIP object (addFolder)<br>
 Folder paths are relative to the top of the ZIP file, so start with a name<br>
 This must be followed by additional folder names.  Intermediate folders which do not exist are also created
* $SaveZipFile - Saves the contents of the zip object to a file (saveZip)
* $LoadZipFile - Loads a zip file into a zip object (loadZip)<br>
 This also returns a list of the contents of the zip file.
* $ExtractAFile - Extracts a specific file out of the loaded zip object (extractFile)


