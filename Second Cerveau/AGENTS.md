# Perspectives IA — Instructions Agent

## À propos de ce vault

Ce vault est organisé selon la méthode **IPCRA** (Inbox, Projets, Casquettes, Ressources, Archive).

**Structure :**
```
0 INBOX/        → Capture rapide, traitement en attente
1 PROJETS/      → Projets actifs (1 dossier par projet)
│   └── Mon Projet/
│       └── Mon Projet.md (note de contexte)
2 CASQUETTES/   → Responsabilités ongoing (1 dossier par casquette)
│   ├── Sur ma vie/
│   │   ├── Moi.md (qui je suis, style IA, valeurs)
│   │   ├── Mon Parcours.md (historique chronologique)
│   │   └── Life Phases/
│   │       ├── Life Phases.md (note de contexte)
│   │       └── 1 Ma phase/
│   │           ├── 1 Intention.md
│   │           ├── YYYY-MM-DD.md (daily notes = logs de session)
│   │           └── YYYY-WXX.md (weekly notes)
│   └── Entrepreneur/
│       └── Entrepreneur.md (note de contexte)
3 RESSOURCES/   → Références, inspirations, documentation
│   └── Process/
│       └── Process - [Nom].md (fiches process documentées)
4 TOOLS/        → Templates, scripts, process documentés
│   └── Templates/
5 ARCHIVE/      → Terminé ou inactif
_Import/        → Notes à reclasser (temporaire, pour migration)
```

**Important :** Les projets et casquettes sont des **dossiers** contenant une note de contexte (`type: context`) + des notes/sous-dossiers liés.

---

## Contexte de l'utilisateur

Le contexte est distribué dans le vault, pas centralisé dans un seul fichier :

| Source | Contenu | Quand la lire |
|--------|---------|---------------|
| `AGENTS.md` (ce fichier) | Structure du vault, commandes, règles | À chaque session |
| `2 CASQUETTES/Sur ma vie/Moi.md` | Qui est l'utilisateur, style IA, MBTI, valeurs | À chaque session |
| `2 CASQUETTES/Sur ma vie/Mon Parcours.md` | Historique chronologique | Quand besoin de contexte biographique |
| Intention de la phase active | Objectifs, focus, contraintes actuelles | À chaque session |
| Dernière daily note | Logs de la session précédente, prochaines étapes | À chaque session |
| Notes de contexte des casquettes | Responsabilités, état actuel | Quand tu travailles sur cette casquette |
| Notes de contexte des projets | Roadmap, progression, état | Quand tu travailles sur ce projet |

**Lis TOUJOURS au début d'une session :** ce fichier + `Moi.md` et en fonction du projet sur lequel on travaille, la note de contexte du projet / de la casquette ou la daily / weekly note / intention de phase de vie.

---

## Système Life Phases

Le vault inclut un système de **phases de vie** dans `2 CASQUETTES/Sur ma vie/Life Phases/`.

### Détection de la phase active

**Ne jamais hardcoder le numéro ou nom de phase.** Toujours détecter dynamiquement :

```bash
ls -d "2 CASQUETTES/Sur ma vie/Life Phases/"*/ | sort -V | tail -1
```

### Structure d'une phase

```
N Nom de la phase/
├── N Intention.md          # L'intention de la phase (status: active)
├── N Bilan.md              # Bilan de fin (quand terminé)
├── YYYY-MM-DD.md           # Daily notes (= logs de session IA)
├── YYYY-WXX.md             # Weekly notes (= planification)
└── [autres notes]          # Réflexions, journaling
```

### Règles Life Phases

1. **TOUT le journaling va dans le dossier de la phase active**
2. **Une seule phase peut être `active` à la fois**
3. **Format des daily notes :** `YYYY-MM-DD.md`
4. **Format des weekly notes :** `YYYY-WXX.md`
5. **Liens/idées reçus** → daily note + routage vers le projet/casquette concerné
6. **Tâches/todos reçus** → weekly note active. Préparer une note de travail liée via `[[wikilink]]` si possible
7. **Quand l'utilisateur parle de changement de cap**, proposer `/new-life-phase`

---

## Flux de contexte (Ruissellement)

Quand tu fais quelque chose, applique ce flux de mise à jour :

```
NIVEAU 1 - Action         Faire la chose (éditer, créer, organiser)
    ↓
NIVEAU 2 - Daily note     Trace dans la daily note de la phase active
                           2 CASQUETTES/Sur ma vie/Life Phases/[active]/YYYY-MM-DD.md
    ↓
NIVEAU 3 - Contexte       Update de la note du projet/casquette concerné
  Projet/Casquette         (1 PROJETS/[X]/[X].md ou 2 CASQUETTES/[X]/[X].md)
    ↓
NIVEAU 4 - Contexte       Update de Moi.md ou de l'intention de phase (avec validation)
  Personnel                2 CASQUETTES/Sur ma vie/Moi.md
                           2 CASQUETTES/Sur ma vie/Life Phases/[active]/Intention.md
```

**Règle :** Les faits vont dans les notes de projet/casquette (NIVEAU 3). La daily note (NIVEAU 2) est le log de session. Moi.md et l'intention (NIVEAU 4) ne changent que rarement et avec validation.

---

## Style de communication

- Direct et concis, pas de blabla
- TOUJOURS mettre les accents français (é, è, ê, à, â, ù, û, ô, î, ç)
- Utiliser des `[[wikilinks]]` généreusement dans les notes
- Utiliser des listes et structures claires
- Poser des questions si quelque chose n'est pas clair
- Toujours reformuler pour vérifier ma compréhension
