- Applications web côté serveur
-  Créer des API
- Gérer les données

Node.js est un moteur qui interprete js en c++ pour communiquer avec la machine

pour créer un package.json automatique par Node
```bash
	npm init
```

exporter un objet dans le Node
```js
	function add(a, b) {
    return a + b
	}
	function mul(a, b) {
	    return a * b
	}
	function div(a, b) {
	    return a / b
	}
	function sub(a, b) {
	    return a - b
	}
	module.exports = {
	    add, mul, div, sub,
	}
```

importer un objet 
```js
	const {add , mul, div , sub} = require('./math')
```


pour utiliser 'import from' et 'export 'on ajoute le "type" : "module" dans le pkg.json
```json
{
  "name": "node",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "type": "module",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
},
  "author": "nano",
  "license": "ISC"
}
```
## Import
```js
	import {add} from './math.js'
```
## Export
```js
	export function add(a, b) {
    return a + b
}
```


## ReadFile
```js
	import fs from 'fs'

	fs.readFile("./user.txt",(err, contenu)=>{
    if(err){
        console.log(err);
    }else{
        console.log(contenu.toString());
    }
    })
```

## ReadLine
```js
	import readline from 'readline'

	const inter = readline.createInterface({
    input: process.stdin,
    output: process.stdout,
});
inter.question("what's your name?", (nom)=> {
    console.log(nom);
    inter.close();
})
```
![[Pasted image 20240513110723.png]]

## WriteFile
- creates  file using a javaScript "script"
```js
	import fs from 'fs'
	import readline from 'readline'
	
	const inter = readline.createInterface({
    input: process.stdin,
    output: process.stdout,
	});
	
inter.question("what's your project name?", (fileName)=> {

	fs.writeFile("./" + fileName, '', (err)=>{
	
	   if(err){
	        console.log("file creation abadonned");
	   }else{
	        console.log("file creation succesful");
	   }
	    inter.close();
	   })

})
```
![[Pasted image 20240513114950.png]]



## Node Server 
- On créer un dossier server 
- on intialise le dossise avec npm init
- puis on créer un fichier index.js
```js
	import http from 'http'

	const server = http.createServer((req, res)=>{
	    console.log("recu");
	    console.log(req);
	    res.end("bye")
	})
	
	server.listen(3001)

```
- on ajoute le script dans le pkg.json |                                                                            "scripts": {
    "start": "node index.js" }, 
    |
    
```json
{
  "name": "server-simple",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "type": "module",
  "scripts": {
    "start": "node index.js"
  },
  "author": "",
  "license": "ISC"
}
```


### POST AND GET 
```JS
	import http from 'http'
	
	const server = http.createServer((req, res)=>{
    if(req.url === "/posts"){
        if(req.method === "GET"){
            res.end("our products")
            return
        }
        if(req.method === "POST"){
            res.end("create articles")
        }
    }
    res.end("goodbye")
})
```

