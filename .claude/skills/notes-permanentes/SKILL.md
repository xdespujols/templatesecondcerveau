---
name: notes-permanentes
description: Transformer des sources (highlights, podcasts, livres) en notes atomiques permanentes (Zettelkasten), reformulées et connectées au vault.
---

# Session Notes Permanentes

Tu guides l'utilisateur dans une session de creation de notes permanentes (Zettelkasten) a partir de ses sources : highlights Readwise, podcasts deconstruits, livres, articles, ou toute autre note du vault.

Une note permanente = un concept autonome, reformule dans les mots de l'utilisateur, connecte au reste du vault.

## Avant de commencer

1. Lis le contexte de l'utilisateur (`Second Cerveau/2 CASQUETTES/Sur ma vie/Moi.md`)
2. Si un dossier `Second Cerveau/3 RESSOURCES/Zettelkasten/` existe, scanne les notes et MOC pour connaitre les themes documentes
3. Si un dossier `Second Cerveau/3 RESSOURCES/Readwise/` existe, note les sources disponibles

## Etape 1 : Choisir la source

Demande a l'utilisateur :

```
Session Notes Permanentes

Comment tu veux proceder ?
a) Je scanne tes sources recentes (Readwise, podcasts, livres) et te propose les meilleurs concepts a extraire
b) Tu me donnes une source specifique a traiter (note, livre, podcast, article)
c) On complete les notes en brouillon (stubs/drafts) existantes dans le Zettelkasten
```

## Etape 2 : Identifier les concepts

### Si option a) — Sources recentes
1. Scanne les fichiers recents dans `Second Cerveau/3 RESSOURCES/` (Readwise, Podcasts, Livres)
2. Identifie les passages riches en concepts (pas les simples citations)
3. Propose 3-5 concepts extractibles, avec pour chacun :
   - Le concept en une phrase
   - La source
   - Un lien potentiel avec une note existante

### Si option b) — Source specifique
1. Lis la source demandee
2. Identifie TOUS les concepts extractibles
3. Propose-les groupes par theme

### Si option c) — Completer l'existant
1. Lis les stubs et drafts du Zettelkasten
2. Cherche dans les sources des highlights pertinents pour les completer
3. Propose du contenu pour chaque note incomplete

**→ Attendre validation de l'utilisateur avant de creer.**

## Etape 3 : Creer les notes permanentes

Pour chaque concept valide par l'utilisateur :

### 3.1 — Creer la note

Emplacement : `Second Cerveau/3 RESSOURCES/Zettelkasten/`

```markdown
---
type: permanent
status: complete
source: [[Nom de la source]]
MOC: [[MOC pertinente]]
created: [date]
---

# [Titre du concept]

[Le concept reformule dans les mots de l'utilisateur — 5-10 lignes, autonome et comprehensible sans contexte]

---

## References

> [Citation originale ou passage cle de la source]
— *[Source]*

## Liens

- [[Note existante 1]] — [type de relation : renforce, nuance, contredit, complete]
- [[Note existante 2]] — [type de relation]

## Notes connexes

- [Suggestion de connexion avec d'autres themes du vault]
```

### 3.2 — Mettre a jour la MOC

Si une MOC pertinente existe dans `Second Cerveau/3 RESSOURCES/Zettelkasten/MOC/`, ajouter la nouvelle note.
Si aucune MOC ne correspond, proposer d'en creer une.

### 3.3 — Proposer des connexions

Scanner le Zettelkasten et le vault pour des notes liees :
- Types de relation : renforce, nuance, contredit, complete, applique
- Ne forcer aucune connexion — seulement les liens reels

## Etape 4 : Resume de session

```
Session terminee !

**Notes creees :** [X]
**Notes completees :** [X]
**MOC mises a jour :** [liste]

Veux-tu :
a) Continuer avec d'autres concepts de la meme source ?
b) Traiter une autre source ?
c) C'est bon pour maintenant ?
```

## Regles

- **Une note = un concept** (atomicite) — si une note couvre 2 idees, la decouper
- **Max 1 ecran** par note (~200-500 mots)
- **Toujours reformuler** dans les mots de l'utilisateur, jamais copier-coller le highlight brut
- **Toujours lier** a au moins une MOC et proposer des connexions
- **Demander validation** avant de creer chaque note (montrer le contenu propose)
- **Style de l'utilisateur** — lire `Moi.md` et le referentiel style s'il existe
- Les notes vont dans `Second Cerveau/3 RESSOURCES/Zettelkasten/`, les MOC dans `Second Cerveau/3 RESSOURCES/Zettelkasten/MOC/`
