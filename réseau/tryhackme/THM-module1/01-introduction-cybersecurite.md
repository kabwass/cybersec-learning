séance 1 : Introduction à la cybersécurité

Plateforme : TryHackMe
Parcours : Pre Security

1. Sécurité offensive — Offensive security

La sécurité offensive consiste à adopter le point de vue
d'un attaquant pour identifier des faiblesses et améliorer
la protection des systèmes.

DIRB : 

Dans le lab, j'ai découvert la commande :

dirb <URL_du_laboratoire>

DIRB utilise une liste de mots pour rechercher des fichiers
et des répertoires accessibles sur un serveur web, même
s'ils ne sont pas directement visibles dans les menus du site.

Dans la sortie de mon exercice, des résultats étaient
signalés par le symbole « + ». Je pouvais utiliser les
chemins trouvés pour accéder aux URL correspondantes.

À retenir :
- DIRB et DirBuster sont deux outils différents.
- Un contenu découvert n'est pas forcément une faille.
- Je ne dois pas tester des sites sans autorisation.

2. Sécurité défensive — Defensive security

La sécurité défensive vise à protéger les appareils,
les réseaux et les systèmes, ainsi qu'à détecter les
menaces et à répondre aux incidents.

Tableau de bord de supervision

Il permet de visualiser l'activité, les événements
suspects et les alertes provenant des outils de sécurité.

Les outils peuvent générer des alertes automatiquement,
mais une alerte ne confirme pas à elle seule une attaque.

Rôle du SOC

Le SOC (centre opérationnel de sécurité) 
analyse les événements et les alertes pour :
- Distinguer les activités malveillantes des faux positifs.
- Comprendre ce qui se passe.
- Déterminer la réponse adaptée.
- Rechercher des menaces non détectées automatiquement.

Réponse à une activité malveillante

Dans le scénario du lab, une action consistait
à identifier une adresse IP malveillante et à la bloquer.

Bloquer une IP est une mesure possible, mais ne suffit
pas toujours à arrêter une attaque.

3. Ce que je retiens

La sécurité offensive cherche les faiblesses dans un cadre
autorisé. La sécurité défensive protège les systèmes,
surveille leur activité et répond aux incidents.
Je dois analyser le contexte avant de conclure qu'une
activité est une attaque ou de décider d'un blocage.


- Comment fonctionne une liste de mots utilisée par DIRB ?
- Comment reconnaître un faux positif ?
- Dans quels cas le blocage d'une IP est-il adapté ?
