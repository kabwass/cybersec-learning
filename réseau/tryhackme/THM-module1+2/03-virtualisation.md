03 — Virtualisation, hyperviseurs et conteneurs

Ce que j’ai vu dans cette séance

- Pourquoi utiliser la virtualisation.
- Le rôle de l’hyperviseur et ses deux types.
- Les machines virtuelles (VM).
- Les conteneurs, leurs images et Docker.
- Les avantages de la virtualisation.

1. Pourquoi la virtualisation ?

Le cours part du principe : un service = un serveur physique.
Exemples : une application ou un service de mails.

Plusieurs problèmes :
- Coût des serveurs et de leur entretien.
- Installation longue : il faut préparer chaque machine physique.
- Ressources sous-utilisées : une application n’utilise pas forcément toute la puissance du serveur.

L’idée : partager une machine physique entre plusieurs ordinateurs virtuels qui fonctionnent séparément.
C’est la virtualisation.

2. L’hyperviseur

L’hyperviseur (hypervisor) est le logiciel qui crée et gère les machines virtuelles.
Il répartit les ressources et joue le rôle d’arbitre entre les VM.

À ne pas confondre :
- Hardware = matériel physique.
- Software = logiciel.

Ce qu’il permet de faire :
- Créer plusieurs machines virtuelles sur un ordinateur physique.
- Donner à chaque VM sa part de processeur (CPU), de RAM et de stockage.
- Maintenir une séparation entre les VM.
- Démarrer, arrêter, mettre en pause, cloner ou supprimer des VM.

3. Les deux types d’hyperviseurs

Type 1
Il fonctionne directement sur le matériel physique.
Matériel → hyperviseur → VM.

Adapté aux serveurs et aux environnements professionnels.
Exemples du cours : production, bases de données et data centers.

Type 2
Il fonctionne sur un système d’exploitation déjà installé.
Matériel → système d’exploitation → hyperviseur → VM.

Pratique pour apprendre et faire des tests sur son ordinateur.
Exemples : VirtualBox et VMware Workstation.

Les réponses de l’exercice :
- Tester un fichier suspect dans un lab → type 2.
- Serveur de production → type 1.
- Serveur de base de données → type 1.
- Tester un logiciel → type 2.
- Utiliser Kali Linux sur son ordinateur → type 2.
- Data center → type 1.

Ce sont les choix du cours selon le contexte, pas des règles absolues.
Kali Linux n’est pas limité aux hyperviseurs de type 2.

4. Les machines virtuelles (VM)

VM = Virtual Machine = machine virtuelle.
Dans le cours, « Lab Machine » désigne la VM du laboratoire.

C’est un ordinateur virtuel avec :
- Un processeur virtuel.
- De la mémoire RAM attribuée.
- Du stockage virtuel.
- Une interface réseau virtuelle.
- Son propre système d’exploitation et son propre noyau.

Exemple : je veux utiliser Kali Linux sans acheter un autre ordinateur.
J’installe un hyperviseur, je crée une VM et j’y installe Kali Linux.

Les VM sont séparées : si une VM plante, les autres peuvent continuer à fonctionner.
Mais une VM ne garantit pas une sécurité absolue. Pour analyser un fichier dangereux, il faut un lab adapté et correctement configuré.

5. Les conteneurs

Un conteneur est un environnement léger et isolé pour une application et ses dépendances.
Les dépendances sont les éléments nécessaires à l’application : bibliothèques, outils, versions, etc.

Contrairement à une VM, il n’a pas son propre noyau : il partage celui du système sur lequel il fonctionne.

Le noyau (kernel) est la partie centrale du système d’exploitation.
Il gère notamment le matériel, la mémoire et les programmes en cours d’exécution.

Les conteneurs :
- Démarrent rapidement.
- Utilisent généralement moins de ressources que des VM complètes.
- Facilitent le déploiement des applications dans un environnement compatible.

Attention : ils partagent un noyau, donc leur séparation n’est pas la même que celle des VM.
Un conteneur Windows ne tourne pas directement sur un noyau Linux.

6. Les images et Docker

Une image de conteneur est un modèle préconfiguré qui contient l’application et ce qu’il faut pour créer un conteneur.

À retenir :
- Image = modèle.
- Conteneur = environnement créé à partir de ce modèle.

Docker est une plateforme qui facilite la création, le déploiement et l’exécution des conteneurs.
Ce n’est pas un hyperviseur.

On peut aussi utiliser Docker et des conteneurs dans une VM.
Exemple : serveur physique → hyperviseur → VM → conteneurs.
Les conteneurs ne sont pas obligatoirement dans une VM.

7. L’analogie de l’immeuble

- Machine physique = immeuble.
- Hyperviseur = gestionnaire qui répartit les ressources.
- VM = appartements séparés.
- Conteneurs = pièces dans un appartement.

Les appartements partagent les ressources de l’immeuble mais gardent leur espace.
Les pièces partagent davantage d’éléments entre elles.
C’est une image pour retenir la différence, pas un schéma exact.

8. Rappel sur les ports réseau

Un port est un point d’entrée numéroté qui permet de diriger une communication vers un service sur une machine.
Le port n’est pas le service lui-même.

9. Les avantages de la virtualisation

- Réduction des coûts : moins de machines physiques à acheter et entretenir.
- Meilleure utilisation des ressources : plusieurs VM partagent le matériel disponible.
- Tests dans un environnement séparé : utile en cybersécurité, sans oublier les précautions nécessaires.
- Déploiement rapide : créer une VM au lieu d’installer un nouvel ordinateur physique.
- Flexibilité : utiliser différents systèmes et adapter ses environnements.
- Portabilité : déplacer ou reproduire un environnement sur une infrastructure compatible.
- Évolutivité (scalability) : ajouter des VM ou adapter les ressources aux besoins.
- Gestion centralisée : gérer plusieurs VM avec des outils communs.

10. Questions du cours

Que permet la virtualisation à plusieurs applications de partager ?
Réponse : un serveur physique (physical server).

Quel logiciel gère les ressources des machines du lab ?
Réponse : l’hyperviseur (hypervisor).

Ce que je retiens

- Virtualisation = une machine physique peut fonctionner comme plusieurs ordinateurs séparés.
- Hyperviseur = logiciel qui crée et gère les VM.
- VM = ordinateur virtuel avec son propre système et son propre noyau.
- Conteneur = environnement léger qui partage un noyau.
- Image = modèle pour créer un conteneur.
- Docker = outil pour travailler avec les conteneurs.
- Isolé ne veut pas dire sans risque.
