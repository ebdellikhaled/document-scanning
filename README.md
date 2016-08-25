# Document Scanning for Windows, Linux and macOS
The demo shows how to create a simple online document scanning app for Windows, Linux and macOS with Dynamic Web TWAIN and JavaScript.

## Getting Started
1. Download the project and get into the project folder:

    ```
    git clone https://github.com/yushulx/document-scanning.git
    cd document-scanning
    ```
2. Install **express** and **Dynamic Web TWAIN**:

    ```
    npm install
    ```
3. Run the project:

    ```
    node server.js
    ```
4. Edit **node_modules/dwt/dist/dynamsoft.webtwain.config.js**:
 
    ```
    Dynamsoft.WebTwainEnv.ResourcesPath = 'node_modules/dwt/dist/';
    ```
5. Open **http://localhost:2016/helloworld.html** in **Chrome**.
6. Click the popup dialog to install scanning service for different platforms.
7. Select a scanner source and scan documents.


## Resource Path
When creating a new HTML document, you need to include following JavaScript files:

```
<script type="text/javascript" src="<Resource Directory>/dynamsoft.webtwain.initiate.js"></script>
<script type="text/javascript" src="<Resource Directory>/dynamsoft.webtwain.config.js"></script>
```
In addition, change the resource path in **node_modules/dwt/dist/dynamsoft.webtwain.config.js**:

```
Dynamsoft.WebTwainEnv.ResourcesPath = '<Resource Directory>';
```

## Code for Linux
You need to specify the driver type for Linux before getting the source count.

```
if (DWObject) {
    DWObject.ImageCaptureDriverType = 3;
    var count = DWObject.SourceCount;
    for (var i = 0; i < count; i++)
        document.getElementById("source").options.add(new Option(DWObject.GetSourceNameItems(i), i)); // Get Data Source names from Data Source Manager and put them in a drop-down box
}
```
