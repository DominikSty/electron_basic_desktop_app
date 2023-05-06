# Create basic Electron desktop application tutorial

First you need to download and install NODE.JS. To check the correct installation you need to call the appropriate commands in the console: ```node -v``` and ```npm -v```.

## Creating a project
Create a project folder: ```mkdir my_app && cd my_app```

Initialize the project: ```npm init```

Installing the electron package: ```npm install electron --save-dev```

When you create the package. json project files, it should look like this:
```
{
  "name": "my_app",
  "version": "1.0.0",
  "description": "...",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "author": "autor",
  "license": "ISC",
  "devDependencies": {
    "electron": "^24.2.0"
  }
}
```
Remember to add the line: ```"start": "electron .",``` in:
```
"scripts": {
   "start": "electron .",
   "test": "echo \"Error: no test specified\" && exit 1"
 },
```
Then create the application files:
- ```index.js``` (sample file content):
```
const { app, BrowserWindow } = require('electron')
function createWindow () {
  let win = new BrowserWindow({ width: 800, height: 600 })
  win.setMenu(null)
  win.loadFile('index.html')
}
app.on('ready', createWindow)
```
- ```index.html``` (sample file content):
```
<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8">
    <title>Title</title>
  </head>
  <body>
    <h1>Hello World!</h1>
  </body>
</html>
```

## Launch of the project
The project is started from the command line with the command: ```npm run start```

## Creating an EXE Application
First install the package in the project folder: ```npm install -g electron-packager```

To compile the project, use the command: ```electron-packager . my_app --platform=win32 --arch=x64 --icon=icon.ico --overwrite```

where:

```.``` means the current directory where the project is located

```my_app``` is the name of the folder where the application files will be located

```--platform=win32``` means we want to build an executable for Windows

```--arch=x64``` means we want to build a file for 64-bit architecture

```--icon=icon.ico``` indicates that we want to use an icon file named icon. ico

```--overwrite``` means that if the my-app folder already exists, its contents will be overwritten.
