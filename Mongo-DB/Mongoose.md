## Installation Mongoose
Pour **utiliser Mongoose** dans une application Node.js, il faut **installer** le module Mongoose à l'aide de `npm`.

- **[Site web de mongoose**](https://mongoosejs.com/)  

- **[Package NPM mongoose**](https://www.npmjs.com/package/mongoose)  

- [**GitHub de mongoose**](https://github.com/Automattic/mongoose)  

Dans un terminal, **exécutez** la commande suivante pour **installer** Mongoose :
```bash
npm install mongoose
```

## Connect Mongoose to file

```js
	import mongoose from "moongoose"
	const MONGODB_URI = "mongodb://127.0.0.1:27017/mabdd";
```

```js
	app.listen(PORT, function(){
    console.log(`le server est lancée sur le port ${PORT}`);
    console.log(`http://localhost:${PORT}/`);
   ///////-----------------------\\\\\\\
   MONGOdb
    mongoose.connect(MONGODB_URI).then(()=>{
       console.log(`Base de donnée connectée`);
    }).catch((err) =>{
       console.log(`Base de données non connectée`);
       console.log(err);
    })
})
```

