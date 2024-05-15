
Express est un library pour node.js
```sh 
	Install Express.js
	npm install express
```
- Pour installer express il faut faire un initialisation du dossier {npm init}

## Method Get
```js
server.get("/api/todo", (req, res) => {
  const dataURL = req.query;
  if (!dataURL.id) {
    return res.status(400).json({ err: "id oubligatoire" });
  }
  fs.readFile("./source/data/todos.json", (err, contenu) => {
    if (err) {
      return res
        .status(500)
        .json({ err: "un problème est survenue sur le server" });
    }
    const dataString = contenu.toString();
    const data = JSON.parse(dataString);
    const todoData = data.todos.find((todo) => {
      return todo.id == dataURL.id;
    });
    if (!todoData) {
      return res.status(404).json({ err: "Tache non trouvée" });
    }
    return res.json(todoData);
  });
});
```

## Method Delete
```js
FILTER
	server.delete("/api/todo", (req, rep) => {
    const dataURL = req.query;
    if (!dataURL.id) {
      return rep.status(500).json({ error: "ID obligatoire" });
    }
    
    const contenu = fs.readFileSync("./source/data/todos.json");
    const contenuString = contenu.toString();
    const data = JSON.parse(contenuString);
    data.todos = data.todos.filter((todo) => todo.id != dataURL.id);
    fs.writeFileSync("./source/data/todos.json", JSON.stringify(data));
    return rep.json({message:"Tache suprimmée"})
  });
```

## Method Post
```js
server.post("/api/todos", (req, rep) => {
  const data = req.body;
  if (!data.title || !data.date) {
    return rep
      .status(400)
      .json({ error: "Titre et date obligatoire" });
  }

  const dataTodos = fs.readFileSync("./src/data/todos.json");
  const todosObject = JSON.parse(dataTodos.toString());
  todosObject.todos.push({
    id: Math.floor(Math.random() * 1000),
    title: req.body.title,
    date: req.body.date,
  });

  fs.writeFileSync("./src/data/todos.json",
    JSON.stringify(todosObject)
  );
  return rep.json({
    message:"Tache ajouté"
  });
});
```
## MiddleWare 


- Creatinng random id's
```JS
	import crypto from "crypto";
	id: crypto.randomUUID()
```

# CRUD
				CRUD == CREATE     READ     UPDATE       DELETE
						   ^         ^         ^            ^
Méthode HTTP de CRUD         Post               GET            PUT                DELETE


