Tu génères un récapitulatif lisible de la session de travail en cours dans Claude Code.

## Portée

Couvre le travail effectué **depuis le dernier récap produit par cette commande dans cette conversation**, ou à défaut **depuis le début de la conversation**.

Si un récap précédent généré par cette commande est présent plus haut dans la conversation, ne couvre que ce qui s'est passé après ce récap.

Ne résume pas l'historique complet du projet, ni des sessions antérieures qui ne sont pas présentes dans le contexte actuel.

Si la session est longue, adapte la granularité : regroupe les actions liées en sujets significatifs plutôt que de produire un journal exhaustif. Ignore les commandes triviales, les explorations sans conséquence, les tentatives abandonnées sans impact, et les détails de faible importance.

Fonde-toi uniquement sur le contexte réellement disponible dans la conversation. N'invente ni actions, ni décisions, ni horodatages.

## Format de sortie

Produis exactement les sections suivantes, dans cet ordre, en Markdown.

### `Résumé de la session`

Écris exactement 2 phrases donnant une vue d'ensemble de la session : les principaux chantiers abordés, les changements ou décisions les plus importants, et l'état général atteint en fin de session. Ne répète pas simplement le contenu du tableau qui suit.

### `Déroulé de la session`

Tableau Markdown avec les colonnes suivantes :

`| # | Sujet | Ce qui a été fait | Heure |`

Règles :

* respecte l'ordre chronologique ;
* crée un nouveau sujet lorsqu'un chantier, un objectif ou une phase significative change ;
* adapte le nombre de lignes à la densité réelle de la session ; pour une très longue session, vise environ 8 à 12 sujets significatifs ;
* donne à chaque sujet un titre court en **gras** ;
* utilise plusieurs bullet points courts dans `Ce qui a été fait` lorsqu'un sujet contient plusieurs actions importantes, séparés par `<br>` ;
* chaque bullet décrit une action, décision, correction ou résultat concret ; évite les répétitions ;
* place l'horodatage dans la dernière colonne, en *italique*, au format `HH:MM`, correspondant au début du bloc thématique ;
* n'invente jamais un horaire si le contexte ne permet pas de le déterminer de façon suffisamment fiable ; dans ce cas, laisse la cellule vide plutôt que d'inventer.

### `Où en est le projet ?`

Tableau Markdown avec les colonnes `Statut | État` et exactement ces trois lignes, dans cet ordre :

* `✅ **En place**` : ce qui est fonctionnel, terminé, validé ou suffisamment stabilisé ;
* `🚧 **À poursuivre**` : ce qui est identifié mais encore incomplet ;
* `❓ **À décider**` : questions, arbitrages ou choix encore ouverts.

Dans chaque cellule `État`, utilise des bullet points courts séparés par `<br>`. Ne mentionne que les éléments réellement pertinents en fin de session. Ne remplis pas artificiellement une catégorie si elle n'est pas pertinente ; indique `—` dans ce cas plutôt que d'inventer du contenu.

### `👉 Prochaine étape`

Hors tableau, ajoute exactement une ligne au format :

`👉 **Prochaine étape** : ...`

Une seule phrase, indiquant l'action la plus logique à entreprendre immédiatement lors de la prochaine session. Ne répète pas toute la liste `À poursuivre`.

## Langue

Réponds dans la langue utilisée par l'utilisateur dans la conversation.

## Contraintes

* Ne modifie aucun fichier du projet : cette commande produit uniquement un texte récapitulatif.
* Ne propose pas de plan d'action ni de liste de tâches au-delà de la `Prochaine étape`.
* Reste concis et directement lisible dans Claude Code.
