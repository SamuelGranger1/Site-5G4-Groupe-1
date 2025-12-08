+++
title = "Notes de cours"
weight = 2
+++

# 1. Définition de la réalité virtuelle

Dans ce cours, nous adoptons une définition largement inspirée de Steven M. LaValle, auteur de *Virtual Reality* (2017), qui constitue aujourd’hui une référence internationale dans le domaine.

> **La réalité virtuelle (VR)** consiste à induire un *comportement ciblé* chez un organisme en utilisant une *stimulation sensorielle artificielle*, de manière à ce que cet organisme ait *peu ou pas conscience* de cette intervention.

Cette définition met l’accent sur quatre éléments fondamentaux :

1. un **comportement ciblé** ;
2. un **organisme** ;
3. une **stimulation sensorielle artificielle** ;
4. une **faible conscience de l’illusion**, permettant un sentiment de **présence**.

---

## 1.1 Comportement ciblé

Le comportement visé n’est jamais laissé au hasard :  
il est intentionnel, conçu par un créateur — développeur, chercheur, artiste ou designer.

### Exemples de comportements ciblés :

- voler au-dessus d’une ville virtuelle ;
- explorer un environnement simulé ;
- assister à un film immersif ;
- interagir avec d’autres utilisateurs via avatars.

L’objectif est que l’organisme **vive** cette expérience comme naturelle, sans constamment percevoir la manipulation de ses sens.

---

## 1.2 Organisme

Le terme *organisme* est volontairement large.  
Il englobe :

- les **humains** (casques VR grand public ou professionnels) ;
- les **animaux**, utilisés en recherche (souris, rats, poissons, primates).

### Exemples d'utilisation scientifique :

- étude de la navigation spatiale chez les rongeurs ;
- compréhension des circuits neuronaux en environnement contrôlé.

Dans ce cours, nous étudions la VR principalement du point de vue humain, mais cette définition plus générale rappelle que la VR est un **outil expérimental** avant d’être un produit commercial.

---

## 1.3 Stimulation sensorielle artificielle

La VR repose sur la capacité de **remplacer ou modifier** les signaux sensoriels naturels.

Elle peut agir sur :

### Vision  
- Le casque affiche une scène 3D qui remplace complètement la vision du monde réel.

### Audition  
- Les sons spatialisés font croire à des sources situées dans l'espace virtuel.

### Toucher / proprioception  
- Vibrations, retours haptiques, plateformes de mouvement.

### But final  
L’organisme utilise ces signaux **artificiels** comme base de perception et d’action, ce qui crée une illusion d’être réellement *présent* dans un autre monde.

---

## 1.4 Absence de conscience de l’illusion et sentiment de présence

Pour que la VR soit efficace, l'utilisateur ne doit pas se rappeler à chaque instant que ses sens sont manipulés.  
Il doit ressentir :

> **« J’ai l’impression d’être là-bas. »**

Ce phénomène est appelé **présence**.  
Un bon système VR ne cherche donc pas uniquement à afficher des images 3D, mais à :

- créer une illusion cohérente,  
- maintenir une immersion stable,  
- et réduire la conscience de l’artificialité.

Lorsque cette illusion échoue, l’utilisateur peut ressentir de la confusion ou du **cybersickness**.

---

# 2. Réalité virtuelle, réalité augmentée, réalité mixte : comprendre les différences

Avant d’aller plus loin dans la partie technique, c’est important de clarifier ce qu’on entend par “VR”, “AR”, “MR” et même “XR”, parce que ce sont des termes qu’on mélange souvent. Les technologies se ressemblent, elles utilisent parfois les mêmes capteurs et les mêmes algorithmes, mais leur objectif n’est pas du tout le même.

Cette section s’inspire principalement de :  
- *Virtual Reality* de Steven M. LaValle (2017)  
- *Understanding Augmented Reality* de Alan B. Craig (2013)  
- Documentation Meta/Oculus Developer (2023)  
- Norme OpenXR du Khronos Group  

L’idée est simplement de poser les bases pour qu’on parle tous le même langage dans le reste du cours.

---

## 2.1 Réalité virtuelle (VR)

La **réalité virtuelle**, c’est la technologie qu’on utilise quand on veut que l’utilisateur quitte complètement le monde réel pour entrer dans un monde 100% numérique. Avec un casque VR, tu ne vois plus ton environnement physique. Toute la perception passe par :

- deux écrans (un pour chaque œil),  
- un rendu 3D stéréoscopique,  
- un suivi de tête et de position (6DOF),  
- parfois du son 3D et du retour haptique.

L’objectif, c’est l’immersion totale.  
Le système veut te convaincre que “tu es là-bas”, même si tu es physiquement dans ta chambre. C’est exactement ce que LaValle appelle la **présence**.

Exemples d’applications VR :  
- entraînement en simulateur (médecine, aviation, industrie),  
- jeux immersifs,  
- visualisation architecturale,  
- recherche en neurosciences (étudier la navigation, les phobies, etc.).

En VR, le monde réel n’est plus une référence. Il est complètement remplacé.

---

## 2.2 Réalité augmentée (AR)

La **réalité augmentée**, elle, garde ton environnement réel comme base.  
L’idée, c’est d’ajouter du contenu numérique **par-dessus** ce que tu vois déjà autour de toi.

Exemples d’appareils AR :  
- téléphones (Pokémon GO, IKEA Place),  
- tablettes,  
- lunettes AR comme HoloLens ou Magic Leap.

Pour que ça fonctionne, l’appareil doit comprendre un minimum ton environnement :  
- détecter les surfaces,  
- repérer les murs,  
- savoir où tu es situé dans l’espace,  
- estimer la lumière ambiante pour intégrer les objets virtuels correctement.

L’objectif n’est **pas** l’immersion totale.  
C’est plutôt de “compléter” le monde réel avec des éléments interactifs, informatifs ou visuels.

Applications AR :  
- instructions de maintenance industrielle,  
- visualisation de produits avant achat,  
- filtres Snapchat,  
- navigation intérieure,  
- outils pédagogiques.

---

## 2.3 Réalité mixte (MR)

La **réalité mixte** est un concept un peu plus flou, mais on peut la voir comme une forme “plus avancée” de l’AR.  
Ici, les objets virtuels ne sont pas seulement superposés : ils peuvent **interagir** avec le monde réel.

Exemple :  
- un objet virtuel peut être caché par une table réelle (occlusion),  
- une créature virtuelle peut marcher sur ton plancher et éviter les obstacles,  
- tu peux saisir un objet virtuel avec ta main réelle.

Pour faire ça, il faut une compréhension profonde de l’environnement :  
- reconstruction 3D en temps réel,  
- SLAM avancé (Simultaneous Localization And Mapping),  
- détection d’objets réels,  
- suivi précis des mains.

C’est ce que promettent les casques comme HoloLens 2 ou le Meta Quest 3 en mode passthrough couleur.

---

## 2.4 XR (Extended Reality)

Le terme **XR** est un mot parapluie qui regroupe :  
- VR,  
- AR,  
- MR.

On utilise souvent “XR” dans les milieux professionnels parce que la frontière entre les technologies commence à devenir floue. Par exemple, un Meta Quest 3 peut faire **VR, AR, MR** selon l’application.

---

## 2.5 Résumé des différences

Voici un résumé simple que j’aime utiliser, parce qu’il clarifie vraiment l’intention de chaque technologie :

| Technologie | Ce que tu vois | Rôle du monde réel | Niveau d’immersion | Exemple |
|------------|----------------|---------------------|---------------------|---------|
| **VR** | 100% virtuel | Ignoré / masqué | Très élevé | Beat Saber, simulateur de vol |
| **AR** | Réel + objets numériques superposés | Référence principale | Faible à modéré | IKEA Place, filtres Snapchat |
| **MR** | Réel + virtuel qui interagit | Analyse profonde de l’environnement | Modéré à élevé | HoloLens, Quest 3 passthrough |
| **XR** | Tout ce qui précède | N/A | Variable | terme générique |

Ce tableau est basé sur les classifications proposées par LaValle (UIUC), Craig (Elsevier) et le Khronos Group.

---

## 2.6 Pourquoi faire cette distinction ?

Même si ces technologies semblent proches, elles reposent sur des contraintes techniques très différentes.

### En VR :
- stéréoscopie obligatoire,  
- tracking très précis,  
- 90 Hz minimum pour éviter la nausée,  
- rendu 3D complet pour deux yeux.

### En AR/MR :
- traitement d’image intensif,  
- reconnaissance du monde réel,  
- gestion de l’occlusion,  
- fusion du numérique et du réel.

Les compétences qu’un développeur doit maîtriser ne sont donc pas les mêmes.  
Et dans ton atelier, on s’intéresse **uniquement** à la VR — plus précisément au rendu **stéréoscopique**, qui est le cœur de l’illusion de profondeur.

---

## 2.7 Lien avec la stéréoscopie

La VR ne peut pas exister sans stéréoscopie.  
Contrairement à l’AR, la VR doit recréer *toute* la profondeur en générant deux images légèrement différentes, une pour chaque œil.

Dans la prochaine section, on va voir pourquoi ce principe est essentiel et comment un moteur VR génère ces deux vues (left/right) grâce aux matrices de vue et de projection.

---
# 3. La stéréoscopie : un principe essentiel pour comprendre la VR

Dans cette partie, on va parler d’un aspect fondamental de la réalité virtuelle : **la stéréoscopie**.  
C’est littéralement la base qui permet de créer l’impression de profondeur dans un casque VR. Sans ce principe, la VR ne serait qu’un écran plat collé au visage, sans immersion et sans sensation d’espace.

Cette section s’appuie principalement sur :  
- LaValle, *Virtual Reality* (chapitre sur la vision humaine et la stéréoscopie)  
- Documentation Meta/Oculus (rendu stéréo et IPD)  
- SIGGRAPH Courses sur la perception 3D  

---

## 3.1 Qu’est-ce que la stéréoscopie ?

La stéréoscopie, c’est simplement le fait que **chaque œil voit une image différente** du monde réel.  
Nos yeux sont espacés d’environ **6,3 cm** (on appelle ça l’IPD — *Inter-Pupillary Distance*).  
À cause de cette distance, l’œil gauche et l’œil droit ne reçoivent pas exactement la même image.  

Le cerveau utilise ensuite cette différence — qu’on appelle **disparité binoculaire** — pour calculer la profondeur.

### Exemple simple
Si tu places ton doigt devant toi et que tu fermes alternativement l’œil gauche puis l’œil droit, tu vas voir ton doigt bouger “d’un côté à l’autre”.  
C’est exactement cette différence que la VR imite avec deux images légèrement différentes.

---

## 3.2 Pourquoi la VR a absolument besoin de stéréoscopie

Dans un casque VR, tu ne vois pas le monde réel.  
Alors si on affichait la même image pour les deux yeux :

- il n’y aurait **aucune profondeur**,  
- tout serait **plat**,  
- ton cerveau n’aurait **aucune raison de croire** à l’illusion,  
- tu serais juste devant un grand écran 2D à quelques centimètres de ton visage.

Donc pour que ton cerveau accepte le monde virtuel comme “réel”, il faut **recréer artificiellement deux caméras**, placées exactement là où seraient tes yeux.

C’est ce qu’on appelle le **rendu stéréoscopique**.

---

## 3.3 Comment on génère deux images dans un moteur VR

Dans un moteur VR (Unity, Unreal, OpenXR… ou même ton mini moteur C++), le système calcule :

- **une vue pour l’œil gauche**  
- **une vue pour l’œil droit**

Ces deux vues sont presque identiques, mais elles ont un **léger décalage horizontal** correspondant à ton IPD.

### En pratique, ça implique :

1. Deux matrices de vue (viewLeft, viewRight)  
2. Deux matrices de projection (projLeft, projRight)  
3. Deux passes de rendu (on dessine la scène deux fois)

C’est exactement ce que ton atelier VR fait à petite échelle.

---

## 3.4 Notion d’IPD et effet sur le confort

L’IPD, c’est la distance entre les pupilles.  
En VR, si l’IPD n’est pas correct, deux problèmes arrivent :

- **Mauvaise perception de la profondeur**  
- **Fatigue visuelle ou inconfort**

Dans un casque VR moderne, l’IPD peut être ajusté soit mécaniquement (Quest, Index), soit électroniquement.  
La documentation Meta insiste beaucoup sur ce point : un IPD mal configuré est l’une des causes principales de **nausée** et de **mal de tête**.

---

## 3.5 Projection asymétrique (FOV tangentiel)

Un point plus avancé, mais important :

Chaque œil ne regarde **pas droit devant lui**.  
Il regarde légèrement vers l’intérieur, ce qui fait que la projection nécessaire pour un œil n’est pas parfaitement symétrique.

Certains moteurs VR utilisent donc une **projection asymétrique** pour mieux correspondre :

- à la position réelle des yeux,  
- au comportement des lentilles Fresnel,  
- au champ de vision.

SIGGRAPH et Oculus expliquent que cette asymétrie améliore la clarté de l’image et la stabilité visuelle.

Ton atelier n’utilise pas ces projections avancées (ce serait trop complexe), mais c’est ce que font les moteurs professionnels.

---

## 3.6 Exemple visuel : comment le cerveau voit en stéréo

Pour donner une idée simple, voici un schéma ASCII :

[ Oeil gauche ] [ Oeil droit ]
\ /
\ /
\ /

Chaque œil reçoit un angle de vue légèrement différent.  
Le cerveau compare les deux images et reconstruit la distance.

Dans un casque VR, on simule exactement ces deux rayons, sauf que :

- l’objet est 3D calculé par le GPU,  
- les deux caméras virtuelles remplacent tes deux yeux,  
- les lentilles amplifient le champ de vision.

---

## 3.7 Stéréoscopie vs profondeur “fausse” (indices monoculaires)

Même avec un seul œil, on peut percevoir une forme de profondeur grâce à :

- la perspective,  
- la taille relative,  
- l’ombre,  
- le flou,  
- le mouvement de caméra.

Ce sont des **indices monoculaires**.

En VR, ils sont présents, mais ils ne suffisent pas.  
Si on coupe la stéréo, l’immersion chute drastiquement.  
La Valle (UIUC) explique que **la stéréoscopie est le signal de profondeur le plus fort que le cerveau utilise**, et c’est pour ça que la VR dépend autant de ce mécanisme.

---

## 3.8 Pourquoi la stéréoscopie cause parfois de l’inconfort

En VR, on demande aux yeux de faire quelque chose qui n’arrive pas dans la vraie vie :

- les yeux convergent vers un point virtuel (comme dans la réalité),  
- mais l’accommodation (la mise au point du cristallin) reste fixe, car l’écran ne bouge pas.

Ce conflit s’appelle le **vergence-accommodation conflict**.

Quand il est trop fort, tu as :

- fatigue visuelle,  
- maux de tête,  
- difficulté à faire la mise au point.

La recherche travaille activement sur de nouvelles solutions :  
- écrans multifocaux,  
- écrans varifocaux,  
- lentilles à profondeur variable,  
- holographie (SIGGRAPH 2023).

---

## 3.9 Résumé : pourquoi la stéréoscopie est la base de la VR

1. Elle recrée la profondeur de manière naturelle.  
2. Elle permet au cerveau de croire que le monde virtuel est réellement “spatial”.  
3. Elle est nécessaire pour la présence et l’immersion.  
4. Sans elle, on obtient un simple écran 2D.  
5. Toute la chaîne VR (tracking, shaders, matrices, lentilles) existe pour la supporter.

C’est pourquoi ton atelier VR n’est pas juste un exercice OpenGL :  
c’est une **mini version** d’un vrai pipeline VR qui montre **la mécanique exacte** utilisée dans les casques modernes.

---

# 4. Applications concrètes de la réalité virtuelle

Maintenant qu’on comprend mieux ce qu’est la VR et comment elle fonctionne au niveau perceptif, c’est important de voir **à quoi elle sert réellement**. La VR n’est pas seulement utilisée pour jouer à des jeux : c’est une technologie qui touche plusieurs domaines importants, autant dans l’industrie que dans la recherche scientifique. Dans cette section, je présente les applications les plus courantes, basées sur LaValle, Meta, et différents cas publiés dans SIGGRAPH ou l’industrie.

---

## 4.1 Formation et simulation

C’est probablement l’un des domaines où la VR est la plus utile.  
La raison est simple : **la VR permet de s’entraîner dans des conditions réalistes, sans être exposé à des risques réels**.

Exemples :

- simulation de vol (pilotes d’avion),  
- entraînement militaire dans des environnements virtuels,  
- pratique médicale (chirurgie, injection, soins d’urgence),  
- formation en entreprise (manipulation de machines, sécurité).

L’avantage est énorme :  
on peut répéter les gestes, apprendre de ses erreurs, recommencer autant de fois qu’on veut, le tout dans un environnement contrôlé.  
Des études scientifiques montrent aussi que la VR améliore la rétention des compétences, surtout quand la tâche est motrice.

---

## 4.2 Architecture, design et urbanisme

Avec la VR, on peut visiter un bâtiment **avant même qu’il existe**.  
Ça change totalement la façon dont les architectes présentent leurs projets.

Exemples d’utilisation :

- visiter une maison en construction,  
- ajuster la lumière naturelle selon l’heure de la journée,  
- comparer plusieurs configurations de pièces,  
- collaborer à distance dans un espace 3D partagé.

Là encore, la VR n’est pas un “gadget”.  
C’est un outil professionnel concret : il réduit les erreurs, accélère la prise de décision et améliore la communication entre le client et les designers.

---

## 4.3 Jeux vidéo et divertissement

Même si la VR ne se résume pas à ça, les jeux restent un moteur majeur de son développement.  
Grâce au suivi de mouvement, à la stéréoscopie et à l’immersion, on obtient un type d’expérience impossible sur un écran classique.

Jeux populaires :

- **Beat Saber** : coordination et rythme  
- **Half-Life: Alyx** : exploration et interactions réalistes  
- **Superhot VR** : gameplay basé sur le mouvement du corps  
- **VRChat** : interactions sociales dans des mondes virtuels

La VR change non seulement la manière de jouer, mais aussi la manière de **vivre une histoire**, avec des films 360°, des concerts virtuels, des animations 3D immersives, etc.

---

## 4.4 Médecine et réhabilitation

La VR est utilisée pour :

- traiter les phobies (exposition graduelle),  
- réduire la douleur lors de procédures médicales,  
- faire de la rééducation physique,  
- aider certains patients à retrouver leur mobilité.

Parce que la VR capte les mouvements du corps, elle peut guider un patient dans des exercices adaptés à son état, tout en collectant des données précises pour le thérapeute.

---

## 4.5 Recherche scientifique et neurosciences

C’est un domaine un peu moins connu du grand public, mais extrêmement important.  
La VR permet aux chercheurs de contrôler totalement l’environnement d’un sujet — humain ou animal — ce qui est impossible dans le monde réel.

Exemples :

- étudier la navigation spatiale,  
- analyser les comportements sociaux,  
- comprendre les circuits neuronaux,  
- mesurer les réactions physiologiques à un environnement contrôlé.

C’est pour ça que LaValle, qui vient du milieu académique, insiste que la VR n’est pas juste un produit commercial : c’est aussi un **laboratoire expérimental mobile**.

---

# 5. Défis techniques et limitations actuelles de la VR

Même si la VR est impressionnante et continue d’évoluer rapidement, il reste plusieurs défis techniques importants.  
Ces défis viennent principalement du fait que la VR doit convaincre le cerveau avec des illusions très précises, et qu’un simple détail mal géré peut briser l’immersion ou rendre l’utilisateur malade.

Cette section s’inspire fortement de LaValle, des recherches SIGGRAPH et des recommandations techniques de Meta/Oculus.

---

## 5.1 Latence et motion-to-photon delay

La **latence** est le délai entre ton mouvement réel et l’image mise à jour dans le casque.  
Si ce délai est trop long, le cerveau remarque l’incohérence et l’illusion tombe.

Les casques modernes visent un **motion-to-photon** inférieur à 20 ms.

Problèmes causés par une latence trop élevée :

- nausée,  
- décalage entre mouvement et perception,  
- impression que le monde "flotte".

C’est une des raisons pour lesquelles la VR demande des GPU puissants et des logiciels optimisés.

---

## 5.2 Fréquence d’image (90 Hz et plus)

Pour que l’image soit fluide et naturelle, il faut un minimum de :

- **72 Hz** (acceptable),  
- **90 Hz** (standard VR),  
- **120 Hz** (haut de gamme).

Une fréquence faible crée du flou, des saccades, et augmente les risques de cybersickness.

Le moteur VR doit rendre **deux images** par frame (œil gauche et œil droit), ce qui double presque le coût de calcul. D’où l’importance d’optimiser le rendu.

---

## 5.3 Conflit vergence-accommodation

Comme expliqué dans la section stéréoscopie :

- les yeux convergent vers des objets virtuels,  
- mais l’accommodation reste fixe (écran à distance constante).

Ce conflit peut causer :

- fatigue visuelle,  
- difficulté à faire la mise au point,  
- inconfort après quelques minutes.

Des solutions expérimentales existent, comme les écrans varifocaux et holographiques, mais elles ne sont pas encore grand public.

---

## 5.4 Champ de vision limité

Le **FOV** (Field of View) des casques VR actuels est généralement entre 90° et 110°.  
C’est bien, mais encore loin du champ de vision humain naturel, qui est d’environ 200° horizontalement.

Un FOV trop petit peut donner l’impression de “regarder dans un masque de plongée”.  
Des progrès sont faits avec :

- des lentilles plus grandes,  
- des écrans plus larges,  
- des systèmes optiques pliés ("pancake lenses").

---

## 5.5 Résolution et effet de grille (screen-door effect)

Même si les casques montent en résolution, il reste parfois visible une sorte de grille due à l’espace entre les pixels.  
Ce problème diminue avec :

- des écrans plus denses,  
- des sous-pixels optimisés,  
- des lentilles plus efficaces.

Les casques haut de gamme comme le Quest 3 ou le Varjo XR-3 s’en sortent déjà très bien, mais ce n’est pas parfait.

---

## 5.6 Tracking et dérive

Pour que la VR soit naturelle, le suivi doit être :

- précis,  
- constant,  
- sans dérive dans le temps.

La VR moderne utilise une combinaison de :

- caméras embarquées,  
- capteurs inertiels (IMU),  
- algorithmes SLAM.

Si une pièce est trop sombre, trop lumineuse ou trop vide, le tracking peut devenir instable, ce qui brise l’immersion.

---

## 5.7 Cybersickness

Le cybersickness est l’équivalent du mal des transports, mais dans un monde virtuel.  
Il peut être causé par :

- latence,  
- mismatch visuel/vestibulaire,  
- faible framerate,  
- mauvaises distances de confort,  
- accélérations non naturelles.

LaValle consacre tout un chapitre à ce sujet, car c’est l’un des plus grands défis de la VR actuelle.

---

## 5.8 Conclusion des défis

En résumé, la VR fonctionne déjà très bien, mais elle demande :

- beaucoup de calcul,  
- une synchronisation parfaite,  
- une compréhension précise du cerveau humain,  
- et des systèmes optiques et logiciels sophistiqués.

C’est ce qui rend la VR à la fois **complexe** et **passionnante** à étudier.

