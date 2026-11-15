# Linux CLI Basics

TryHackMe — Pre Security — Module 3

## 1. Me repérer et naviguer

| Commande | Rôle |
|---|---|
| `pwd` | Afficher le chemin du dossier courant : print working directory. |
| `ls` | Lister le contenu du dossier courant, sans les fichiers cachés par défaut. |
| `ls -l` | Afficher une liste détaillée. |
| `ls -al` | Afficher aussi les éléments cachés, avec les détails. |
| `cd Documents` | Entrer dans le sous-dossier Documents. |
| `cd ..` | Remonter au dossier parent. |
| `cd ~` | Revenir au dossier personnel. |

- `~` : dossier personnel de mon utilisateur ; `/home/ubuntu` dans l’exemple.
- `.` : dossier courant ; `..` : dossier parent.
- Un nom commençant par `.` est caché par défaut, pas protégé ni secret.

## 2. Chercher et lire un fichier

```bash
find ~ -name mission_brief.txt
```

Recherche ce nom dans mon dossier personnel et ses sous-dossiers. Le résultat donne le chemin du fichier s’il est trouvé.

```bash
cd /chemin/du/dossier
ls
cat mission_brief.txt
```

`/chemin/du/dossier` est un exemple à remplacer par le dossier réellement trouvé.

`cat` affiche le contenu du fichier dans le terminal.

## 3. Relever les informations système

| Commande | Information |
|---|---|
| `whoami` | Nom de l’utilisateur courant. |
| `uname` | Nom du noyau, par exemple Linux. |
| `uname -a` | Informations sur le noyau, le nom de machine et l’architecture. |
| `df -h` | Taille, espace utilisé et disponible des systèmes de fichiers montés. |
| `cat /etc/os-release` | Nom et version de la distribution. |

Dans la sortie de `uname -a` :

- `tryhackme` : nom de la machine (hostname).
- La chaîne de version du noyau n’est pas la version de la distribution.
- `x86_64` : architecture 64 bits.

Dans `df -h` :

- `Size` : taille totale du système de fichiers.
- `Used` / `Avail` : espace utilisé / disponible.
- `Use%` : pourcentage utilisé.
- `Mounted on` : point de montage ; `/` est la racine.
- `-h` : tailles lisibles, comme `G` ou `M`.
- `tmpfs` : système de fichiers temporaire en mémoire ; ce n’est pas un disque physique supplémentaire.

Je ne confonds pas ces tailles avec la somme de tous les disques physiques.

## 4. Identifier la distribution

Deux façons de lire le même fichier :

```bash
cd /etc
cat os-release
```

ou directement :

```bash
cat /etc/os-release
```

`/etc` contient notamment des fichiers de configuration et d’information.

L’exemple du cours indique Ubuntu 24.04.1 LTS :

- `PRETTY_NAME` : nom complet lisible.
- `NAME` : nom de la distribution.
- `VERSION_ID` : numéro de version.

## 5. Exercices de la room

- Trouver et lire `mission_brief.txt`.
- Relever l’utilisateur, la version du noyau, l’espace disque et la distribution.
- Mini-défi : trouver `day1_report.txt` dans mon dossier personnel, rejoindre son dossier et lire son contenu.

Les chemins, réponses et flags masqués ne sont pas inventés. Ces exercices restent à confirmer comme réalisés.
