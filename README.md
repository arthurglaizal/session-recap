# Session Recap

> **Récapitule ta session Claude Code d'un coup d'œil.**

Session Recap est une commande slash minimale pour Claude Code qui génère un récapitulatif lisible de la session de travail en cours : ce qui a été fait, dans quel ordre, où en est le projet, et quoi reprendre la prochaine fois.

## Pourquoi ?

Une session Claude Code peut vite s'étaler sur plusieurs chantiers, corrections et décisions. Sans récap, il est facile de perdre le fil : qu'est-ce qui a été fait, dans quel ordre, qu'est-ce qui reste ouvert.

Session Recap relit la conversation en cours et produit un compte rendu structuré, pour reprendre le travail rapidement — dans la session actuelle ou la suivante.

## Utile pour

Session Recap est utile quand tu veux :

* Revoir rapidement ce qui a été fait pendant une session.
* Comprendre le déroulé chronologique d'une session longue.
* Savoir clairement où en est le projet à l'instant T.
* Identifier quoi reprendre à la prochaine session.

## Comment l'utiliser

Dans une session Claude Code, tape :

```txt
/session-recap
```

## Ce que fait la commande

La commande couvre le travail effectué depuis le dernier récap généré dans la conversation, ou à défaut depuis le début de la conversation. Elle ne résume pas tout l'historique du projet, et n'invente ni actions, ni décisions, ni horodatages.

Elle produit quatre sections :

* **Résumé de la session** — deux phrases de vue d'ensemble.
* **Déroulé de la session** — un tableau chronologique par sujet, avec horodatage.
* **Où en est le projet ?** — un tableau `✅ En place` / `🚧 À poursuivre` / `❓ À décider`.
* **👉 Prochaine étape** — une seule phrase sur l'action la plus logique à entreprendre ensuite.

Pour une session longue, le récap regroupe les actions liées en sujets significatifs plutôt que de tout journaliser : les commandes triviales, explorations sans conséquence et tentatives abandonnées sans impact sont ignorées.

## Limitations

Session Recap ne modifie aucun fichier du projet : elle produit uniquement un texte récapitulatif.

Le récap est fondé uniquement sur le contexte réellement disponible dans la conversation Claude Code en cours. Il ne connaît pas les sessions passées qui ne font pas partie du contexte actuel, et n'invente jamais d'horodatage qu'il ne peut pas déterminer de façon fiable.

## Installer dans Claude Code

### Méthode 1 : copier le fichier de commande

Copie [session-recap.md](.claude/commands/session-recap.md) dans le dossier `.claude/commands/` de ton projet.

### Méthode 2 : installation via Claude Code

Tu peux demander à Claude Code de faire l'installation à ta place. Colle ce prompt dans une session Claude Code :

[install-session-recap-for-claude-code.md](prompts-for-installation/install-session-recap-for-claude-code.md)

## Utiliser dans un chat IA classique (ChatGPT, Claude, Gemini…)

Si tu veux juste utiliser Session Recap dans un chat classique, sans l'installer dans un projet ou un outil de code, colle cette version dans une conversation :

[session-recap-ai-chat-version.md](prompts-for-ai-chat/session-recap-ai-chat-version.md)

Une fois collée, écris exactement `recap` à tout moment de la conversation pour obtenir le récapitulatif de la session en cours. Tu peux le redemander plusieurs fois : chaque récap ne couvre que ce qui s'est passé depuis le précédent.

Cette instruction ne s'applique qu'à la conversation en cours. Si tu ouvres une nouvelle conversation, colle-la à nouveau.

## Structure du dépôt

```txt
session-recap/
├── README.md
├── LICENSE
├── .gitignore
├── .claude/
│   └── commands/
│       └── session-recap.md
├── prompts-for-installation/
│   └── install-session-recap-for-claude-code.md
└── prompts-for-ai-chat/
    └── session-recap-ai-chat-version.md
```
