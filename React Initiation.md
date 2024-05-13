
## install React 

- install node
- install vite

## Install vite
### Command
```bash
  npx create vite@latest
```
### Run node
```bash
  npm run dev
```

## Composant 
- Un composant est une fonction qui retourne du JSX

```JSX
function Titre(param){
	return <h1> "hello world" </h1>
}
```
### Utiliser le composant

```jsx
<div>
	<Titre/>
</div>
```
### Composant paramétré
- Un composant peut recevoir  un objet en paramètre:

#### Déclarer le composant 
```jsx
function Titre(param){
	return <h1>{param.text}</h1>
}
```
### Utiliser le composant paramétré
```jsx
<div>
	<Titre text="Hello world"/>
</div>
```

## Styliser un application React 
### Utiliser des fichier CSS

Il suffit d' importer le ficher dans un composant , par convention on l'importe 
dans App.jsx
```jsx
import './App.css'
```
### Utiliser des modules de Css
Créer un ficher qui porte dans le nom 'module.css'
impoter le ficher dans le ficher du composant 
Utiliser les classes déclarer le module directement dans l'élement HTML
```JSX
import mesClasses from "./Titre.module.css"
("./Titre.module.css" module is required in the name of the file css)
export default function Titre({children}){
	return <h1 classeName={mesClasses.titre} > {children}</h1>
}
```
### lnline style
(A utiliser avec les petit composants du style: bouton, input, titre) Le inline style, permet d'ajouter du style aux éléments JSX directement
```jsx
export default function Titre({ children }) {   return <h1 style={{color:"royalblue"}}>{children}</h1>; }
```
