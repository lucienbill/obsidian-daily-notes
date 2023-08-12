# Notes quotidiennes avec Obsidian
## A quoi sert ce truc (description) ?
Il y a quelques questions auxquelles mon cerveau a du mal à répondre :
- J'ai fait quoi hier ? Et la semaine dernière ? Le mois dernier ?
- Où me suis-je arrêté hier ? Quel était mon plan ?

Heureusement, je prends des notes : c'est la mémoire persistante que je n'ai pas naturellement.
Pendant des années, j'ai écrit des choses de manière peu ordonnée dans de nombreux onglets non sauvegardés dans NotePad++.
C'est mieux que rien, mais ça a ses limites.

J'ai récemment découvert [cet article](https://v5.chriskrycho.com/journal/writing-down-what-i-do-in-obsidian/) de Chris Krycho : "Writing Down What I Do-In Obsidian".

Ce projet est ma propre version de son système :
- La structure est moins rigide (plus simple à exploiter pour moi)
- J'utilise le plugin Templater pour automatiser certains nommage et liens.

## Exigences
TODO ; Obsidian + Templater (module complémentaire)
## Configuration
Copiez les modèles (templates) de `{ce repo}/{langue}/Work/templates` dans `{votre coffre Obsidian}/Work/templates`

Configurez ensuite Obisidian :
- Obsidian > Paramètres > Modules principaux (Options) > Modèles = **Désactivé**
- Obsidian > Paramètres > Notes quotidiennes (Modules principaux) > Nouvel emplacement de fichier = `Work/Tracking/Daily`
- Obsidian > Paramètres > Notes quotidiennes (Modules principaux) > Emplacement du fichier de modèle = `Work/templates/Daily`
- Obsidian > Paramètres > Templater (Module complémentaire) > Template folder location = `Work/templates`

Configuration optionnelle :
- Obsidian > Paramètres > Templater (Module complémentaire) > Trigger Templater on new file location = **Activé** - effet : exécute le modèle "Daily" lorsque que vous créez une note quotidienne en cliquant sur "Ouvrir la note quotidienne"

Quittez ensuite les paramètres et cliquez sur "Open today's daily note" (Ouvrir la note quotidienne d'aujourd'hui) - par défaut, il s'agit d'une icône de calendrier dans la barre de gauche.
Si vous avez activé la configuration `Templater (Module complémentaire) > Trigger Templater on new file location`, le modèle "Daily" sera automatiquement exécuté sur votre note quotidienne.

Les autres modèles devront être exécutés manuellement sur le fichier sélectionné à partir de l'icône "Templater" (qui ressemble à `<%`).

Note : selon votre système, les modèles peuvent considérer que votre semaine commence le dimanche.
En France sur mon ordinateur, les semaines de travail sont configurées "du lundi au vendredi".
Il se peut que vous deviez modifier toutes les instances de `tp.date.weekday` dans les modèles, ainsi que le modèle Monthly.

## Comment je l'utilise
Tous les jours, j'écris des choses :
- Ce que je prévois de faire
- Ce que j'ai appris
- Ce que j'ai réalisé
- Ce qui m'a posé problème
- Ce que je prévois pour l'avenir (le jour suivant ou une autre période)

À la fin de la journée, je résume les éléments les plus importants dans la rubrique "Résumé".

À la fin de la semaine, j'ouvre la note hebdomadaire, je jette un coup d'œil sur les résumés combinés de chaque jour et je résume ma semaine.
Puis mon mois, mon trimestre (quarter), mon année...

Cela m'aide à garder une trace de ce que j'ai fait et de ce que j'ai l'intention de faire, et peut m'aider à faire le point sur les ressources humaines.
Cela peut aider à rédiger un [brag document](https://jvns.ca/blog/brag-documents/).


## Contributions
TODO ;
TL;DR=contribuez sous la forme qui vous convient. Je lis les issues et les PR
