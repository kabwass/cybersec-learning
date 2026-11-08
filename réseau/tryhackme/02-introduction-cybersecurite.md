02 — Modèle client-serveur et HTTP

Ce que j’ai vu dans cette séance

- Le fonctionnement du modèle client-serveur.
- Le vocabulaire : client, serveur, réseau, protocole, port et DNS.
- Le protocole HTTP et son fonctionnement « stateless ».
- Les méthodes HTTP, avec une première pratique sur GET.
- L’observation des requêtes dans les outils de développement de Firefox.

1. Le modèle client-serveur

Le principe : le client demande quelque chose, le serveur traite la demande et lui répond.

Exemple avec une page web :
- Mon navigateur Firefox est le client.
- Il envoie une requête pour demander la page.
- Le serveur renvoie une réponse avec la page demandée ou un message d’erreur.

À retenir :
Client → requête → serveur → réponse → client.

2. Le vocabulaire

- Client : programme qui envoie une demande, comme Firefox.
- Serveur : programme qui reçoit les demandes et fournit un service. Le mot peut aussi désigner la machine qui l’héberge.
- Réseau : ensemble d’appareils connectés qui échangent des données.
- Protocole : règles utilisées pour communiquer et comprendre les messages échangés.
- Request : requête envoyée par le client.
- Response : réponse renvoyée par le serveur.
- Port : numéro qui permet de diriger la communication vers un service sur une machine.
- DNS : permet notamment de retrouver l’adresse IP associée à un nom de domaine.

Deux précisions à retenir :
- Un port n’est pas le service lui-même.
- Une adresse IP est une adresse réseau, pas une position géographique.

3. HTTP et HTTPS

HTTP est un protocole utilisé pour communiquer entre un client et un serveur sur le Web.
Le navigateur envoie une requête HTTP, puis le serveur renvoie une réponse HTTP.
HTTPS correspond à une communication HTTP protégée par chiffrement.

HTTP est « stateless »
Stateless = sans état.
Cela veut dire que chaque requête est indépendante des précédentes. HTTP ne garde pas, à lui seul, une mémoire des échanges.

comment un site sait que je suis encore connecté ?

1. Je me connecte avec mes identifiants.
2. Le serveur crée une session avec un identifiant.
3. Mon navigateur conserve cet identifiant, souvent dans un cookie.
4. Il le renvoie avec les requêtes suivantes.
5. Le serveur reconnaît ma session.

[Il existe aussi des mécanismes utilisant des jetons, appelés « tokens ».]
Donc HTTP reste sans état, mais l’application ajoute un mécanisme pour reconnaître l’utilisateur entre plusieurs requêtes.

4. Les méthodes HTTP

On parle de méthodes HTTP, pas de commandes.
La méthode indique l’action demandée au serveur.

Les neuf méthodes présentées dans le cours :
- GET
- POST
- PUT
- DELETE
- PATCH
- HEAD
- OPTIONS
- CONNECT
- TRACE

Pour cette séance, on s’est entraîné avec GET.

GET sert à demander une ressource au serveur.
Exemples : une page HTML, une image ou un fichier utilisé par le site.

5. Observer les requêtes dans Firefox

Manipulation dans la machine du lab :

1. Ouvrir Firefox.
2. Aller sur `http://httpdemo.local:8080`.
3. Appuyer sur F12 pour ouvrir les outils de développement.
4. Aller dans l’onglet « Réseau » / « Network ».
5. Recharger la page.
6. Cliquer sur la première requête pour regarder ses détails.

On peut alors observer les requêtes du navigateur et les réponses du serveur.
Une page peut charger plusieurs ressources, donc plusieurs requêtes peuvent apparaître.

6. Lire les détails d’une requête

Les champs vus dans le cours :

- Scheme : protocole utilisé, `http` ou `https`.
- Host : hôte auquel on demande la ressource.
- Filename : chemin de la ressource demandée.
- Address : adresse IP du serveur, avec éventuellement le port.
- Status : résultat de la requête.

Le chemin `/`
`/` correspond à la racine du site.

Dans l’exemple du cours, le serveur renvoie la page d’accueil `index.html`.
`/` ne veut pas toujours dire `index.html`.

L’adresse `127.0.0.1`
Elle désigne la machine elle-même.
Dans ce lab, Firefox et le serveur web tournent sur la même machine.

Le port `8080`
Dans `http://httpdemo.local:8080`, le nombre `8080` est le port utilisé pour joindre le service web du lab.

Le statut `200 OK`
Il indique que la requête a réussi.
Dans le cas du GET observé, le serveur a traité la demande et renvoie la ressource.
