- install nodmon 
```sh
	  npm install -D nodemon
```
- setup nodemon in pkg.json {"dev": "nodemon index.js",} in script feild
```json
{
  "name": "server-simple",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "type": "module",
  "scripts": {
    "dev": "nodemon index.js",
    "start": "node index.js"
  },
  "author": "",
  "license": "ISC",
  "devDependencies": {
  "nodemon": "^3.1.0"
  }
}
```
- To run nodemon 
```sh
	npm run dev
```
```sh
to use in other folders

	npm install nodemon --save-dev
```
