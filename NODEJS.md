
# NodeJS

Tout d'abord, voici une image illustrant trois éléments clés pour comprendre NodeJS:

![image](https://github.com/user-attachments/assets/2ad8a4ba-3f05-4e84-a8d0-c50fdcd7bb6a)


## Qu'est-ce que NodeJS?

NodeJS est un projet open-source et multi-plateforme qui permet d'exécuter du code JavaScript côté serveur. Il utilise le moteur JavaScript V8 de Google Chrome pour exécuter du code JavaScript.

On dit aussi que NodeJS est un **environnement** d'exécution JavaScript côté serveur.

### Qu'est-ce qu'un environnement d'exécution?

Un environnement d'exécution est un logiciel qui fournit un environnement dans lequel un programme peut être exécuté. Cela inclut des choses comme la gestion de la mémoire, la gestion des fichiers, la gestion des entrées/sorties, etc. 

Dans le cas de JavaScript, l'environnement est ce qui va fournir les **objets** et les **fonctions** qui permettent à notre code d'intéragir avec *l'extérieur* (le navigateur, le serveur, etc).

Les différents environnements fournissent donc des fonctionnalités différentes. Par exemple, l'environnement d'exécution de NodeJS fournit des fonctionnalités pour lire et écrire des fichiers, pour créer des serveurs, etc. Alors que l'environnement d'exécution du navigateur fournit des fonctionnalités pour manipuler le DOM (La page Web), pour gérer les événements, etc.

![image-2](https://github.com/user-attachments/assets/8dda4b40-746a-454d-bb75-603506238fa2)

### Pourquoi utiliser NodeJS?

NodeJS est très populaire pour plusieurs raisons:

- **JavaScript**: NodeJS permet d'utiliser JavaScript côté serveur. Cela signifie que les développeurs peuvent utiliser le même langage de programmation pour le côté client et le côté serveur. Cela permet de réduire la complexité du code et de faciliter la maintenance.
- **Asynchrone**: NodeJS est asynchrone. Cela signifie que les opérations d'entrée/sortie (comme la lecture d'un fichier, la requête à une base de données, etc) sont non bloquantes. Cela permet de gérer un grand nombre de connexions simultanées sans utiliser beaucoup de ressources.
- **Événements**: NodeJS est basé sur un modèle d'événements. Cela signifie que les fonctions sont appelées en réponse à des événements. Cela permet de créer des applications réactives et performantes.
- **Ecosysteme**: NodeJS a un écosystème très riche. Il existe de nombreux modules et packages qui permettent de faire beaucoup de choses. Cela permet de gagner du temps et de ne pas avoir à réinventer la roue pour chaque projet.

## Exemples de programmes NodeJS

### Hello World!
Voici un exemple de programme NodeJS qui affiche "Hello World!" dans la console:

```javascript
console.log("Hello World!");
```

Pour exécuter ce programme, il suffit de créer un fichier `hello.js` avec ce code, puis d'exécuter la commande `node hello.js` dans un terminal. On obtiendra alors la sortie suivante:

```
Hello World!
```

### Utilisation du système de fichier

Voici un exemple de programme NodeJS qui lit un fichier et affiche son contenu dans la console:

```javascript
import fs from 'node:fs';

fs.readFile('file.txt', 'utf8', (err, data) => {
	if (err) {
		console.error(err);
		return;
	}
	console.log(data);
});
```

Pour exécuter ce programme, il suffit de créer un fichier `readFile.js` avec ce code, puis de créer un fichier `file.txt` avec du contenu, et enfin d'exécuter la commande `node readFile.js` dans un terminal. Le contenu du fichier `file.txt` sera alors affiché dans la console.

### Création d'un serveur HTTP

Voici un exemple de programme NodeJS qui crée un serveur HTTP et affiche "Hello World!" dans le navigateur:

```javascript
import http from 'node:http';

const server = http.createServer((req, res) => {
	res.writeHead(200, { 'Content-Type': 'text/plain' });
	res.end('Hello World!\n');
});

server.listen(3000);
```

Pour exécuter ce programme, il suffit de créer un fichier `server.js` avec ce code, puis d'exécuter la commande `node server.js` dans un terminal. Ensuite, en ouvrant un navigateur et en allant à l'adresse `http://localhost:3000`, on verra s'afficher "Hello World!".

**Note:** Cette fois-ci, le programme ne s'arrête pas tout seul. Il faut appuyer sur `Ctrl+C` dans le terminal pour l'arrêter. En effet, le serveur reste en écoute sur le port 3000 tant qu'on ne l'arrête pas.

### Note sur les adresses IP

Quand on crée un programme en réseau comme celui que nous venons de faire, celui-ci devient accessible à d'autres ordinateur sur le même réseau. Mais pour que notre ordinateur sache à avec quel autre ordinateur il doit communiquer, nous devons utiliser une **adresse IP**. Chaque appareils sur le réseau en possède une, c'est ce qui forme la base du réseau Internet.

Par exemple voici une image d'un réseau avec des ordinateurs et une imprimante. Chaque appareil à sa propre adresse unique:

![image](https://github.com/user-attachments/assets/d9327ea4-d852-48e7-8cca-d4641ef4bbc3)

Dans notre cas si nous voulons partager notre site avec quelqu'un d'autre, nous devons lui communiquer notre adresse IP. Tu peux connaitre l'adresse IP de ton ordinateur via la commande `ifconfig` dans le terminal. Le résultat de la commande est un peut fouilli, mais sur les iMacs de TUMO tu dois retrouver la catégorie `en1`:

```
...
en1: flags=8863<UP,BROADCAST,SMART,RUNNING,SIMPLEX,MULTICAST> mtu 1500
	options=400<CHANNEL_IO>
	ether 80:5f:c5:44:98:ce 
	inet6 fe80::1cb2:3002:a22d:8d22%en1 prefixlen 64 secured scopeid 0x5 
	inet 10.21.38.40 netmask 0xfffffe00 broadcast 10.21.39.255
...
```
Ce qui nous intéresse c'est l'addresse IPv4 noté à côté de `inet`, dans cet exemple notre adresse IP serait **10.21.38.40**.

## API NodeJS

NodeJS fournit de [nombreuses API](https://nodejs.org/api/index.html) pour interagir avec le système d'exploitation, le réseau, le système de fichiers, etc. Voici quelques exemples d'API couramment utilisées:

- **[fs](https://nodejs.org/api/fs.html)**: API pour interagir avec le système de fichiers.
- **[http](https://nodejs.org/api/http.html)**: API pour créer des serveurs HTTP.
- **[https](https://nodejs.org/api/https.html)**: API pour créer des serveurs HTTPS.
- **[events](https://nodejs.org/api/events.html)**: API pour gérer des événements.
- **[stream](https://nodejs.org/api/stream.html)**: API pour gérer des flux de données.
- **[child_process](https://nodejs.org/api/child_process.html)**: API pour exécuter des processus externes.
- **[os](https://nodejs.org/api/os.html)**: API pour interagir avec le système d'exploitation.
- **[path](https://nodejs.org/api/path.html)**: API pour manipuler les chemins de fichiers.

### Cheatsheet: fs

Voici une petite cheatsheet pour l'API `fs`:

| Méthode | Description |
|---------|-------------|
| `fs.readFile(path, options, callback)` | Lit un fichier de manière asynchrone (non bloquante). |
| `fs.readFileSync(path, options)` | Lit un fichier de manière synchrone. |
| `fs.writeFile(path, data, options, callback)` | Écrit dans un fichier de manière asynchrone. |
| `fs.writeFileSync(path, data, options)` | Écrit dans un fichier de manière synchrone. |
| `fs.readdir(path, options, callback)` | Liste les fichiers d'un répertoire de manière asynchrone. |
| `fs.readdirSync(path, options)` | Liste les fichiers d'un répertoire de manière synchrone. |
| `fs.stat(path, callback)` | Récupère des informations sur un fichier de manière asynchrone. |
| `fs.statSync(path)` | Récupère des informations sur un fichier de manière synchrone. |


## CheatSheet: Création d'un repository (projet) NodeJS

### 1. Ouverture d'un terminal

Ouvrir un terminal (**CMD + J**) et se rendre dans le dossier où l'on souhaite créer le projet. (Utiliser la commande `cd` pour se déplacer dans les dossiers).

### 2. Créer d'un dossier

Pour créer un dossier, il suffit d'exécuter la commande suivante:

```bash
mkdir nom-du-dossier
```

Ensuite rendez-vous dans le dossier créé avec la commande `cd`:

```bash
cd nom-du-dossier
```

### 3. Initialisation du projet

Pour initialiser un projet NodeJS, il suffit d'exécuter la commande suivante:

```bash
npm init es6 -y
```

Cela va créer un fichier `package.json` qui contient les informations sur le projet.

**Note:** L'option `es6` permet d'activer la syntaxe ES6 (import/export) dans les fichiers JavaScript.

**Note:** L'option `-y` permet de répondre automatiquement à toutes les questions en acceptant les valeurs par défaut.

### 4. Installation de dépendances

Pour installer des dépendances (modules) dans le projet, il suffit d'exécuter la commande suivante:

```bash
npm install nom-du-module
```

Par exemple, pour installer le module `express`:

```bash
npm install express
```

### 5. Création d'un fichier JavaScript

Pour créer un fichier JavaScript, il suffit d'exécuter la commande suivante:

```bash
touch nom-du-fichier.js
```

Par exemple, pour créer un fichier `index.js`:

```bash
touch index.js
```

Ensuite, on peut éditer le fichier avec un éditeur de texte comme VSCode.

### 6. Exécution du programme

Pour exécuter un programme NodeJS, il suffit d'exécuter la commande suivante:

```bash
node nom-du-fichier.js
```

Par exemple, pour exécuter le fichier `index.js`:

```bash
node index.js
```

coucou
