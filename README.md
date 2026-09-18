# Agents consommateurs

Sous-agents Claude Code qui incarnent une cible précise et réagissent aux
contenus, offres, campagnes et expériences comme de véritables consommateurs.

## Fichiers

| Agent | Fichier | Rôle |
| --- | --- | --- |
| `agent-consommateur` | `.claude/agents/agent-consommateur.md` | Agent générique. On lui décrit une entreprise et une cible, il construit son identité puis analyse les contenus. |
| `klesis-parent-helicoptere` | `.claude/agents/klesis-parent-helicoptere.md` | Déclinaison KLESIS Junior. Incarne la mère « Parent hélicoptère », identité déjà construite et validée. |

Les deux agents partagent la même configuration :

| Champ | Valeur |
| --- | --- |
| `model` | `sonnet` |
| `tools` | `Read, Glob, Grep` (lecture seule — aucun outil d'écriture, d'édition, de suppression ou d'exécution) |
| Mémoire persistante | non activée |

### klesis-parent-helicoptere — ce qu'il contient

Fiche d'identité validée (mère 35-45 ans, CSP+, urbaine, 1-2 enfants de 6-12 ans),
9 objections classées, réaction aux 6 piliers KLESIS, points de friction
structurels, et deux grilles de leviers émotionnels :

- **Sept péchés capitaux**, classés du plus au moins activable : orgueil (vicariant,
  le plus puissant) · envie (à double tranchant) · colère · avarice (aversion à la
  perte) · paresse (à reformuler en soulagement de charge mentale) · gourmandise ·
  luxure.
- **Quatre hormones**, par ordre de priorité : endorphine (soulagement de la
  douleur — le levier différenciant) · ocytocine · sérotonine · dopamine (à doser).

Un garde-fou est inscrit dans la fiche : sur un profil anxieux et culpabilisé, un
contenu qui active frontalement la peur ou la culpabilité ne convertit pas, il fait
fuir.

Le protocole d'analyse A→K impose de nommer à chaque fois le péché visé et activé,
l'hormone visée et produite, et l'écart entre les deux. Deux scores supplémentaires :
« capacité à me faire préférer KLESIS au sport » et « capacité à produire de
l'endorphine ».

Faits de référence : offre EFL à 1 250 €, paiement jusqu'à 6 fois, deux dates
d'entrée (septembre ou janvier), alternative concurrente = le sport, décision
majoritairement maternelle.

Informations encore manquantes, à compléter dans le fichier quand elles seront
connues : modalités exactes du paiement échelonné, type et budget du sport
pratiqué, contenu d'une séance type, nombre de séances par pilier, témoignages
nommés.

## Installation globale (tous les projets, toutes les entreprises)

Copier le fichier dans le répertoire des agents utilisateur :

```bash
mkdir -p ~/.claude/agents
cp .claude/agents/*.md ~/.claude/agents/
```

Un agent placé dans `~/.claude/agents/` est disponible dans **toutes** les sessions
Claude Code, quel que soit le projet ou le dépôt courant.

## Utilisation

Claude délègue automatiquement quand une demande correspond à la description d'un
agent. On peut aussi les invoquer explicitement :

> Utilise l'agent-consommateur pour tester ce script de publicité auprès de notre cible.

> Utilise klesis-parent-helicoptere pour tester cette publication Instagram.
