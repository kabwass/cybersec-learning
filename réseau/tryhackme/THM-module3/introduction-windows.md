# Introduction à Windows

TryHackMe — Pre Security — Module 3, room 2  
Environnement du cours : Windows Server 2019. L’interface peut varier selon la version.

## 1. Repères et comptes

- MS-DOS : interface en ligne de commande.
- Windows 1.0 (1985) : interface graphique ajoutée à DOS ; Windows a ensuite évolué vers un OS complet.
- Authentification : prouver mon identité (mot de passe, PIN…).
- Permissions : définir les actions autorisées après connexion.

| Compte | Droits |
|---|---|
| Invité (Guest) | Accès temporaire très limité. |
| Standard | Tâches quotidiennes et paramètres personnels, sans modifications globales réservées à l’administrateur. |
| Administrateur | Gestion du système, des logiciels et des utilisateurs. |

Dans le lab, le compte fourni est Administrateur. Je ne confonds pas ces droits élevés avec une absence de protections.

## 2. Bureau et outils essentiels

- Bureau (Desktop) : espace de travail avec fichiers, dossiers et raccourcis.
- Barre des tâches (Taskbar) : applications ouvertes ou épinglées, réseau, son, horloge et notifications.
- Menu Démarrer (Start) : applications, paramètres, déconnexion, arrêt et redémarrage.
- Recherche (Search) : retrouver une application, un fichier ou un réglage.
- Vue des tâches (Task View) : afficher les fenêtres ouvertes et passer de l’une à l’autre.
- Bloc-notes (Notepad) : modifier du texte.
- Explorateur de fichiers (File Explorer) : parcourir et gérer les fichiers.

## 3. Informations système et fichiers

- À propos de votre PC (About your PC) : informations sur la machine et la version de Windows.
- Les dossiers suivent une structure hiérarchique : un dossier peut contenir des fichiers et des sous-dossiers.
- L’Explorateur permet de naviguer, rechercher et consulter le chemin d’un dossier.

Dossier utilisé dans le cours :

```text
C:\Users\Administrator\Desktop\TryHatMe Onboarding
```

## 4. Applications et mises à jour

Les mises à jour corrigent des failles, des bugs et améliorent le fonctionnement.

- Windows Update : mises à jour du système et de certains composants ; automatisation selon la configuration.
- Applications : mise à jour intégrée, automatique ou installation manuelle d’une nouvelle version selon le logiciel.
- Installation : Microsoft Store, lorsqu’il est disponible, ou installateur `.exe` / `.msi` obtenu auprès d’un éditeur fiable.
- Le Microsoft Store n’est pas disponible par défaut sur Windows Server.
- Désinstallation : « Ajouter ou supprimer des programmes », Panneau de configuration ou désinstalleur du logiciel.

## 5. Paramètres et surveillance

- Paramètres (Settings) : interface moderne de configuration.
- Panneau de configuration (Control Panel) : outils classiques, encore utilisés pour certains réglages.
- Gestionnaire des tâches (Task Manager) : surveiller les processus et les ressources.

| Onglet présenté dans le lab | Utilité |
|---|---|
| Processus | Applications, processus en arrière-plan et consommation de ressources. |
| Performances | Utilisation du CPU, de la RAM et du réseau. |
| Utilisateurs | Sessions connectées et ressources utilisées. |
| Détails | Informations techniques, dont le PID : identifiant du processus. |
| Services | Services Windows et état : démarré ou arrêté. |

## 6. Sécurité Windows

Les rubriques présentées dans la room :

| Rubrique | Rôle |
|---|---|
| Protection contre les virus et menaces | Détection des logiciels malveillants, protection en temps réel et analyses. |
| Pare-feu et protection réseau | Contrôle des communications réseau selon des règles. |
| Contrôle des applications et du navigateur | Protection contre des applications, fichiers et sites potentiellement dangereux. |
| Sécurité des appareils | Protections reposant notamment sur le matériel. |

### Pare-feu Windows Defender

Les règles autorisent ou bloquent les connexions entrantes et sortantes.

- Domaine : réseau de domaine de l’organisation.
- Privé : réseau considéré comme fiable.
- Public : réseau non fiable, comme un Wi-Fi public.

Les paramètres avancés permettent de consulter, filtrer et créer des règles, avec leur profil, leur état et leur action.

## 7. Manipulations prévues dans le lab

À noter comme réalisées seulement après les avoir effectuées :

1. Ouvrir « About your PC » pour relever les informations système.
2. Explorer le dossier `TryHatMe Onboarding`.
3. Lancer l’installateur `TryHatMeWelcome` et suivre l’installation.
4. Ouvrir les paramètres et le Gestionnaire des tâches.
5. Dans Sécurité Windows : Protection contre les virus et menaces → Options d’analyse → Analyse personnalisée → Analyser maintenant → sélectionner `TryHatMe Onboarding`.
6. Consulter « See details » pour identifier le fichier de test détecté. Le cours précise qu’il est inoffensif ; son nom reste à relever dans le lab.
7. Examiner les règles dans les paramètres avancés du pare-feu.
