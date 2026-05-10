---
name: weekly-review
description: Weekly review : bilan + priorisation par énergie
---

# Weekly Review

Bilan de la semaine, carry-forward des tâches non complétées, organisation par énergie, priorisation.

## Process

### Étape 1 : Lire le contexte
Lis `Second Cerveau/2 CASQUETTES/Sur ma vie/Moi.md` pour comprendre l'utilisateur. Lis aussi les daily notes de la semaine dans la phase active pour avoir le contexte des sessions récentes.

### Étape 2 : Détecter la phase active et la semaine
```bash
PHASE_DIR=$(ls -d "Second Cerveau/2 CASQUETTES/Sur ma vie/Life Phases/"*/ 2>/dev/null | sort -V | tail -1)
PHASE_NAME=$(basename "$PHASE_DIR")
CURRENT_WEEK=$(date +%Y-W%V)
PREV_WEEK=$(date -v-7d +%Y-W%V 2>/dev/null || date -d "7 days ago" +%Y-W%V)
echo "Phase: $PHASE_NAME | Semaine: $CURRENT_WEEK | Précédente: $PREV_WEEK"
```

### Étape 3 : Carry-forward des tâches non complétées
Lire la weekly note précédente (`$PREV_WEEK.md`) dans la phase active. Extraire toutes les lignes `- [ ]` (tâches non complétées). Les garder pour ré-injection dans la nouvelle note. Si la note précédente n'existe pas, passer cette étape.

### Étape 4 : Scanner l'activité de la semaine
```bash
find . -type f -name "*.md" -mtime -7 2>/dev/null | grep -v ".git" | head -50
```
Scanner en particulier les dossiers `Second Cerveau/1 PROJETS/`, `Second Cerveau/2 CASQUETTES/`, `Second Cerveau/0 INBOX/`. Présenter un résumé rapide de ce qui a bougé.

### Étape 5 : Brain dump
Poser la question :
> Comment s'est passée ta semaine ? Qu'est-ce qui a avancé, qu'est-ce qui a bloqué, qu'est-ce qui a émergé ?

Attendre la réponse. Extraire les éléments clés.

### Étape 6 : Organiser par énergie
Classer TOUTES les tâches (carry-forward + nouvelles) en 3 catégories :
- **Deep Focus** : travail technique, écriture longue, apprentissage profond, réflexion stratégique
- **Créatif** : contenu, design, idéation, vidéos, présentations, brainstorming
- **Admin** : emails, compta, organisationnel, logistique, réunions, rangement

Grouper par projet/casquette à l'intérieur de chaque catégorie. Présenter la classification et attendre validation.

### Étape 7 : Priorités de la semaine suivante
Demander :
> Quelles sont tes 2-3 priorités pour la semaine prochaine ?

### Étape 8 : Générer la weekly note
Créer `YYYY-WXX.md` dans la phase active avec ce format :

```markdown
---
type: weekly
week: YYYY-WXX
phase: "[Phase name]"
---
# YYYY-WXX (DD-DD mon)

## Bilan
- Avancé : ...
- Bloqué : ...
- Émergent : ...

## Deep Focus
### [[Projet ou Casquette]]
- [ ] Tâche

## Créatif
### [[Projet ou Casquette]]
- [ ] Tâche

## Admin
### [[Projet ou Casquette]]
- [ ] Tâche

## Questions ouvertes

## Prochaines échéances
```

### Étape 9 : Confirmation
Afficher un résumé : nombre de tâches carry-forward, nouvelles tâches, répartition Deep Focus / Créatif / Admin, top 2-3 priorités.

## Output Style
- En français
- Concis, pas de blabla
- Interactif (attend les réponses)
- Pas d'emojis
