04 — Le cloud computing

Ce que j’ai vu dans cette séance

- Le principe du cloud et ses avantages.
- Les clouds publics, privés et hybrides.
- Les modèles IaaS, PaaS et SaaS.
- Les principaux fournisseurs.
- La création de machines virtuelles dans le lab.
- La gestion des ressources et des coûts.

1. Du serveur physique au cloud

Avant : les entreprises installaient leurs serveurs physiques dans leurs locaux.
Il fallait acheter, installer et entretenir le matériel.

Avec la virtualisation : plusieurs machines virtuelles peuvent partager une même machine physique.

Avec le cloud : on utilise des ressources informatiques à la demande, sans acheter soi-même les serveurs physiques.

Exemples de ressources :
- Machines virtuelles.
- Stockage.
- Réseau.
- Applications.

Le cloud permet d’utiliser des ressources selon ses besoins plutôt que de posséder toute l’infrastructure.

2. Les avantages et caractéristiques du cloud

- Scalability : adapter la capacité aux besoins, par exemple quand une application reçoit plus de visiteurs.
- On-demand self-service : obtenir ou créer des ressources à la demande depuis une interface.
- Pay only for what you use : payer selon l’utilisation et les conditions du service.
- Sécurité : disposer de protections et d’outils pour sécuriser son environnement. La configuration et les accès restent importants.
- Haute disponibilité : prévoir une infrastructure qui limite les interruptions, même si un composant tombe en panne.
- Accès mondial : rendre ses services accessibles depuis différentes régions du monde.

L’idée : des ressources plus flexibles, des coûts adaptés aux besoins et une gestion facilitée.

Le cloud n’est pas automatiquement moins cher ni automatiquement sécurisé : cela dépend aussi de son utilisation.

3. Public, privé et hybride

Ces termes décrivent les modèles de déploiement du cloud.

Public cloud — cloud public

On utilise les services d’un fournisseur qui propose son infrastructure à plusieurs clients.

Le fournisseur gère le matériel physique.
Ce qu’il reste à gérer de mon côté dépend du service choisi.

Exemples du cours : sites web et applications d’entreprise.

Attention :
Public ne veut pas dire que mes données sont accessibles à tout le monde.

Private cloud — cloud privé

L’environnement cloud est réservé à une seule organisation.

Intérêt :
- Plus de contrôle.
- Plus de personnalisation.
- Répondre à des exigences particulières sur les données sensibles.

Exemples du cours : banques et secteur de la santé.

Compliance = conformité.
Cela veut dire respecter les règles et obligations applicables aux données et à l’organisation.

Un cloud privé n’est pas automatiquement sécurisé : il faut aussi bien le gérer.

Hybrid cloud — cloud hybride

Il combine un cloud privé et un cloud public qui peuvent fonctionner ensemble.

Exemple du cours : une plateforme de e-commerce.
- Certaines données sensibles restent dans l’environnement privé.
- Le cloud public permet d’absorber une hausse de fréquentation.

Public = services proposés à plusieurs clients.
Privé = environnement réservé à une organisation.
Hybride = combinaison des deux.

4. IaaS, PaaS et SaaS

Ici, la question n’est plus « public ou privé ? ».

La question est :
Qu’est-ce que le fournisseur gère, et qu’est-ce que je gère ?

IaaS — Infrastructure as a Service

Je loue des ressources de base :
- Serveurs virtuels.
- Stockage.
- Réseau.

Le fournisseur gère le matériel physique.
Je gère notamment le système d’exploitation et mes applications.

Analogie : appartement vide.
Le logement existe, mais je dois l’aménager.

PaaS — Platform as a Service

Le fournisseur gère l’infrastructure et le système d’exploitation.

Je me concentre sur mon application :
- La développer.
- La déployer.
- Gérer son fonctionnement et ses données.

Analogie : appartement semi-meublé.
La base est déjà prête, je n’ai pas tout à installer.

SaaS — Software as a Service

J’utilise directement une application fournie en ligne.

Le fournisseur gère le fonctionnement technique du service.
Je reste responsable de mon compte, de mes accès et de mon utilisation.

Exemples : Gmail et Zoom.
L’accès peut se faire depuis un navigateur ou une application.

Analogie : hôtel.
Le service est prêt à être utilisé.

Résumé :
- IaaS : je gère le système et les applications sur une infrastructure louée.
- PaaS : je développe et déploie mon application sur une plateforme préparée.
- SaaS : j’utilise une application déjà prête.

5. Les fournisseurs présentés dans le cours

- AWS — Amazon Web Services : présenté comme le leader du marché.
- Microsoft Azure : très présent dans les entreprises et le cloud hybride.
- Google Cloud — GCP : notamment présenté pour les données, l’IA et le machine learning.
- Alibaba Cloud : acteur important en Asie.
- IBM Cloud : notamment orienté entreprises, cloud hybride et IA.
- Oracle Cloud : notamment orienté applications d’entreprise et bases de données.

6. Exemples d’utilisation

Les exemples donnés dans le cours :

- Netflix : utilisation d’AWS pour une grande partie de son infrastructure et pour adapter ses ressources à la demande.
- Spotify : utilisation du cloud pour gérer ses services à grande échelle.
- Instagram : stockage et distribution de grandes quantités de photos et de vidéos.
- Boutiques en ligne : augmentation des ressources pendant les pics comme le Black Friday.

On adapte les ressources à la charge au lieu d’acheter du matériel uniquement pour les périodes les plus chargées.

7. Le vocabulaire AWS du lab

EC2

Une instance EC2 est un ordinateur virtuel dans le cloud AWS.

Elle dispose notamment :
- D’un processeur virtuel.
- De mémoire RAM.
- D’un système permettant de faire fonctionner des applications.

Créer une instance = ajouter une machine virtuelle à mon environnement.

Instance Type

Le type d’instance définit les ressources de la machine.

Dans le lab :
- t3.micro.
- m5.large.

Plus de ressources = généralement plus de capacité et un coût plus élevé.

Il faut choisir selon les besoins, pas prendre systématiquement la machine la plus puissante.

Région

Une région correspond à une zone géographique où sont hébergées les ressources.

Dans le lab, je choisis la région en haut à droite de l’interface.

8. Pratique : créer mon environnement

J’ai créé trois instances dans le bloc « Create Lab Machine ».

Machine pour l’interface :
- Nom : application-interface.
- Type : t3.micro.
- Statut : running.

Machines d’entraînement :
- Nom : study-machine-1.
- Type : m5.large.
- Statut : running.

- Nom : study-machine-2.
- Type : m5.large.
- Statut : running.

Running = machine démarrée.

Le lab utilise des machines plus puissantes pour les entraînements que pour l’interface.

Cet exercice correspond au modèle IaaS :
je dispose de machines virtuelles sur lesquelles je peux gérer le système et installer mes outils.

Cela permet de préparer un environnement pour les exercices de cybersécurité.

9. Pratique : observer et réduire les coûts

Dans la section « Billing », j’ai regardé :
- Le coût des différents types d’instances.
- Le coût total affiché pour l’environnement.

Dans le scénario, l’application est encore en développement.
Les utilisateurs n’ont donc pas encore besoin des machines d’entraînement.

J’ai arrêté :
- study-machine-1.
- study-machine-2.

J’ai laissé application-interface démarrée.

En retournant dans « Billing », j’ai constaté que le coût affiché dans le lab avait diminué.

- Arrêter les ressources inutilisées permet d’adapter les coûts.
- Arrêter une machine ne veut pas dire la supprimer.
- La diminution observée ici concerne le coût affiché dans l’exercice.
