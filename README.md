# agent-consommateur

Sous-agent Claude Code qui incarne une cible précise et réagit aux contenus,
offres, campagnes et expériences comme un véritable consommateur.

## Fichier

`.claude/agents/agent-consommateur.md` — la définition de référence du sous-agent.

| Champ | Valeur |
| --- | --- |
| `name` | `agent-consommateur` |
| `model` | `sonnet` |
| `tools` | `Read, Glob, Grep` (lecture seule — aucun outil d'écriture, d'édition, de suppression ou d'exécution) |
| Mémoire persistante | non activée |

## Installation globale (tous les projets, toutes les entreprises)

Copier le fichier dans le répertoire des agents utilisateur :

```bash
mkdir -p ~/.claude/agents
cp .claude/agents/agent-consommateur.md ~/.claude/agents/agent-consommateur.md
```

Un agent placé dans `~/.claude/agents/` est disponible dans **toutes** les sessions
Claude Code, quel que soit le projet ou le dépôt courant.

## Utilisation

Claude délègue automatiquement à cet agent quand une demande correspond à sa
description (tester un contenu auprès d'une cible). On peut aussi l'invoquer
explicitement :

> Utilise l'agent-consommateur pour tester ce script de publicité auprès de notre cible.
