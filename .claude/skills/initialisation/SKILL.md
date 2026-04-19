---
name: initialisation
description: Initialiser le vault Perspectives IA via conversation guidée. Pédagogie IPCRA, décharge projets/casquettes/contexte, dépôt de documents à tout moment (CV, bios, offres écrites…), création complète de la structure et des fichiers de contexte personnalisés.
---

# Initialisation du Vault Perspectives IA

Tu initialises ce vault avec les informations de l'utilisateur via une conversation guidée. En même temps, tu **expliques** ce qu'on met en place et pourquoi — l'utilisateur comprend ce qu'il fait, pas seulement ce qu'il remplit.

## Règle transversale — dépôt de documents

**À tout moment** pendant les étapes de décharge (Étapes 3 à 7), l'utilisateur peut déposer des fichiers pour compléter ou remplacer la réponse vocale/écrite : CV, bios historiques, notes de parcours, offres écrites, briefs clients, archives de réunions, journal intime, anciens coachings, etc.

À chaque grande étape, rappelle cette affordance :

> « Tu peux aussi me déposer ici des fichiers (PDF, docs, notes) qui couvrent cette section — CV, bio, historique, offres écrites, anciens docs. Je les lis et j'en extrais ce qui compte. »

Quand un fichier est déposé :
1. **Lis-le intégralement** (via Read pour les .md/.txt, via les outils PDF pour les .pdf, etc.)
2. **Extrais** les informations pertinentes pour la section en cours
3. **Résume** à l'utilisateur ce que tu as compris et demande validation ou compléments
4. **Continue** la section avec les gaps restants (si le document n'a pas tout couvert)

---

## Étape 1 — Prélude pédagogique (explique le système)

Dis à l'utilisateur (adapte le ton, ne le récite pas mot pour mot — formule en conversant) :

```
Bienvenue. On va initialiser ton second cerveau.

## Où on est

Tu es dans un WORKSPACE — un dossier parent qui peut héberger plusieurs projets.
Pour l'instant il contient juste ton second cerveau (dossier `Second Cerveau/`).
Plus tard, si tu veux, tu pourras y ajouter d'autres projets à côté : un site web,
une app, un repo client, un repo partagé avec ton équipe… et l'IA y aura accès
depuis le même endroit.

Aujourd'hui on se concentre sur le second cerveau.

## Le deal

Ce que je te propose de faire maintenant, en trois temps :

  1. Je te présente ce qu'on met en place et pourquoi (5 min)
  2. Tu décharges : tout ce qu'il faut pour peupler ton contexte (20-40 min, adaptable)
  3. Je génère la structure complète de ton vault + tes fichiers de contexte

Tu peux répondre à l'écrit, à l'oral (SuperWhisper), ou me déposer des documents
à chaque étape. On prend le temps qu'il faut.

## Pourquoi un second cerveau

La puissance de l'IA émerge de TON contexte.

  → IA sans contexte    = réponses génériques, réinvente la roue à chaque prompt,
                          ne te connaît ni toi, ni tes projets, ni tes clients.

  → IA avec ton contexte = extension de toi-même, connaît tes projets, tes offres,
                          ta vie. Exécute dans ton cadre, pas hors-sol.

L'équation : **Qualité IA = Qualité du contexte × Qualité du modèle**.
Le modèle, tu le choisis une fois. Le contexte, on le construit maintenant.

## IPCRA — organiser par utilité

La vraie question, c'est pas « de quoi ça parle ? » mais « à quoi ça sert ? »

  ❌ Par thématique (Marketing, Finance, Santé, Famille)
     → tu cherches partout, tout se mélange, l'IA se perd.

  ✅ Par utilité (IPCRA)
     → tu vois tout de suite ce qui est actionnable vs ce qui dort.

Les 5 dossiers IPCRA :

  0 INBOX       Tout ce qui arrive, avant tri. Tampon temporaire.
  1 PROJETS     Ce sur quoi tu bosses activement (deadline → archive après).
  2 CASQUETTES  Tes rôles permanents (CEO, parent, santé, créateur…).
  3 RESSOURCES  Référence utile mais inactive.
  4 TOOLS 
  5 ARCHIVE     Terminé ou inactif (mais accessible).

### Projet vs Casquette — la distinction clé

  PROJET      = temporaire, a une deadline, un output défini.
                Ex : « Lancer le podcast », « Refonte site ». Deadline → archive.

  CASQUETTE   = permanent, une aire de responsabilité, pas de fin.
                Ex : « CEO de X », « Santé », « Finances perso ». Ça vit tout le temps.

## Le principe qu'on ne lâche jamais

**On amplifie, on ne remplace pas.**
On ne te crée pas de nouveaux usages externes. On mappe ce que tu fais déjà —
qui produit de la valeur — et on l'amplifie avec l'IA.

---

Des questions sur tout ça avant qu'on commence ? Sinon, on attaque avec « Qui tu es ».
```

Attends une confirmation ou une question. Réponds aux questions. Puis enchaîne sur l'Étape 2.

---

## Étape 2 — Nommer l'IA

**Avant toutes les décharges**, pose deux questions :

```
1. Comment tu veux que je t'appelle ? (prénom ou surnom — je vais l'utiliser tout le temps)
2. Et moi, comment tu veux que je m'appelle ? (tu donnes un nom à ton IA, c'est elle
   que tu invoqueras quand tu ouvriras ton vault)
```

Une fois les deux noms recueillis :
- Le **prénom** de l'utilisateur → sera stocké dans `Second Cerveau/2 CASQUETTES/Sur ma vie/Moi.md` (Étape 12)
- Le **nom de l'IA** → sera stocké dans **l'`AGENTS.md` à la racine du WORKSPACE** (pas celui du vault) — c'est l'identité globale de l'IA, valable pour tous les projets WORKSPACE, pas seulement le vault

---

## Étape 3 — Section 01 : Qui tu es

Annonce :

```
On attaque par « Qui tu es ». C'est la section la plus importante — prends le temps.
Tu peux me déposer des PDF, ton CV, des bios, des docs qui remontent ton parcours.
J'en extrais ce qui compte et on complète ensemble avec ce qui manque.
```

Pose ces questions **une par une**, attends la réponse entre chaque :

1. **Raconte-moi ton parcours.** Les étapes clés, les tournants, les chiffres importants. Sois précis — dates, entreprises, CA, équipes, durées. Pas « j'ai lancé une boîte » mais « J'ai lancé [Nom] en 2019, CA année 1 : 20k, année 2 : 80k, solo jusqu'en 2021 puis équipe de 3 ».

2. **Comment tu fonctionnes ?** Forces, faiblesses, façon de prendre des décisions (analyse / intuition / consultation), gestion du stress. Si tu connais ton MBTI → donne-le. Sinon [16personalities.com](https://www.16personalities.com/fr) prend 10 min.

3. **Passions, intérêts actuels, grandes convictions.** Les sujets sur lesquels tu peux passer des heures. Sois précis : pas « la tech » mais « les systèmes de pensée augmentée, les PKM, l'IA appliquée au knowledge management ».

Après chaque réponse : reformule ce que tu as compris en 2-3 phrases, demande si c'est juste, puis passe à la question suivante. Rappelle discrètement à l'utilisateur qu'il peut déposer un document ou répondre à voix haute (SuperWhisper).

---

## Étape 4 — Section 02 : Ta vision

Annonce :

```
Maintenant, ta vision. Sans vision claire, tu subis les opportunités au lieu de les
choisir — la vision, c'est le phare qui guide tes décisions.

Ici aussi tu peux déposer des docs : manifeste perso, notes de vision, feuille de
route long-terme, si tu en as.
```

Pose **une par une** :

1. **Décris ta journée idéale**, du réveil au coucher. Sois concret : heures, activités, lieux, qui est avec toi, quelle énergie.

2. **Projette-toi à 12 mois.** Tout s'est bien passé. Qu'est-ce qui s'est passé ? Concrètement — métriques, événements, relations, état d'être.

3. **À 5 ans ?** Même exercice. Qu'est-ce que tu vois ?

4. **3 à 5 actions quotidiennes essentielles pour être heureux.** Pas des valeurs abstraites — des actions concrètes qui, si tu les fais, font que ta journée est bonne.

---

## Étape 5 — Section 03 : Décharge Casquettes

Annonce :

```
On décharge tes casquettes. Rappel : une casquette = une aire de responsabilité
permanente, pas de deadline.

Exemples : CEO de [ta boîte], Papa, Santé, Finances perso, Ami proche, Créateur.
La plupart des gens ont entre 3 et 7 casquettes.

Liste-les moi d'abord — juste les noms. Ensuite on remplit 6 champs par casquette.
Et si tu as des docs pertinents (descriptions de rôle, OKR ongoing, etc.), dépose-les.
```

### 5.1 — Lister les casquettes

L'utilisateur liste ses casquettes. Tu les reformules pour validation avant d'attaquer le remplissage.

### 5.2 — Par casquette : conversation ouverte

**Pour chaque casquette, une par une**, ouvre avec cette question :

> « Parle-moi de [Casquette]. En quoi ça consiste pour toi concrètement ? Quel est ton rôle là-dedans ? »

Écoute la réponse. Pose ensuite des **questions de clarification adaptées à ce que tu entends** — pas de checklist figée. L'objectif n'est pas de remplir un formulaire mais de capturer ce qui permettra à l'IA de t'aider sur cette casquette demain.

**Banque d'inspiration** (à piocher selon ce qui manque, pas à dérouler mécaniquement) :
- Qu'est-ce que « bien tenir cette casquette » veut dire pour toi ?
- Qu'est-ce que tu fais régulièrement dans ce rôle ? (quotidien / hebdo / mensuel)
- Qui est impliqué autour de toi ? (équipe, proches, prestataires…)
- Quels outils tu utilises ?
- Qu'est-ce qui est pénible ou dysfonctionnel en ce moment ?
- Qu'est-ce que tu veux changer ou améliorer dans cette zone ?

Rappelle l'affordance document : « Tu peux aussi me déposer ici des docs liés à cette casquette (descriptions de rôle, OKR, notes historiques) — je les intègre. »

**Suis l'énergie de la réponse** : si une question tombe à plat, passe à autre chose. Si une réponse ouvre une piste riche, creuse-la. Reformule brièvement à la fin pour validation, puis passe à la casquette suivante.

Sauvegarde tout en mémoire pour l'Étape 10.

---

## Étape 6 — Section 04 : Décharge Projets

Annonce :

```
Maintenant tes projets actifs et futurs. Rappel : un projet a une fin, une deadline
(même floue). Quand c'est fini → ça va en archive.

Liste-les d'abord. Pour chacun ensuite, 7 questions. Dépose tes docs projet existants
si tu en as (brief, roadmap, offres écrites…).
```

### 6.1 — Lister les projets

### 6.2 — Par projet : conversation ouverte

**Pour chaque projet, un par un**, ouvre avec :

> « Parle-moi de [Projet]. De quoi il s'agit, où tu en es, qu'est-ce que tu vises ? »

Écoute la réponse. Pose ensuite des **questions de clarification adaptées** — pas une grille à remplir. Ce qu'on veut, c'est que l'IA puisse t'aider sur ce projet en comprenant son essence, son état, et ce qui bloque.

**Banque d'inspiration** (pioche selon ce qui manque, pas une checklist à dérouler) :
- Pourquoi tu le fais, toi personnellement ? (pas la justification publique)
- Quel est l'output concret ? Qu'est-ce que tu vends ou livres ?
- Quelle deadline ou horizon ?
- Qui bosse dessus avec toi ? Qui joue quoi ?
- Où tu en es exactement — dernières avancées, prochaine étape concrète ?
- Qu'est-ce qui te bloque actuellement ?
- Tâches récurrentes liées à ce projet ?

Rappelle l'affordance document : « Tu as des docs à rapatrier pour ce projet ? Briefs, roadmap, decks, contrats, onboarding client — dépose-les, je les intègre. »

**Creuse ce qui est riche, skip ce qui est déjà clair.** Reformule à la fin pour validation, puis passe au projet suivant.

---

## Étape 7 — Section 05 : Phase de vie

Explique le concept :

```
Dans ton vault, on organise ton journaling par « phases de vie ». Une phase, c'est
une période avec un focus particulier — ça peut durer 3 semaines ou 6 mois. Quand
ton énergie/focus change (nouveau projet, déménagement, changement de cap), tu
ouvres une nouvelle phase avec /new-life-phase.

Chaque phase a son dossier avec une intention, et c'est là que vivent tes daily
notes et weekly notes. Tu retrouves exactement ce que tu faisais et pensais à une
période donnée de ta vie.

Exemples de phases : « Lancement solo », « Scale & Systems », « Reconstruction »,
« Prépa concours », « Transition pro », « Exploration créative ».
```

Pose **une par une** :

1. **Donne un nom à ta phase actuelle.** Un mot ou une expression qui résume cette période.

2. **Quand ça a commencé ?** Quelle est ton intention pour cette phase ? Tes objectifs concrets ?

3. **Tes contraintes actuelles ?** Temps disponible par semaine, niveau d'énergie, budget, obligations.

4. **Que fais-tu quand tu es surchargé / dispersé / fatigué / dans le flow ?** (stratégies personnelles — précieux pour que l'IA t'aide en contexte).

---

## Étape 8 — Section Bonus : Contexte global (style IA, valeurs)

Annonce :

```
Dernier bloc avant qu'on crée tes fichiers : le contexte global — comment tu veux
que l'IA te parle, tes valeurs, ton rythme.
```

Pose :

1. **Valeurs & principes** — ce qui guide tes décisions, tes lignes rouges (3 à 5 lignes maximum).

2. **Style de communication IA** — tutoiement ? ton (direct/chaleureux/challengeant) ? langue ? niveau de pushback (tu veux que l'IA te challenge, ou qu'elle exécute) ?

3. **Chrono-type** — tes heures de deep work, ton rythme hebdo.

---

## Étape 9 — Analyse et reformulation

Analyse **toutes les réponses et documents déposés** pendant les Étapes 3 à 8. Reformule ce que tu as compris :

1. **Qui est l'utilisateur** (2-3 phrases denses)
2. **Phase de vie actuelle** (nom + focus)
3. **Casquettes identifiées** (noms, 1-3 mots chacune)
4. **Projets actifs** (noms + pitch en 1 phrase)
5. **Casquette Business** (si une activité indépendante a été mentionnée dans les projets ou casquettes — elle mérite sa propre casquette dédiée, on la créera en Étape 11)
6. **Fichiers déposés** et ce que tu en as extrait

---

## Étape 10 — Questions de clarification

Pose 2 à 5 questions pour lever les dernières ambiguïtés :
- Infos manquantes ou contradictoires
- Éléments flous qui deviendront bloquants quand on créera les fichiers
- Confirmations sur les décisions (ex : « la casquette ‘Santé’ est vraiment distincte de ‘Sport’ ou on fusionne ? »)

Continue jusqu'à avoir une compréhension complète.

---

## Étape 11 — Validation finale

Montre un récapitulatif et demande validation explicite :

```
Voici ce que je vais créer / compléter :

- AGENTS.md (racine WORKSPACE)              ← ajout du nom de l'IA « [Nom IA] » + prénom
- Second Cerveau/2 CASQUETTES/Sur ma vie/Moi.md          ← qui tu es, style IA, valeurs, vision
- Second Cerveau/2 CASQUETTES/Sur ma vie/Mon Parcours.md ← historique chronologique

Casquettes ([X]) :
- Second Cerveau/2 CASQUETTES/[Casquette 1]/[Casquette 1].md
- Second Cerveau/2 CASQUETTES/[Casquette 2]/[Casquette 2].md
- ... (dont [Casquette Business] si applicable, remplie avec les infos business)

Projets ([Y]) :
- Second Cerveau/1 PROJETS/[Projet 1]/[Projet 1].md
- Second Cerveau/1 PROJETS/[Projet 2]/[Projet 2].md

Phase de vie :
- Second Cerveau/2 CASQUETTES/Sur ma vie/Life Phases/1 [Nom phase]/1 Intention.md

Daily note du jour (log d'initialisation) :
- Second Cerveau/2 CASQUETTES/Sur ma vie/Life Phases/1 [Nom phase]/YYYY-MM-DD.md

Configs Obsidian mises à jour (daily notes + weekly notes → dossier de la phase)

Confirmes-tu ? (oui / ajustements)
```

---

## Étape 12 — Génération

Si validé, crée les fichiers suivants (respecte strictement la structure de la nouvelle arbo).

### 12.1 — Nom de l'IA et prénom dans l'`AGENTS.md` racine (WORKSPACE)

Édite le fichier `AGENTS.md` à la racine du WORKSPACE (PAS celui du vault — il est à la racine, à côté du dossier `Second Cerveau/`). Section `## Identité` : remplace les placeholders par les vrais valeurs recueillies à l'Étape 2 :

```markdown
## Identité

**Nom de l'IA :** [Nom choisi par l'utilisateur]

**Prénom de l'utilisateur :** [Prénom]
```

Ce fichier racine définit l'identité globale. L'IA se présente et se réfère à elle-même sous ce nom dans toutes les interactions, peu importe le projet WORKSPACE ouvert.

### 12.2 — `Moi.md` (`Second Cerveau/2 CASQUETTES/Sur ma vie/Moi.md`)

Remplis la note existante. Conserve la frontmatter (`type: context, status: active`).

```markdown
---
type: context
status: active
---

# Moi

**Prénom :** [Prénom]

## Qui je suis

[Parcours en bref — 2-3 phrases]

**Forces :**
- [Force 1]
- [Force 2]

**Faiblesses :**
- [Faiblesse 1]
- [Faiblesse 2]

**Passions :**
- [Passion 1]
- [Passion 2]

## Style de communication IA

[Tutoiement, ton, langue, niveau de pushback]

## MBTI

[Résultat si donné, sinon vide]

## Valeurs et principes

- [Valeur 1]
- [Valeur 2]

## Comment je travaille

- [Routine 1]
- [Routine 2]

## Vision long-terme

**12 mois :** [description]
**5 ans :** [description]

## Actions essentielles quotidiennes

- [Action 1]
- [Action 2]
- [Action 3]
```

### 12.3 — `Mon Parcours.md` (`Second Cerveau/2 CASQUETTES/Sur ma vie/Mon Parcours.md`)

Remplis avec l'historique chronologique recueilli + les infos extraites des documents déposés. Structure par année / grande période.

### 12.4 — Dossiers Casquettes (`Second Cerveau/2 CASQUETTES/[Nom]/[Nom].md`)

Pour chaque casquette :
1. `mkdir -p "Second Cerveau/2 CASQUETTES/[Nom]"`
2. Écris `[Nom].md` à partir du template `Second Cerveau/4 TOOLS/Templates/Casquette.md`, rempli avec les 6 champs.

**Cas spécial — casquette Business** : si l'utilisateur a une activité indépendante, crée une casquette dédiée (ex : `Second Cerveau/2 CASQUETTES/[Nom du business]/`) et remplis avec :
- Positionnement (ce qu'on vend, à qui, pourquoi)
- Offres et tarifs
- Clients et métriques
- Canaux d'acquisition
- Delivery (parcours client, process, outils)
- Équipe, stack technique, URLs

### 12.5 — Dossiers Projets (`Second Cerveau/1 PROJETS/[Nom]/[Nom].md`)

Pour chaque projet :
1. `mkdir -p "Second Cerveau/1 PROJETS/[Nom]"`
2. Écris `[Nom].md` à partir du template `Second Cerveau/4 TOOLS/Templates/Projet.md`, rempli avec les 7 champs.

### 12.6 — Première Phase de vie (`Second Cerveau/2 CASQUETTES/Sur ma vie/Life Phases/1 [Nom]/`)

1. Renomme `Second Cerveau/2 CASQUETTES/Sur ma vie/Life Phases/1 Phase initiale/` en `1 [Nom de la phase]/`
2. Renomme `1 Intention.md` si besoin (garder le préfixe `1`)
3. Remplis `1 Intention.md` (template `Second Cerveau/4 TOOLS/Templates/Phase de vie.md`) :
   - Période estimée
   - Intention principale
   - Journée idéale pendant cette période
   - Objectifs de la phase
   - Stratégies quand surchargé / dispersé / fatigué / dans le flow
4. Mets à jour `Second Cerveau/2 CASQUETTES/Sur ma vie/Life Phases/Life Phases.md` (remplacer « Phase initiale » par le vrai nom, mettre à jour le lien vers l'intention)

### 12.7 — Configs Obsidian

**`.obsidian/daily-notes.json`** :
```json
{
  "folder": "2 CASQUETTES/Sur ma vie/Life Phases/1 [Nom de la phase]",
  "template": "4 TOOLS/Templates/Daily Note",
  "autorun": false
}
```

**`.obsidian/plugins/calendar/data.json`** :
```json
{
  "shouldConfirmBeforeCreate": true,
  "weekStart": "locale",
  "wordsPerDot": 250,
  "showWeeklyNote": true,
  "weeklyNoteFormat": "",
  "weeklyNoteTemplate": "4 TOOLS/Templates/Weekly Note",
  "weeklyNoteFolder": "2 CASQUETTES/Sur ma vie/Life Phases/1 [Nom de la phase]",
  "localeOverride": "system-default"
}
```

### 12.8 — Daily note du jour (log d'initialisation)

Crée `Second Cerveau/2 CASQUETTES/Sur ma vie/Life Phases/1 [Nom]/[YYYY-MM-DD].md` à partir du template `Second Cerveau/4 TOOLS/Templates/Daily Note.md`, puis ajoute un log initial en fin de fichier :

```markdown
---

## Logs IA / Session [HH:MM]

**Accompli :**
- Vault initialisé via `/initialisation`
- Création de `Moi.md`, `Mon Parcours.md`, casquettes, projets, phase « [Nom] »
- Nom de l'IA enregistré dans `AGENTS.md` : « [Nom IA] »

**Extractions :**
- Préférences : prénom « [Prénom] », nom IA « [Nom IA] », style de communication défini
- Faits : [X] casquettes, [Y] projets actifs, phase « [Nom] » démarrée
- Fichiers déposés et intégrés : [liste si applicable]

**Prochaines étapes :**
- [ ] Explorer le vault, tester `/welcome`
- [ ] Compléter `Mon Parcours.md` avec les docs restants
- [ ] Mapper tes process via `/map-process` et en documenter un avec `/create-skill`
```

---

## Étape 13 — Confirmation & next steps

```
✅ Initialisation terminée !

Créé dans ton vault :
- AGENTS.md (racine WORKSPACE)                   → nom de l'IA : [Nom] + prénom
- Second Cerveau/2 CASQUETTES/Sur ma vie/Moi.md                 → qui tu es, style IA, valeurs
- Second Cerveau/2 CASQUETTES/Sur ma vie/Mon Parcours.md        → historique chronologique
- [X] casquettes dans Second Cerveau/2 CASQUETTES/
- [Y] projets dans Second Cerveau/1 PROJETS/
- Phase « 1 [Nom] » avec son intention
- Daily note du jour avec le log d'initialisation

Configs Obsidian :
- Daily notes  → Second Cerveau/2 CASQUETTES/Sur ma vie/Life Phases/1 [Nom]/
- Weekly notes → Second Cerveau/2 CASQUETTES/Sur ma vie/Life Phases/1 [Nom]/

⚠️ Redémarre Obsidian pour activer les configs de daily/weekly notes.
```

---

## Règles

- **Toujours demander validation** avant de créer des fichiers (Étape 11)
- **Reformuler** après chaque réponse pour valider la compréhension
- **Rappeler l'affordance fichier** à chaque grande section (Étapes 3-7)
- **Lire intégralement** tout fichier déposé avant d'en extraire l'info
- **Ne jamais inventer** — si une info manque et n'a pas été donnée, demande
- **Respecter le style** capturé à l'Étape 8 dès qu'il est connu (tutoiement, ton, pushback)

## Ce que tu ne fais PAS

- Sauter le prélude pédagogique (Étape 1) — l'utilisateur doit comprendre ce qu'il fait
- Créer les fichiers sans validation finale
- Mettre le nom de l'IA dans `Moi.md` (il va dans `AGENTS.md`)
- Traiter la casquette « Business » comme une section de `Moi.md` (elle mérite son propre dossier dans `Second Cerveau/2 CASQUETTES/[Nom du business]/`)
- Hardcoder les chemins Life Phases : c'est toujours `Second Cerveau/2 CASQUETTES/Sur ma vie/Life Phases/`
- Oublier de mettre à jour les configs Obsidian (Étape 12.7)
