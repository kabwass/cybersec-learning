# Windows CLI Basics — Les bases de l’invite de commandes

TryHackMe — Pre Security — Module 3

## Ce que j’ai vu

- Naviguer dans les dossiers avec l’invite de commandes (Command Prompt / CMD).
- Afficher les éléments cachés, rechercher un fichier et lire son contenu.
- Identifier l’utilisateur, la machine, Windows et la configuration réseau.

## 1. Me repérer et naviguer

Dans cette room, les commandes sont utilisées dans CMD.

| Commande | Rôle |
|---|---|
| `cd` | Afficher le chemin du dossier courant. |
| `dir` | Lister les fichiers et dossiers visibles. |
| `dir /a` | Lister tous les éléments, y compris ceux marqués cachés ou système. |
| `cd Documents` | Entrer dans le sous-dossier Documents. |
| `cd ..` | Remonter au dossier parent. |

À retenir : dans CMD, `cd` seul affiche ma position ; avec un chemin, il change de dossier. Pour remonter, c’est bien `cd ..`, pas seulement `cd`.

Un fichier caché n’est pas forcément secret ni protégé : il n’apparaît simplement pas dans l’affichage habituel.

## 2. Trouver et lire un fichier

Le texte mentionne d’abord `mission_brief.txt`, mais les consignes et commandes portent sur `task_brief.txt`. Je garde ce dernier nom pour l’exercice.

Depuis mon dossier utilisateur :

```cmd
dir /s task_brief.txt
```

`/s` recherche dans le dossier courant et ses sous-dossiers, pas automatiquement dans tout le disque.

Une fois le fichier trouvé :

```cmd
cd "C:\chemin\du\dossier"
dir
type task_brief.txt
```

- Je remplace le chemin d’exemple par le dossier trouvé, pas par le chemin complet du fichier.
- Les guillemets permettent de gérer les chemins contenant des espaces.
- `dir` confirme la présence du fichier.
- `type` affiche son contenu dans le terminal.

## 3. Relever les informations système

| Commande | Ce que je consulte |
|---|---|
| `whoami` | Le compte utilisateur courant. |
| `hostname` | Le nom de l’ordinateur. |
| `systeminfo` | Les informations sur Windows et le système. |
| `ipconfig` | La configuration réseau des interfaces. |

Dans `systeminfo`, je repère :

- `OS Name` : nom de Windows.
- `OS Version` : version du système.
- `System Type` : type de système, notamment x86 ou x64.

Dans `ipconfig`, je repère :

- `IPv4 Address` : adresse IPv4 de l’interface.
- `Default Gateway` : passerelle par défaut.

Je distingue le nom de la machine (`hostname`) de son adresse réseau (`ipconfig`).

## 4. Mes repères Linux / Windows

| Action | Linux | Windows CMD |
|---|---|---|
| Afficher le dossier courant | `pwd` | `cd` |
| Lister le contenu | `ls` | `dir` |
| Inclure les éléments cachés | `ls -al` | `dir /a` |
| Remonter d’un niveau | `cd ..` | `cd ..` |
| Rechercher le fichier dans les sous-dossiers | `find ~ -name task_brief.txt` depuis le dossier personnel | `dir /s task_brief.txt` depuis le dossier personnel |
| Lire un fichier texte | `cat task_brief.txt` | `type task_brief.txt` |
| Identifier mon compte | `whoami` | `whoami` |

## 5. Exercice de la room

1. Ouvrir le terminal depuis le Bureau.
2. Me repérer et explorer les dossiers, y compris les éléments cachés.
3. Retrouver `task_brief.txt` puis lire son contenu.
4. Relever le compte, le nom de la machine, la version de Windows et les informations réseau.

Je ne note pas de chemin trouvé ni de résultat système sans les avoir relevés dans mon lab.
