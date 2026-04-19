---
name: import
description: Import intelligent note par note : routage IA + passage Bruce Lee (garder ou archiver)
---

# Import Intelligent — Note par Note

Tu vas analyser chaque note de `Second Cerveau/_Import/` pour la router vers le bon endroit du vault, avec un passage **Bruce Lee** : « Absorb what is useful, discard what is useless. » — qu'est-ce qui t'aide encore aujourd'hui, et qu'est-ce qui peut aller à l'archive ?

**Dossier source :** `Second Cerveau/_Import/` (l'utilisateur y dépose tout ce qu'il veut importer).

## Étape 1 — État des lieux du vault

Avant toute chose, lis le contexte utilisateur pour savoir où router les notes :

1. **Contexte perso :** `Second Cerveau/2 CASQUETTES/Sur ma vie/Moi.md`
2. **Phase active :** détecte dynamiquement
   ```bash
   ls -d "Second Cerveau/2 CASQUETTES/Sur ma vie/Life Phases/"*/ | sort -V | tail -1
   ```
   Puis lis son `[N] Intention.md` pour comprendre les objectifs actuels.
3. **Projets actifs :** liste tous les dossiers dans `Second Cerveau/1 PROJETS/` et lis chaque note de contexte (`Second Cerveau/1 PROJETS/[X]/[X].md`)
4. **Casquettes :** liste tous les dossiers dans `Second Cerveau/2 CASQUETTES/` et lis chaque note de contexte

**Produis un résumé compact** (interne, pour toi) :

```
Contexte utilisateur :
- Prénom : [Prénom]
- Phase active : [Nom] — Focus : [résumé 1 ligne]

Projets actifs ([X]) :
- [Projet 1] : [1 ligne de description + état]
- [Projet 2] : [1 ligne + état]
...

Casquettes ([Y]) :
- [Casquette 1] : [1 ligne]
- [Casquette 2] : [1 ligne]
...
```

Ce résumé te servira de table de routage pour l'analyse note par note.

## Étape 2 — Scan de `Second Cerveau/_Import/`

1. **Liste tous les fichiers** dans `Second Cerveau/_Import/` (récursif).
2. **Compte-les** et affiche le total.
3. **Présente le plan à l'utilisateur** :

```
J'ai trouvé [X] notes dans Second Cerveau/_Import/.

Je vais procéder en 3 phases :
1. Analyse note par note (lance des sous-agents en parallèle, ~50 notes par batch)
2. Passage Bruce Lee : pour chaque note, je tranche entre « encore utile » ou « archive »
3. Plan de routing détaillé soumis à ta validation avant exécution

On y va ? (oui/non)
```

## Étape 3 — Analyse en parallèle (sous-agents, 50 par batch)

Découpe la liste des notes en **batches de ~50**. Pour chaque batch, lance **un sous-agent** via l'outil `Agent` (en parallèle si plusieurs batches).

### Prompt à passer à chaque sous-agent

```
Tu analyses un batch de notes à importer dans un vault Obsidian IPCRA.

**Contexte du vault (table de routage) :**
[Coller ici le résumé produit à l'Étape 1 : phase active, projets, casquettes]

**Ton job :** pour chacune des notes listées ci-dessous, lis son contenu et produis un objet JSON avec :

- `source` : chemin relatif depuis la racine du vault
- `title` : titre de la note
- `summary` : 1-2 phrases sur ce que contient la note
- `created_hint` : date probable (d'après le nom, la frontmatter, ou le contenu) ou « inconnu »
- `bruce_lee` : « keep » (encore utile aujourd'hui) ou « archive » (obsolète, curiosité, projet terminé)
- `bruce_lee_reason` : 1 ligne pour justifier le verdict
- `destination` : un des chemins suivants
  - `Second Cerveau/1 PROJETS/[Nom exact d'un projet actif]/`
  - `Second Cerveau/2 CASQUETTES/[Nom exact d'une casquette]/`
  - `Second Cerveau/3 RESSOURCES/` (référence intemporelle, lecture, framework)
  - `Second Cerveau/5 ARCHIVE/` (si bruce_lee = archive)
  - `Second Cerveau/0 INBOX/` (uniquement si vraiment impossible à router)
- `rename_suggestion` : nom de fichier propre (ou null si pas besoin de renommer)
- `confidence` : « high » / « medium » / « low »
- `notes` : remarques pertinentes (doublon détecté, à fusionner avec X, sensible, etc.)

**Règles Bruce Lee :**
- « keep » si : concerne un projet/casquette actif, apporte une info encore utile, note de référence intemporelle
- « archive » si : projet terminé, info périmée, date > 2 ans sans lien avec le présent, brouillon vide, doublon
- En cas d'hésitation → « keep » en Second Cerveau/3 RESSOURCES/ (on peut toujours archiver plus tard)

**Règles de routage :**
- Préfère rattacher à un projet/casquette existant plutôt que créer un nouveau dossier
- Si une note semble vouloir une nouvelle casquette : note-le dans `notes`, route en Second Cerveau/0 INBOX/ pour décision humaine
- Second Cerveau/0 INBOX/ doit rester une exception (< 5% du total)

Retourne un tableau JSON strict, un objet par note.

**Notes à analyser :**
[Liste des chemins des notes du batch]
```

### Récupération des résultats

Agrège les JSON de tous les sous-agents en une seule liste. Garde cette liste en mémoire pour l'Étape 4.

## Étape 4 — Présentation du plan de routing

Présente à l'utilisateur un plan **détaillé et regroupé** par destination, avec le verdict Bruce Lee.

Format :

```
## Plan de routing — [X] notes analysées

### Bruce Lee — vue d'ensemble
- **Keep** : [X] notes
- **Archive** : [Y] notes

---

### → Second Cerveau/1 PROJETS/[Nom du projet 1] ([N] notes)
| Note source | → Destination | Bruce Lee | Note |
|---|---|---|---|
| `Second Cerveau/_Import/xxx.md` | `Second Cerveau/1 PROJETS/[Projet]/[xxx renommé].md` | keep | [raison] |
| ... | ... | ... | ... |

### → Second Cerveau/2 CASQUETTES/[Casquette 1] ([N] notes)
[idem tableau]

### → Second Cerveau/3 RESSOURCES/ ([N] notes)
[idem tableau]

### → Second Cerveau/5 ARCHIVE/ ([N] notes)
> Ces notes vont être archivées parce qu'elles ne servent plus (Bruce Lee).
| Note source | Bruce Lee reason |
|---|---|
| ... | ... |

### → Second Cerveau/0 INBOX/ ([N] notes) — décisions humaines
> Ces notes n'ont pas pu être routées automatiquement.
| Note | Pourquoi |
|---|---|

### Alertes détectées
- Doublons potentiels : [liste si détectée par les sous-agents]
- Candidats nouvelle casquette : [liste si détectée]
- Notes à fusionner : [liste]

---

**Tu veux :**
a) Tout exécuter tel quel
b) Ajuster certains routages (dis-moi lesquels)
c) Voir en détail le contenu d'une ou plusieurs notes avant de décider
```

## Étape 5 — Ajustements (si l'utilisateur choisit b ou c)

- **Option b** : l'utilisateur dit « déplace la note X vers Y ». Modifie la liste en mémoire.
- **Option c** : affiche le contenu brut des notes demandées, puis repropose le plan ajusté.

Boucle jusqu'à ce que l'utilisateur valide (option a).

## Étape 6 — Exécution

Une fois validé :

1. **Crée les dossiers de destination** manquants (si une note va dans un nouveau projet/casquette, demande confirmation avant de créer le dossier).
2. **Déplace chaque note** vers sa destination, en renommant si `rename_suggestion` est donné.
3. **Nettoie** les dossiers vides dans `Second Cerveau/_Import/`.

Pas de log externe — `/done` loggera un résumé dans la daily note du jour.

## Étape 7 — Récap final

```
Import terminé.

**Résumé :**
- [X] notes → Second Cerveau/1 PROJETS/
- [X] notes → Second Cerveau/2 CASQUETTES/
- [X] notes → Second Cerveau/3 RESSOURCES/
- [X] notes → Second Cerveau/5 ARCHIVE/ (Bruce Lee : discard)
- [X] notes → Second Cerveau/0 INBOX/ (décisions reportées)

**Bruce Lee :** [X] gardées (utiles), [Y] archivées (obsolètes).

Second Cerveau/_Import/ est [vide / nettoyé].

Prochaines étapes suggérées :
- [ ] Traiter les [X] notes en Second Cerveau/0 INBOX/ via `/inbox-processor`
- [ ] Lance `/done` pour logger la session dans ta daily note
```

## Principes

**1. Note par note, pas en vrac.** Chaque note passe par un sous-agent qui lit son contenu.

**2. Bruce Lee tranche systématiquement.** Keep ou archive. Pas de « peut-être ».

**3. L'utilisateur valide avant exécution.** Plan détaillé → ajustements → go.

**4. Routage vers l'existant d'abord.** On ne crée pas de nouveau projet/casquette sans demander.

**5. Parallélisation.** Si plus de 50 notes, lancer les sous-agents en parallèle (1 batch = 1 sous-agent, un seul message avec plusieurs appels Agent).

**6. `Second Cerveau/0 INBOX/` est une exception.** Si un sous-agent y route > 10% des notes, c'est qu'il manque de contexte — affiner le résumé de l'Étape 1.
