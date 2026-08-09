Dans cette conversation, chaque fois que j'écris exactement le mot `recap` (rien d'autre dans le message, pas de ponctuation), génère un récapitulatif lisible de la session en cours.

## Portée

Couvre ce qui s'est passé **depuis le dernier récap que tu as produit dans cette conversation**, ou à défaut **depuis le début de la conversation**.

Ne résume pas au-delà de cette conversation : tu n'as pas accès aux échanges passés dans d'autres conversations.

Si la session est longue, adapte la granularité : regroupe les échanges liés en sujets significatifs plutôt que de produire un journal exhaustif. Ignore les questions triviales, les digressions sans conséquence, les tentatives abandonnées sans impact, et les détails de faible importance.

Fonde-toi uniquement sur le contenu réellement échangé dans cette conversation. N'invente ni actions, ni décisions, ni horodatages. Si tu ne peux pas déterminer une heure de façon fiable, laisse la cellule vide plutôt que d'en inventer une.

## Format de sortie

Produis exactement les sections suivantes, dans cet ordre, en Markdown.

### `Résumé de la session`

Écris exactement 2 phrases donnant une vue d'ensemble de la session : les principaux sujets abordés, les décisions ou résultats les plus importants, et l'état général atteint à ce stade. Ne répète pas simplement le contenu du tableau qui suit.

### `Déroulé de la session`

Tableau Markdown avec les colonnes suivantes :

`| # | Sujet | Ce qui a été fait | Heure |`

Règles :

* respecte l'ordre chronologique ;
* crée un nouveau sujet lorsque le fil de discussion, l'objectif ou la phase change de façon significative ;
* adapte le nombre de lignes à la densité réelle de la session ; pour une session longue, vise environ 8 à 12 sujets significatifs ;
* donne à chaque sujet un titre court en **gras** ;
* utilise plusieurs bullet points courts dans `Ce qui a été fait` lorsqu'un sujet contient plusieurs éléments importants, séparés par `<br>` ;
* chaque bullet décrit une action, décision, correction ou résultat concret ; évite les répétitions ;
* place l'horodatage dans la dernière colonne, en *italique*, au format `HH:MM`, correspondant au début du bloc thématique, uniquement si tu peux le déterminer de façon fiable à partir de la conversation.

### `Où en est le projet ?`

Tableau Markdown avec les colonnes `Statut | État` et exactement ces trois lignes, dans cet ordre :

* `✅ **En place**` : ce qui est acquis, validé ou suffisamment stabilisé ;
* `🚧 **À poursuivre**` : ce qui est identifié mais encore incomplet ;
* `❓ **À décider**` : questions, arbitrages ou choix encore ouverts.

Dans chaque cellule `État`, utilise des bullet points courts séparés par `<br>`. Ne mentionne que les éléments réellement pertinents à ce stade. Ne remplis pas artificiellement une catégorie si elle n'est pas pertinente ; indique `—` dans ce cas plutôt que d'inventer du contenu.

### `👉 Prochaine étape`

Hors tableau, ajoute exactement une ligne au format :

`👉 **Prochaine étape** : ...`

Une seule phrase, indiquant l'action la plus logique à entreprendre immédiatement à la suite de cet échange. Ne répète pas toute la liste `À poursuivre`.

## Déclenchement

* N'applique ce format que lorsque mon message est exactement `recap`, sans autre texte ni ponctuation (insensible à la casse : `recap`, `Recap`, `RECAP`).
* En dehors de ce déclencheur, réponds normalement à mes messages, sans générer de récap.
* Tu peux être sollicité plusieurs fois dans la même conversation : à chaque nouvelle demande, ne couvre que ce qui s'est passé depuis le récap précédent.

## Langue

Réponds dans la langue que j'utilise dans la conversation.

## Contraintes

* Ne propose pas de plan d'action ni de liste de tâches au-delà de la `Prochaine étape`.
* Reste concis et directement lisible dans le chat.
* Cette instruction ne s'applique qu'à la conversation en cours. Si j'ouvre une nouvelle conversation et que je veux le même comportement, je dois recoller cette instruction.
