# psshiftjshigearwebwrkernt
##2 The Basics
###2 Messages 
copy vs transfer
```
let ab = new ArrayBuffer(32);
let worker = new Worker('worker.js');


//copy
worker.postMessage(ab);
console.log(ab.byteLength); //32

//transfer
worker.postMessage(ab,[ab]);
console.log(ab.byteLength); //0
```  
can only transfer ArrayBuffers and MessagePorts  


###6 Demo: Importing Scripts
index.html
```
let worker = new Worker('worker.js');
```
helper.js
```
console.log('test');
```
worker.js
```
importScripts('hepler.js');
console.log('this will print after the helper.js loads');
```
