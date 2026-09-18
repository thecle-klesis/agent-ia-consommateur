# Agents consommateurs

Sous-agents Claude Code qui incarnent une cible précise et réagissent aux
contenus, offres, campagnes et expériences comme de véritables consommateurs.

## Fichiers

| Agent | Fichier | Rôle |
| --- | --- | --- |
| `agent-consommateur` | `.claude/agents/agent-consommateur.md` | Agent générique. On lui décrit une entreprise et une cible, il construit son identité puis analyse les contenus. |
| `klesis-parent-helicoptere` | `.claude/agents/klesis-parent-helicoptere.md` | Sociostyle 1. Incarne la mère « Parent hélicoptère » : anxieuse, protectrice, arbitre face au sport. |
| `klesis-parent-life-skills` | `.claude/agents/klesis-parent-life-skills.md` | Sociostyle 2. Incarne le Parent « life skills » : convaincu, exigeant, prospect froid qui applique déjà sa propre pédagogie. |

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

### klesis-parent-life-skills — ce qu'il contient

Profil opposé au précédent : ce parent n'est **pas en recherche**. Il a une
conviction éducative qu'il applique déjà seul, et c'est un prospect froid. Enfant
de moins de 13 ans, décision prise en couple avec un poids fort du père.

Le fichier conserve un **agenda de test** : cinq hypothèses concurrentes (H1 à H5)
expliquant pourquoi un parent convaincu de faire le travail lui-même accepterait de
payer un tiers, chacune avec la question d'entretien et le signal de vente qui
permettent de la trancher. Aucune n'est validée.

Leviers émotionnels : orgueil **direct** (et non vicariant) en tête, puis avarice en
version ROI. Hormones dans l'ordre inverse du profil hélicoptère — **dopamine**
d'abord, endorphine en dernier. Trois scores dédiés : « capacité à me montrer ce que
je ne fais pas déjà », « capacité à convaincre aussi mon conjoint », « capacité à
transformer mon approbation en action ».

### Le contraste entre les deux profils

| | Parent hélicoptère | Parent life skills |
| --- | --- | --- |
| Posture | En recherche, inquiet | Prospect froid, convaincu |
| Fierté | Vicariante (via l'enfant) | Directe (sa méthode) |
| Concurrent | Le sport | Lui-même |
| Hormone n°1 | Endorphine (soulager) | Dopamine (faire progresser) |
| Décideur | Majoritairement la mère | Couple, le père pèse |
| Piège | Le culpabiliser | Lui répéter ce qu'il fait déjà |

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
