# Cours Complet Git 

### Nom : Lo | Prénom : Pape | Email : pape.lo@estiam.co

<div align="center">

![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white)
![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)
![Version Control](https://img.shields.io/badge/Version%20Control-VCS-blue?style=for-the-badge)
![Workflow](https://img.shields.io/badge/Workflow-GitHub_Flow-2088FF?style=for-the-badge&logo=github-actions&logoColor=white)
![Niveau](https://img.shields.io/badge/Niveau-Débutant_à_Expert-brightgreen?style=for-the-badge)

**Formation complète et pratique sur Git : 24 modules, théorie et labs guidés**

*Version 1.0 - Branches · Rebase · Conflits · Workflows · Internals*

[Sommaire](#-sommaire) • [Modules](#-comment-utiliser-ce-cours) • [Labs pratiques](#module-2--le-dépôt-local--init-add-commit) • [Workflows](#module-9--workflows-déquipe-git-flow-github-flow-trunk-based) • [Projet final](#annexe-b--projet-final-récapitulatif)

</div>

> Formation professionnelle complète sur Git : théorie, pratique intensive, labs guidés et exercices réels. Chaque module contient des explications, des commandes commentées, des schémas conceptuels et des labs à faire vous-même dans un terminal.

---

## Sommaire

### Partie 1 - Fondations
- [Module 0 - Préparer son environnement](#module-0---préparer-son-environnement)
- [Module 1 - Comprendre ce qu'est Git](#module-1---comprendre-ce-quest-git)
- [Module 2 - Le dépôt local : init, add, commit](#module-2---le-dépôt-local-init-add-commit)
- [Module 3 - L'historique : log, diff, show](#module-3---lhistorique-log-diff-show)

### Partie 2 - Travailler avec des branches
- [Module 4 - Branches : créer, naviguer, fusionner](#module-4---branches-créer-naviguer-fusionner)
- [Module 5 - Les conflits de fusion](#module-5---les-conflits-de-fusion)
- [Module 6 - Rebase et historique linéaire](#module-6---rebase-et-historique-linéaire)

### Partie 3 - Travail collaboratif (distant)
- [Module 7 - Dépôts distants : clone, push, pull, fetch](#module-7---dépôts-distants-clone-push-pull-fetch)
- [Module 8 - GitHub : Pull Requests et code review](#module-8---github-pull-requests-et-code-review)
- [Module 9 - Workflows d'équipe (Git Flow, GitHub Flow, Trunk-Based)](#module-9---workflows-déquipe-git-flow-github-flow-trunk-based)

### Partie 4 - Techniques intermédiaires
- [Module 10 - Annuler et corriger : reset, revert, checkout, restore](#module-10---annuler-et-corriger-reset-revert-checkout-restore)
- [Module 11 - Stash et travail temporaire](#module-11---stash-et-travail-temporaire)
- [Module 12 - Tags et versions](#module-12---tags-et-versions)
- [Module 13 - .gitignore et gestion des fichiers](#module-13---gitignore-et-gestion-des-fichiers)

### Partie 5 - Techniques avancées
- [Module 14 - Rebase interactif et réécriture d'historique](#module-14---rebase-interactif-et-réécriture-dhistorique)
- [Module 15 - Cherry-pick et gestion fine des commits](#module-15---cherry-pick-et-gestion-fine-des-commits)
- [Module 16 - Git Bisect : débogage par dichotomie](#module-16---git-bisect-débogage-par-dichotomie)
- [Module 17 - Submodules et Subtrees](#module-17---submodules-et-subtrees)
- [Module 18 - Hooks Git : automatiser des actions](#module-18---hooks-git-automatiser-des-actions)
- [Module 19 - Plumbing et internals : comment Git fonctionne vraiment](#module-19---plumbing-et-internals-comment-git-fonctionne-vraiment)

### Partie 6 - Maîtrise professionnelle
- [Module 20 - Gérer un historique propre (rewriting avancé, filter-repo)](#module-20---gérer-un-historique-propre-rewriting-avancé-filter-repo)
- [Module 21 - Git avancé en équipe : CODEOWNERS, branch protection, signing](#module-21---git-avancé-en-équipe-codeowners-branch-protection-signing)
- [Module 22 - Dépannage et récupération (reflog, fsck)](#module-22---dépannage-et-récupération-reflog-fsck)
- [Module 23 - Bonnes pratiques et conventions professionnelles](#module-23---bonnes-pratiques-et-conventions-professionnelles)

### Annexes
- [Annexe A - Aide-mémoire (Cheat Sheet) complet](#annexe-a---aide-mémoire-cheat-sheet-complet)
- [Annexe B - Projet final récapitulatif](#annexe-b---projet-final-récapitulatif)
- [Annexe C - Glossaire](#annexe-c---glossaire)
- [Annexe D - Ressources complémentaires](#annexe-d---ressources-complémentaires)

---

## Comment utiliser ce cours

Chaque module suit la même structure :

1. **Objectifs** - ce que vous saurez faire à la fin
2. **Théorie** - les concepts expliqués simplement, avec schémas
3. **Commandes** - la syntaxe, les options utiles, des exemples concrets
4. **Lab pratique** - un exercice guidé pas-à-pas, à faire dans votre terminal
5. **Quiz / Auto-évaluation** - pour vérifier que les notions sont acquises
6. **Défi bonus** - pour aller plus loin (optionnel)

**Conseil pédagogique :** ne sautez pas les labs. Git s'apprend par la pratique : lire ne suffit pas, il faut taper les commandes, casser des choses, et les réparer. Prévoyez un dossier de travail dédié, par exemple :

```bash
mkdir -p ~/git-formation && cd ~/git-formation
```

---

## Module 0 - Préparer son environnement

### Objectifs
- Installer Git correctement sur son système
- Configurer son identité et ses préférences globales
- Comprendre les trois niveaux de configuration

### Théorie

Git est un **logiciel** que l'on installe sur sa machine (contrairement à GitHub/GitLab, qui sont des **plateformes en ligne** hébergeant des dépôts Git). Avant de l'utiliser, il faut le configurer : nom, email, éditeur par défaut, comportements par défaut.

Git lit sa configuration à trois niveaux, du plus général au plus spécifique (le plus spécifique l'emporte) :

| Niveau | Commande | Portée | Fichier |
|---|---|---|---|
| `--system` | rare, admin machine | toute la machine | `/etc/gitconfig` |
| `--global` | le plus courant | tous vos dépôts | `~/.gitconfig` |
| `--local` | spécifique à un projet | un seul dépôt | `.git/config` |

### Commandes essentielles

```bash
# Vérifier l'installation
git --version

# Identité (obligatoire avant le premier commit)
git config --global user.name "Votre Nom"
git config --global user.email "vous@exemple.com"

# Éditeur par défaut (pour les messages de commit, rebase interactif, etc.)
git config --global core.editor "nano"      # ou "vim", "code --wait"

# Couleurs dans le terminal (très utile visuellement)
git config --global color.ui auto

# Nom de branche par défaut lors d'un init (bonne pratique moderne)
git config --global init.defaultBranch main

# Voir toute la configuration active
git config --list

# Voir d'où vient un paramètre précis
git config --show-origin user.name
```

### Lab 0.1 - Installer et configurer Git

**Étape 1.** Vérifiez si Git est installé :
```bash
git --version
```
Si la commande échoue, installez Git :
- **Linux (Debian/Ubuntu)** : `sudo apt update && sudo apt install git`
- **macOS** : `brew install git` (ou Xcode Command Line Tools)
- **Windows** : téléchargez [Git for Windows](https://git-scm.com/download/win)

**Étape 2.** Configurez votre identité :
```bash
git config --global user.name "Votre Nom"
git config --global user.email "votre.email@exemple.com"
```

**Étape 3.** Vérifiez que tout est bien pris en compte :
```bash
git config --list --global
```
Vous devez voir apparaître `user.name` et `user.email` avec vos valeurs.

**Étape 4.** (Bonus) Activez quelques améliorations de confort :
```bash
git config --global color.ui auto
git config --global init.defaultBranch main
git config --global pull.rebase false
```

### Auto-évaluation
- Quelle est la différence entre `--global` et `--local` ?
- Que se passe-t-il si vous committez sans avoir configuré `user.email` ?
- Où se trouve le fichier de configuration global sur votre OS ?

---

## Module 1 - Comprendre ce qu'est Git

### Objectifs
- Comprendre ce qu'est un système de contrôle de version
- Comprendre la différence entre Git (l'outil) et GitHub/GitLab (les plateformes)
- Comprendre l'architecture en 3 zones de Git

### Théorie

#### Qu'est-ce qu'un système de contrôle de version (VCS) ?

Un **VCS** (Version Control System) enregistre l'historique des modifications d'un ensemble de fichiers dans le temps. Cela permet de :
- revenir à une version antérieure,
- comparer des versions,
- savoir qui a modifié quoi et quand,
- travailler en parallèle sans s'écraser mutuellement le travail.

Git est un VCS **distribué** : chaque développeur possède une copie complète de l'historique du projet sur sa machine (contrairement aux VCS centralisés plus anciens comme SVN, où l'historique complet n'existe que sur un serveur central).

#### Les trois zones de Git

C'est **LE** concept fondamental à comprendre avant tout le reste. Git organise le travail en trois zones :

```
┌──────────────────┐    git add     ┌──────────────────┐    git commit    ┌──────────────────┐
│  Working Dir      │ ─────────────▶│  Staging Area     │ ─────────────────▶│  Repository       │
│  (répertoire de   │                │  (index)          │                    │  (.git, historique)│
│   travail)         │◀───────────────│                   │◀───────────────────│                  │
└──────────────────┘  git restore    └──────────────────┘    git reset       └──────────────────┘
```

1. **Working Directory** (répertoire de travail) : les fichiers tels que vous les voyez et les modifiez sur le disque.
2. **Staging Area / Index** : une zone tampon où vous préparez ce qui ira dans le prochain commit. C'est ce qui rend Git unique : vous choisissez précisément quelles modifications inclure.
3. **Repository** (`.git/`) : la base de données qui contient tout l'historique, les commits, les branches, les tags.

Comprendre ce schéma résout la majorité de la confusion des débutants sur Git.

#### Git ≠ GitHub

- **Git** : le logiciel de contrôle de version, installé localement, fonctionne sans connexion internet.
- **GitHub / GitLab / Bitbucket** : des plateformes web qui **hébergent** des dépôts Git distants et ajoutent des fonctionnalités collaboratives (Pull Requests, Issues, CI/CD, etc.).

Vous pouvez utiliser Git toute votre carrière sans jamais toucher à GitHub. Mais en pratique, la collaboration moderne combine les deux.

### Lab 1.1 - Explorer la structure d'un dépôt

**Étape 1.** Créez un dossier et initialisez un dépôt :
```bash
mkdir mon-premier-depot && cd mon-premier-depot
git init
```

**Étape 2.** Observez ce que Git a créé :
```bash
ls -la
ls -la .git
```
Vous voyez un dossier `.git` : **c'est tout le dépôt**. Si vous le supprimez, vous perdez tout l'historique (mais pas vos fichiers actuels sur le disque).

**Étape 3.** Regardez son contenu interne (juste pour observer, pas pour modifier) :
```bash
cat .git/HEAD
ls .git/refs
ls .git/objects
```
Ne vous inquiétez pas si c'est obscur pour l'instant - le Module 19 y reviendra en détail.

### Auto-évaluation
- Expliquez avec vos mots la différence entre Working Directory, Staging Area et Repository.
- Git est-il obligatoirement connecté à internet pour fonctionner ?
- Quelle est la différence fondamentale entre Git et GitHub ?

---

## Module 2 - Le dépôt local : init, add, commit

### Objectifs
- Créer un dépôt et y faire des commits
- Maîtriser le cycle add → commit
- Comprendre l'état des fichiers (untracked, modified, staged, committed)
- Rédiger des messages de commit de qualité professionnelle

### Théorie

#### Le cycle de vie d'un fichier

```
Untracked ──git add──▶ Staged ──git commit──▶ Committed (Unmodified)
                                                      │
                                                      │ on modifie le fichier
                                                      ▼
                                                  Modified ──git add──▶ Staged ──...
```

- **Untracked** : Git voit le fichier mais ne le suit pas encore.
- **Modified** : le fichier est suivi, mais a changé depuis le dernier commit.
- **Staged** : la modification est prête à être incluse dans le prochain commit.
- **Committed** : la modification est enregistrée définitivement dans l'historique.

#### Anatomie d'un commit

Chaque commit est un instantané (snapshot) référencé par un hash SHA-1 (ex : `a1b2c3d...`), et contient :
- un pointeur vers l'instantané des fichiers,
- un pointeur vers son commit parent (ou plusieurs, pour un merge),
- l'auteur, la date,
- un message décrivant le changement.

#### Bonnes pratiques de message de commit

Convention largement utilisée (issue du projet Git lui-même) :

```
Type court de ligne de résumé (50 caractères max)

Corps explicatif si nécessaire (72 caractères par ligne).
Expliquez le POURQUOI du changement, pas seulement le QUOI :
le code montre déjà ce qui a changé.

- Peut contenir une liste à puces
- Référence un ticket : Fixes #42
```

Une convention très répandue en entreprise est **Conventional Commits** :
```
feat: ajoute le filtre par catégorie sur la page produit
fix: corrige le calcul de la TVA pour les comptes pro
docs: met à jour le README d'installation
refactor: simplifie la logique de pagination
test: ajoute des tests sur le module panier
chore: met à jour les dépendances npm
```

### Commandes essentielles

```bash
git init                          # créer un nouveau dépôt
git status                        # voir l'état actuel (LA commande la plus utilisée)
git add fichier.txt                # ajouter un fichier précis au stage
git add .                         # ajouter tous les fichiers modifiés/nouveaux
git add -p                        # ajouter de façon interactive, morceau par morceau (très puissant)
git commit -m "message"           # committer avec un message court
git commit                        # ouvre l'éditeur pour un message détaillé
git commit -am "message"          # raccourci: add tous les fichiers suivis + commit (n'ajoute pas les nouveaux fichiers !)
git commit --amend                # modifier le dernier commit (message et/ou contenu)
git rm fichier.txt                 # supprimer un fichier et stager la suppression
git mv ancien.txt nouveau.txt      # renommer un fichier et stager le renommage
```

### Lab 2.1 - Premier dépôt et premiers commits

**Étape 1.** Initialisez un dépôt de pratique :
```bash
mkdir lab-recettes && cd lab-recettes
git init
```

**Étape 2.** Créez un premier fichier :
```bash
echo "# Mes Recettes" > README.md
git status
```
Observez : `README.md` apparaît en **Untracked**.

**Étape 3.** Ajoutez-le au stage et observez le changement d'état :
```bash
git add README.md
git status
```
Il apparaît maintenant comme **Changes to be committed**.

**Étape 4.** Faites votre premier commit :
```bash
git commit -m "Initial commit: ajoute le README"
```

**Étape 5.** Ajoutez du contenu et créez un nouveau fichier :
```bash
echo "## Tarte aux pommes" >> README.md
echo "- 4 pommes
- 200g de farine
- 100g de beurre" > tarte-pommes.txt
git status
```
Observez : `README.md` est **Modified**, `tarte-pommes.txt` est **Untracked**.

**Étape 6.** Stagez tout et committez :
```bash
git add .
git status
git commit -m "Ajoute la recette de la tarte aux pommes"
```

**Étape 7.** Testez l'ajout interactif (très utile en pratique professionnelle) :
```bash
echo "## Quiche Lorraine" >> README.md
echo "- 200g de lardons
- 3 oeufs
- 20cl de crème" > quiche.txt
git add -p README.md
```
Git vous montre le "hunk" (le morceau modifié) et vous demande `y/n/q/...`. Répondez `y` pour accepter.

**Étape 8.** Testez `--amend` pour corriger un message de commit :
```bash
git add quiche.txt
git commit -m "ajoute quiche"
git commit --amend -m "Ajoute la recette de la quiche lorraine"
git log --oneline
```

### Pièges fréquents
- `git commit -am` n'ajoute **pas** les nouveaux fichiers (untracked), seulement les fichiers déjà suivis et modifiés.
- `git add .` ajoute tout le dossier courant et ses sous-dossiers - vérifiez toujours avec `git status` avant de committer.
- `--amend` réécrit le dernier commit : **ne jamais l'utiliser sur un commit déjà poussé et partagé** avec d'autres (le Module 14 explique pourquoi).

### Auto-évaluation
- Quelle commande tapez-vous en premier, systématiquement, avant chaque action Git ? (réponse : `git status`)
- Pourquoi `git commit -am` peut-il être piégeux ?
- Que fait `git add -p` par rapport à `git add .` ?

### Défi bonus
Créez un dépôt `journal-perso`, faites 5 commits représentant 5 jours différents de votre semaine, chacun avec un message clair au format Conventional Commits (`feat:`, `docs:`, etc.).

---

## Module 3 - L'historique : log, diff, show

### Objectifs
- Naviguer dans l'historique des commits
- Comparer des versions de fichiers
- Filtrer et formater l'historique selon ses besoins

### Théorie

L'historique Git est une **chaîne de commits**, chacun pointant vers son parent. C'est en réalité un graphe orienté acyclique (DAG), car les merges créent des commits à plusieurs parents.

```
A ── B ── C ── D   (main)
          │
          └── E ── F   (feature)
```

`git log` est l'outil principal pour explorer cette chaîne, et il a des dizaines d'options pour l'adapter à vos besoins.

### Commandes essentielles

```bash
git log                                  # historique complet, détaillé
git log --oneline                        # une ligne par commit (hash court + message)
git log --oneline --graph --all          # vue graphique avec toutes les branches (très utile !)
git log -5                               # les 5 derniers commits seulement
git log --author="Marie"                 # filtrer par auteur
git log --since="2 weeks ago"            # filtrer par date
git log --until="2024-01-01"
git log -- fichier.txt                    # historique limité à un fichier précis
git log -p                               # affiche aussi le diff (patch) de chaque commit
git log --stat                           # affiche les statistiques de fichiers modifiés
git log --grep="fix"                     # rechercher dans les messages de commit

git diff                                 # différences non stagées (working dir vs index)
git diff --staged                        # différences stagées (index vs dernier commit)
git diff HEAD                            # toutes les différences depuis le dernier commit
git diff branche1 branche2                # différences entre deux branches
git diff commit1 commit2                  # différences entre deux commits précis

git show <hash>                          # détails complets d'un commit précis
git show HEAD                            # détails du commit le plus récent
git show HEAD~2                          # détails du commit 2 positions avant HEAD
```

#### Comprendre les références relatives

| Référence | Signification |
|---|---|
| `HEAD` | le commit actuellement « checké out » |
| `HEAD~1` ou `HEAD^` | le parent direct |
| `HEAD~3` | 3 commits avant HEAD (en remontant les parents) |
| `HEAD^2` | le 2e parent (pour un commit de merge, qui a 2 parents) |

### Lab 3.1 - Explorer un historique réaliste

**Étape 1.** Reprenez le dépôt `lab-recettes` du Module 2 (ou créez-en un nouveau avec plusieurs commits).

**Étape 2.** Visualisez l'historique de plusieurs façons :
```bash
git log
git log --oneline
git log --oneline --graph --all --decorate
```

**Étape 3.** Modifiez un fichier sans committer, et observez le diff :
```bash
echo "## Crêpes" >> README.md
git diff
```
Vous voyez les lignes ajoutées en vert (préfixées `+`).

**Étape 4.** Stagez, puis comparez à nouveau :
```bash
git add README.md
git diff             # vide ! car tout est déjà stagé
git diff --staged    # ici vous voyez le changement en attente de commit
```

**Étape 5.** Committez, puis inspectez ce commit précis :
```bash
git commit -m "feat: ajoute la recette des crêpes"
git show HEAD
```

**Étape 6.** Comparez les deux derniers commits entre eux :
```bash
git diff HEAD~1 HEAD
```

**Étape 7.** Recherchez dans l'historique :
```bash
git log --grep="quiche"
git log -- README.md
```

### Pièges fréquents
- Confondre `git diff` (non stagé) et `git diff --staged` (stagé) - c'est l'erreur n°1 des débutants pour comprendre pourquoi "rien ne s'affiche".
- `HEAD^` et `HEAD~` se comportent pareil pour 1, mais divergent en présence de merges (`^2` = second parent, `~2` = grand-parent).

### Auto-évaluation
- Quelle commande utilisez-vous pour voir les modifications déjà stagées mais pas encore committées ?
- Que signifie `HEAD~3` ?
- Comment afficher uniquement l'historique d'un fichier précis ?

---

## Module 4 - Branches : créer, naviguer, fusionner

### Objectifs
- Comprendre ce qu'est réellement une branche dans Git
- Créer, basculer, supprimer des branches
- Fusionner deux branches (fast-forward et merge commit)

### Théorie

#### Ce qu'est vraiment une branche

C'est un autre concept fondamental, souvent mal compris : **une branche Git n'est qu'un simple pointeur mobile vers un commit**. Ce n'est pas une copie de fichiers, ni un dossier séparé - c'est littéralement un fichier texte de 40 caractères (le hash du commit) dans `.git/refs/heads/`.

C'est précisément pour ça que Git rend la création de branches quasi instantanée et très peu coûteuse, contrairement à d'autres VCS plus anciens.

```
            HEAD
             │
             ▼
A ── B ── C ── D        (main)
          │
          └── E ── F    (feature-login)
                   ▲
                   │
              (si on était sur feature-login, HEAD pointerait ici)
```

`HEAD` est lui-même un pointeur - vers la branche actuellement active (généralement). C'est ce qu'on appelle être "sur" une branche.

#### Fast-forward vs Merge commit

Quand vous fusionnez une branche dans une autre, deux cas existent :

**Cas 1 - Fast-forward** : si la branche cible (ex: `main`) n'a **reçu aucun nouveau commit** depuis la création de la branche à fusionner, Git se contente d'avancer le pointeur. Pas de nouveau commit créé.

```
Avant :  main ── A ── B
                       feature ── C ── D

Après (fast-forward) :  main, feature ── A ── B ── C ── D
```

**Cas 2 - Merge commit (3-way merge)** : si les deux branches ont divergé (chacune a de nouveaux commits), Git crée un **commit de fusion** spécial à deux parents.

```
Avant :
main ──── A ── B ──────── E
                \           
feature          C ── D

Après (merge commit) :
main ──── A ── B ──────── E ── M  (M = merge commit, parents : E et D)
                \                /
feature          C ── D ────────
```

### Commandes essentielles

```bash
git branch                          # lister les branches locales ( = branche active)
git branch -a                       # lister aussi les branches distantes
git branch nouvelle-branche         # créer une branche (sans y basculer)
git checkout nouvelle-branche       # basculer sur une branche
git checkout -b nouvelle-branche    # créer ET basculer en une commande
git switch nouvelle-branche         # équivalent moderne de checkout (Git 2.23+)
git switch -c nouvelle-branche      # équivalent moderne de checkout -b

git branch -d nom-branche           # supprimer une branche (refuse si non fusionnée)
git branch -D nom-branche           # supprimer en forçant (même non fusionnée)
git branch -m ancien-nom nouveau-nom # renommer une branche

git merge nom-branche               # fusionner nom-branche DANS la branche courante
git merge --no-ff nom-branche       # forcer un merge commit même si fast-forward possible
git merge --abort                   # annuler une fusion en cours (ex: en cas de conflit)
```

### Lab 4.1 - Manipuler les branches

**Étape 1.** Créez un nouveau dépôt de pratique :
```bash
mkdir lab-branches && cd lab-branches
git init
echo "Page d'accueil" > index.html
git add . && git commit -m "Initial commit"
```

**Étape 2.** Créez une branche pour une nouvelle fonctionnalité :
```bash
git checkout -b feature-contact
echo "Page de contact" > contact.html
git add . && git commit -m "feat: ajoute la page de contact"
git log --oneline --all --graph
```

**Étape 3.** Retournez sur `main` et observez que `contact.html` disparaît :
```bash
git checkout main
ls
```
`contact.html` n'existe plus dans le working directory ! Il n'a jamais quitté la branche `feature-contact`. C'est normal et c'est tout l'intérêt des branches.

**Étape 4.** Testez un fast-forward merge :
```bash
git merge feature-contact
ls
git log --oneline --graph
```
Comme `main` n'avait reçu aucun commit pendant ce temps, Git a fait un simple fast-forward (pas de merge commit créé).

**Étape 5.** Maintenant, créez une vraie divergence :
```bash
git checkout -b feature-footer
echo "Footer du site" > footer.html
git add . && git commit -m "feat: ajoute le footer"

git checkout main
echo "<!-- meta tags -->" >> index.html
git add . && git commit -m "feat: ajoute des meta tags SEO"
```

**Étape 6.** Fusionnez et observez le merge commit créé cette fois :
```bash
git merge feature-footer
git log --oneline --graph --all
```
Vous voyez maintenant un commit avec **deux parents** représenté par la jonction dans le graphe.

**Étape 7.** Nettoyez les branches fusionnées :
```bash
git branch -d feature-contact
git branch -d feature-footer
git branch
```

### Pièges fréquents
- Oublier sur quelle branche on se trouve avant de committer (toujours vérifier avec `git status` ou `git branch`, qui affiche la branche active).
- Confondre `git branch nom` (crée sans basculer) et `git checkout -b nom` (crée ET bascule).
- `git branch -d` refuse de supprimer une branche non fusionnée - c'est une protection, pas un bug.

### Auto-évaluation
- Qu'est-ce qu'une branche, techniquement, dans Git ?
- Dans quel cas Git fait-il un fast-forward plutôt qu'un merge commit ?
- Quelle est la différence entre `git branch -d` et `git branch -D` ?

### Défi bonus
Créez 3 branches en parallèle depuis `main` (`feature-a`, `feature-b`, `feature-c`), faites un commit différent sur chacune, puis fusionnez-les toutes dans `main` dans un ordre de votre choix. Observez le graphe final avec `git log --oneline --graph --all`.

---

## Module 5 - Les conflits de fusion

### Objectifs
- Comprendre pourquoi et quand un conflit survient
- Savoir lire les marqueurs de conflit
- Résoudre un conflit manuellement et avec des outils

### Théorie

Un **conflit de fusion** survient quand Git ne peut pas fusionner automatiquement deux versions d'un même fichier, typiquement parce que **la même ligne (ou des lignes très proches) a été modifiée différemment sur les deux branches**.

Git ne devine jamais l'intention humaine : il s'arrête et vous demande de trancher.

#### Anatomie d'un conflit

Quand un conflit survient, Git insère des marqueurs directement dans le fichier :

```
Texte non conflictuel avant...
<<<<<<< HEAD
Version de la branche courante (où vous êtes)
=======
Version de la branche que vous fusionnez
>>>>>>> nom-de-l-autre-branche
Texte non conflictuel après...
```

Votre travail consiste à :
1. Éditer le fichier pour ne garder que le résultat souhaité,
2. Supprimer les marqueurs (`<<<<<<<`, `=======`, `>>>>>>>`),
3. `git add` le fichier résolu,
4. `git commit` pour finaliser le merge.

### Commandes essentielles

```bash
git merge branche-x                 # déclenche potentiellement un conflit
git status                          # liste les fichiers en conflit ("both modified")
git diff                            # montre les marqueurs de conflit dans le diff

# Après résolution manuelle :
git add fichier-resolu.txt
git commit                          # finalise le merge (message pré-rempli)

# Pour annuler un merge en cours de conflit :
git merge --abort

# Outils d'aide à la résolution :
git mergetool                       # ouvre un outil graphique configuré
git checkout --ours fichier.txt      # garder UNIQUEMENT la version de la branche courante
git checkout --theirs fichier.txt    # garder UNIQUEMENT la version de l'autre branche
```

### Lab 5.1 - Provoquer et résoudre un conflit

**Étape 1.** Créez un dépôt et un fichier de base :
```bash
mkdir lab-conflits && cd lab-conflits
git init
echo "Bonjour, bienvenue sur mon site." > accueil.txt
git add . && git commit -m "Initial commit"
```

**Étape 2.** Créez une branche et modifiez la même ligne :
```bash
git checkout -b branche-fr
echo "Bonjour et bienvenue chaleureusement sur mon site !" > accueil.txt
git add . && git commit -m "feat: message d'accueil plus chaleureux"
```

**Étape 3.** Revenez sur `main` et modifiez la même ligne différemment :
```bash
git checkout main
echo "Bienvenue sur le site officiel de mon entreprise." > accueil.txt
git add . && git commit -m "feat: message d'accueil plus formel"
```

**Étape 4.** Tentez la fusion - le conflit apparaît :
```bash
git merge branche-fr
git status
```

**Étape 5.** Ouvrez `accueil.txt` et observez les marqueurs :
```bash
cat accueil.txt
```
Vous devez voir quelque chose comme :
```
<<<<<<< HEAD
Bienvenue sur le site officiel de mon entreprise.
=======
Bonjour et bienvenue chaleureusement sur mon site !
>>>>>>> branche-fr
```

**Étape 6.** Résolvez le conflit en choisissant (ou combinant) une version. Par exemple :
```bash
echo "Bienvenue chaleureusement sur le site officiel de mon entreprise." > accueil.txt
```

**Étape 7.** Finalisez la résolution :
```bash
git add accueil.txt
git status                 # doit indiquer "All conflicts fixed"
git commit                 # un message de merge est pré-rempli, vous pouvez le garder
```

**Étape 8.** Vérifiez le résultat :
```bash
git log --oneline --graph --all
cat accueil.txt
```

### Lab 5.2 - Provoquer un conflit sur plusieurs fichiers et l'annuler

**Étape 1.** Sur `main`, modifiez deux fichiers et créez une branche qui les modifie aussi :
```bash
echo "v1" > a.txt
echo "v1" > b.txt
git add . && git commit -m "ajoute a et b"

git checkout -b experiment
echo "version-experiment-a" > a.txt
echo "version-experiment-b" > b.txt
git add . && git commit -m "modifie a et b sur experiment"

git checkout main
echo "version-main-a" > a.txt
echo "version-main-b" > b.txt
git add . && git commit -m "modifie a et b sur main"
```

**Étape 2.** Lancez la fusion, constatez le double conflit, puis **annulez tout** :
```bash
git merge experiment
git status
git merge --abort
git status
```
`git merge --abort` restaure parfaitement l'état d'avant la tentative de fusion - un filet de sécurité essentiel à connaître.

### Pièges fréquents
- Oublier de supprimer un marqueur de conflit (`<<<<<<<` etc.) avant de committer - le fichier reste alors cassé et le bug n'est découvert que plus tard.
- Paniquer face à un conflit : `git merge --abort` permet toujours de revenir en arrière sans rien casser.
- Confondre `--ours` et `--theirs` : leur sens s'inverse selon qu'on fait un `merge` ou un `rebase` (à garder en tête, source de confusion classique).

### Auto-évaluation
- Que signifient les marqueurs `<<<<<<<`, `=======`, `>>>>>>>` ?
- Quelle commande annule complètement un merge en cours sans rien casser ?
- Quelles sont les 4 étapes pour résoudre un conflit manuellement ?

---

## Module 6 - Rebase et historique linéaire

### Objectifs
- Comprendre la différence fondamentale entre merge et rebase
- Effectuer un rebase simple
- Savoir quand utiliser l'un ou l'autre

### Théorie

`git rebase` est une alternative à `git merge` pour intégrer les changements d'une branche dans une autre, mais avec une approche radicalement différente : **au lieu de créer un commit de fusion, il rejoue vos commits un par un par-dessus la nouvelle base**.

```
Avant rebase :
main ──── A ── B ──── E
                \
feature          C ── D

Après "git rebase main" (exécuté depuis feature) :
main ──── A ── B ──── E
                       \
feature                 C' ── D'   (nouveaux commits, nouveaux hash !)
```

Notez bien : `C'` et `D'` sont des **commits différents** de `C` et `D` (même contenu, mais nouveau hash, car leur parent a changé). C'est crucial : rebase **réécrit l'historique**.

#### Merge vs Rebase : lequel choisir ?

| | `merge` | `rebase` |
|---|---|---|
| Historique | conserve l'historique réel, avec ses divergences | historique linéaire, plus propre à lire |
| Sécurité | ne réécrit jamais rien, toujours sûr | réécrit les commits, dangereux si déjà partagés |
| Traçabilité | on voit exactement quand une branche a été intégrée | on perd la trace du "moment" de la divergence |
| Règle d'or | toujours sûr sur du code déjà publié | **jamais** sur des commits déjà poussés et partagés avec d'autres |

**Règle d'or à retenir absolument :** ne rebasez jamais une branche que d'autres personnes ont déjà récupérée (`pull`) chez eux. Cela forcerait tout le monde à résoudre des conflits artificiels. Le rebase est sûr sur votre branche de travail **locale et non partagée**.

### Commandes essentielles

```bash
git rebase main                     # rejoue les commits de la branche courante sur main
git rebase --abort                  # annule un rebase en cours (en cas de conflit non désiré)
git rebase --continue               # après résolution d'un conflit pendant le rebase
git rebase --skip                   # ignore le commit en conflit (rare, prudence)

git pull --rebase                   # équivalent de fetch + rebase au lieu de fetch + merge
```

### Lab 6.1 - Comparer merge et rebase sur le même scénario

**Étape 1.** Créez un dépôt et un historique divergent :
```bash
mkdir lab-rebase && cd lab-rebase
git init
echo "v1" > app.txt
git add . && git commit -m "Initial commit"

git checkout -b feature-x
echo "v2-feature" >> app.txt
git add . && git commit -m "feat: ajoute la fonctionnalité X"

git checkout main
echo "v2-main" >> app.txt
git add . && git commit -m "fix: corrige un bug urgent sur main"
```

**Étape 2.** Visualisez la divergence :
```bash
git log --oneline --graph --all
```

**Étape 3.** Faites une copie de ce dépôt pour comparer les deux approches :
```bash
cd ..
cp -r lab-rebase lab-rebase-copie
```

**Étape 4. (dans `lab-rebase`)** Testez le merge classique :
```bash
cd lab-rebase
git checkout main
git merge feature-x
git log --oneline --graph --all
```
Observez le commit de merge créé, avec deux branches qui se rejoignent visuellement.

**Étape 5. (dans `lab-rebase-copie`)** Testez le rebase :
```bash
cd ../lab-rebase-copie
git checkout feature-x
git rebase main
```
Comme `app.txt` a été modifié sur les deux branches, un conflit apparaît probablement. Résolvez-le :
```bash
cat app.txt
# éditez pour garder les deux lignes ou choisir
echo "v1
v2-main
v2-feature" > app.txt
git add app.txt
git rebase --continue
```

**Étape 6.** Comparez les deux graphes finaux :
```bash
git log --oneline --graph --all
```
Puis comparez avec celui de `lab-rebase` (merge). Vous constatez que le rebase donne un historique **linéaire** (pas de bifurcation visible), alors que le merge conserve la trace de la divergence.

**Étape 7.** Terminez le rebase en remettant `main` à jour (fast-forward désormais possible) :
```bash
git checkout main
git merge feature-x      # sera un simple fast-forward cette fois
git log --oneline --graph --all
```

### Pièges fréquents
- **Ne jamais rebaser une branche publique/partagée.** Si vous avez un doute, utilisez `merge`.
- Pendant un rebase, `--ours` et `--theirs` ont un sens **inversé** par rapport à un merge (pendant un rebase, "ours" = la branche de destination, "theirs" = vos propres commits en train d'être rejoués).
- Un rebase peut générer plusieurs conflits successifs (un par commit rejoué) - `git rebase --continue` après chaque résolution.

### Auto-évaluation
- Quelle est la règle d'or absolue concernant le rebase ?
- Pourquoi les commits issus d'un rebase ont-ils un hash différent des commits originaux ?
- Dans quel contexte professionnel le rebase est-il particulièrement apprécié ? (indice : historique propre avant une Pull Request)

### Défi bonus
Reproduisez le Lab 6.1 mais en ajoutant un troisième commit sur `feature-x` après le rebase initial, puis refaites un `git rebase main` pour observer comment Git ne rejoue que les commits manquants.

---

## Module 7 - Dépôts distants : clone, push, pull, fetch

### Objectifs
- Comprendre la relation entre dépôt local et dépôt distant
- Cloner, pousser, récupérer des changements
- Comprendre la différence entre `fetch` et `pull`
- Gérer les branches de suivi (tracking branches)

### Théorie

Un **dépôt distant** (remote) est une copie du dépôt hébergée ailleurs : sur GitHub, GitLab, un serveur d'entreprise, ou même un autre dossier sur votre machine. Git est distribué : il n'y a pas de copie "maîtresse" obligatoire, mais en pratique on convient d'un dépôt distant de référence, généralement appelé `origin`.

#### Le schéma complet à 4 zones

```
┌──────────────┐   add    ┌──────────────┐  commit   ┌──────────────┐   push    ┌──────────────┐
│ Working Dir   │ ───────▶│ Staging Area  │ ─────────▶│ Local Repo    │ ─────────▶│ Remote Repo   │
│               │◀─────────│              │◀───────────│ (.git)        │◀─────────│ (GitHub...)   │
└──────────────┘ restore  └──────────────┘  reset     └──────────────┘   fetch   └──────────────┘
                                                              ▲                          │
                                                              └──────── pull = fetch + merge ────┘
```

#### `fetch` vs `pull` - la distinction la plus mal comprise

- **`git fetch`** : télécharge les nouveaux commits du distant **sans toucher** à votre working directory ni à votre branche locale. C'est une opération 100% sûre, qui met simplement à jour vos branches de suivi (`origin/main` par exemple).
- **`git pull`** : équivaut à `git fetch` **suivi automatiquement** d'un `git merge` (ou `rebase` selon configuration) dans votre branche locale. Cela **modifie** votre working directory.

**Bonne pratique professionnelle :** faites souvent `git fetch` pour observer ce qui a changé sans rien impacter, et ne `pull`/`merge` que lorsque vous êtes prêt.

### Commandes essentielles

```bash
git clone <url>                       # copier un dépôt distant en local
git clone <url> mon-dossier            # cloner dans un dossier au nom choisi

git remote -v                         # lister les distants configurés (avec leurs URLs)
git remote add origin <url>            # ajouter/lier un distant nommé "origin"
git remote remove origin               # retirer un distant
git remote set-url origin <nouvelle-url> # changer l'URL d'un distant

git fetch origin                      # télécharger les nouveautés sans fusionner
git fetch --all                       # depuis tous les distants configurés

git pull origin main                  # fetch + merge (ou rebase) automatique
git pull --rebase origin main          # fetch + rebase au lieu de merge

git push origin main                  # envoyer vos commits locaux vers le distant
git push -u origin main                # envoyer ET lier la branche locale à la distante (une seule fois)
git push                              # une fois liée (-u fait), juste "git push" suffit
git push origin --delete nom-branche   # supprimer une branche sur le distant

git branch -vv                        # voir les branches locales et leur lien avec le distant
```

### Lab 7.1 - Simuler un dépôt distant en local (sans GitHub)

Pour bien comprendre le mécanisme avant d'utiliser une vraie plateforme, simulons un "serveur" avec un simple dossier.

**Étape 1.** Créez un dépôt "distant" nu (bare repository, sans working directory, exactement ce qu'héberge GitHub) :
```bash
mkdir -p ~/git-formation/serveur-simule
cd ~/git-formation/serveur-simule
git init --bare projet.git
```

**Étape 2.** Clonez-le comme si c'était un vrai serveur distant :
```bash
cd ~/git-formation
git clone serveur-simule/projet.git mon-clone
cd mon-clone
git remote -v
```

**Étape 3.** Travaillez normalement et poussez :
```bash
echo "# Mon Projet" > README.md
git add . && git commit -m "Initial commit"
git push -u origin main
```

**Étape 4.** Simulez un second développeur en clonant à nouveau dans un autre dossier :
```bash
cd ~/git-formation
git clone serveur-simule/projet.git clone-collegue
cd clone-collegue
ls
```

**Étape 5.** Le "collègue" fait un changement et le pousse :
```bash
echo "Section ajoutée par le collègue" >> README.md
git add . && git commit -m "feat: ajoute une section"
git push
```

**Étape 6.** Retournez dans `mon-clone` (vous) et récupérez le changement :
```bash
cd ~/git-formation/mon-clone
git fetch origin
git log --oneline --all --graph    # vous voyez origin/main en avance sur votre main local !
git pull
cat README.md
```

### Lab 7.2 - Gérer un conflit lors d'un pull

**Étape 1.** Modifiez le même fichier dans les deux clones, sans synchroniser entre les deux :

Dans `clone-collegue` :
```bash
echo "Ligne du collègue" >> README.md
git add . && git commit -m "Modif du collègue"
git push
```

Dans `mon-clone` (sans avoir fetché avant) :
```bash
echo "Ma propre ligne" >> README.md
git add . && git commit -m "Ma modif locale"
git push
```

**Étape 2.** Le push échoue - Git refuse car le distant a évolué entre temps :
```
! [rejected]  main -> main (fetch first)
```

**Étape 3.** Récupérez puis fusionnez (résolvant le conflit comme appris au Module 5) :
```bash
git pull
# en cas de conflit, résolvez-le comme au Module 5
git add README.md
git commit
git push
```

### Pièges fréquents
- `git push` échoue si le distant a des commits que vous n'avez pas localement - **ne jamais utiliser `git push --force`** pour "forcer" sans comprendre pourquoi (cela peut écraser le travail d'un collègue). Réservez `--force` (ou mieux, `--force-with-lease`) aux cas où vous savez exactement ce que vous faites (ex : après un rebase sur votre propre branche).
- Confondre l'URL `https://` (demande identifiants à chaque fois, sauf cache configuré) et `git@` en SSH (nécessite une clé SSH configurée, mais plus fluide ensuite).
- Oublier `-u` au premier push d'une nouvelle branche, ce qui oblige ensuite à toujours écrire `git push origin nom-branche` explicitement.

### Auto-évaluation
- Quelle est la différence exacte entre `git fetch` et `git pull` ?
- Pourquoi `git push --force` est-il dangereux en équipe ?
- Que fait l'option `-u` lors d'un premier `git push` ?

---

## Module 8 - GitHub : Pull Requests et code review

### Objectifs
- Créer un compte GitHub et un dépôt distant réel
- Comprendre le rôle d'une Pull Request (PR)
- Pratiquer un cycle complet : fork/branche, PR, review, merge

### Théorie

GitHub ajoute, par-dessus Git, une couche collaborative essentielle en entreprise :

- **Issues** : suivi de bugs, demandes de fonctionnalités, tâches.
- **Pull Request (PR)** : une proposition d'intégrer les commits d'une branche dans une autre (souvent `feature-x` → `main`), avec discussion, review, et validation avant fusion.
- **Actions** : automatisation (CI/CD) - tests automatiques, déploiement, etc.
- **Fork** : une copie complète d'un dépôt sous votre propre compte, utile pour contribuer à un projet où vous n'avez pas de droit d'écriture direct.

#### Le cycle de contribution typique

```
1. Cloner/forker le dépôt
2. Créer une branche dédiée à la tâche : feature/ajout-filtre
3. Committer son travail dessus
4. Pousser la branche vers le distant (origin ou son fork)
5. Ouvrir une Pull Request vers la branche principale
6. Les collègues commentent, demandent des changements
7. On pousse de nouveaux commits qui mettent à jour la PR automatiquement
8. Une fois approuvée → merge (par bouton GitHub, ou en CLI)
9. Supprimer la branche (nettoyage)
```

### Commandes et concepts essentiels

```bash
# Créer une branche dédiée à une fonctionnalité (convention courante)
git checkout -b feature/nom-de-la-fonctionnalite

# Pousser la branche pour la première fois
git push -u origin feature/nom-de-la-fonctionnalite

# Une fois la PR mergée sur GitHub, nettoyer localement :
git checkout main
git pull
git branch -d feature/nom-de-la-fonctionnalite
git push origin --delete feature/nom-de-la-fonctionnalite   # si pas auto-supprimée par GitHub
```

GitHub propose aussi le **CLI officiel `gh`**, qui permet de créer une PR sans quitter le terminal :
```bash
gh pr create --title "Ajoute le filtre par catégorie" --body "Description détaillée du changement"
gh pr list
gh pr checkout 42        # récupérer localement la PR #42 pour la tester
gh pr merge 42 --squash   # fusionner depuis le terminal
```

### Lab 8.1 - Créer un dépôt GitHub réel et faire votre première PR

**Étape 1.** Sur [github.com](https://github.com), créez un nouveau dépôt (ex : `formation-git-pratique`), public ou privé, **sans** cocher l'initialisation automatique d'un README si vous voulez partir d'un dépôt local existant (ou cochez-la si vous démarrez de zéro).

**Étape 2.** Liez votre dépôt local existant (par exemple `lab-recettes` du Module 2) à ce nouveau dépôt GitHub :
```bash
cd lab-recettes
git remote add origin https://github.com/VOTRE-NOM/formation-git-pratique.git
git branch -M main
git push -u origin main
```

**Étape 3.** Créez une branche pour une nouvelle fonctionnalité :
```bash
git checkout -b feature/recette-soupe
echo "## Soupe à l'oignon
- 4 oignons
- 1L de bouillon
- Pain et gruyère" > soupe.txt
git add . && git commit -m "feat: ajoute la recette de la soupe à l'oignon"
git push -u origin feature/recette-soupe
```

**Étape 4.** Sur GitHub, ouvrez l'onglet **Pull Requests** → **New Pull Request**. Sélectionnez `feature/recette-soupe` vers `main`, ajoutez un titre et une description claire, puis créez la PR.

**Étape 5.** Observez les éléments d'une PR : la liste des commits, le diff (« Files changed »), la possibilité de commenter ligne par ligne.

**Étape 6.** Cliquez sur **Merge pull request** (choisissez « Squash and merge » pour cette pratique - voir encadré ci-dessous), puis supprimez la branche via le bouton proposé par GitHub.

**Étape 7.** Synchronisez votre local :
```bash
git checkout main
git pull
git branch -d feature/recette-soupe
git log --oneline --graph --all
```

### Les trois stratégies de fusion sur GitHub

| Stratégie | Effet | Quand l'utiliser |
|---|---|---|
| **Merge commit** | conserve tous les commits + crée un commit de merge | quand l'historique détaillé de la branche a de la valeur |
| **Squash and merge** | combine tous les commits de la PR en un seul commit propre | le plus courant en entreprise pour un historique `main` lisible |
| **Rebase and merge** | rejoue chaque commit de la PR individuellement sur `main`, sans merge commit | quand on veut un historique linéaire en gardant les commits séparés |

### Lab 8.2 - Simuler une code review

**Étape 1.** Créez une nouvelle branche avec un changement volontairement imparfait :
```bash
git checkout -b feature/recette-cookies
echo "## Cookies
- 200 farine
- 100 beurre
- 1 oeuf" > cookies.txt
git add . && git commit -m "ajoute cookies"
git push -u origin feature/recette-cookies
```

**Étape 2.** Ouvrez la PR sur GitHub. Si vous travaillez seul, demandez-vous (ou demandez à un ami) : les unités sont-elles précisées (g, ml) ? Le message de commit suit-il les conventions vues au Module 2 ?

**Étape 3.** Commentez directement une ligne du diff sur GitHub (clic sur le `+` à gauche de la ligne concernée) pour suggérer : "Précise les unités (grammes) pour plus de clarté."

**Étape 4.** Corrigez localement et repoussez - observez que la PR se met à jour automatiquement avec le nouveau commit :
```bash
echo "## Cookies
- 200g de farine
- 100g de beurre
- 1 oeuf" > cookies.txt
git add . && git commit -m "fix: précise les unités de la recette de cookies"
git push
```

### Pièges fréquents
- Ouvrir une PR avec des dizaines de commits "WIP", "fix", "fix again" - privilégiez un historique propre (voir Module 14) ou utilisez Squash and merge.
- Oublier de mettre à jour sa branche avec `main` avant d'ouvrir la PR, menant à des conflits tardifs.
- Merger sa propre PR sans review dans un contexte d'équipe - même en solo, prenez l'habitude de relire le diff complet avant de fusionner.

### Auto-évaluation
- Quelle est la différence entre Merge commit, Squash and merge, et Rebase and merge ?
- Pourquoi le Squash and merge est-il souvent privilégié en entreprise ?
- Que se passe-t-il sur une PR ouverte quand vous poussez un nouveau commit sur sa branche ?

---

## Module 9 - Workflows d'équipe (Git Flow, GitHub Flow, Trunk-Based)

### Objectifs
- Connaître les principaux modèles de collaboration utilisés en entreprise
- Savoir choisir le bon workflow selon le contexte du projet
- Pratiquer un cycle complet de GitHub Flow

### Théorie

Un **workflow Git** est une convention d'équipe sur comment organiser les branches, quand les fusionner, et comment gérer les versions. Git ne force aucun modèle : c'est une décision d'équipe.

#### 1. Git Flow (modèle historique, structuré)

```
main        ──●──────────────●──────────────●──   (releases en production)
                \            / \            /
release          \      ●──●   \      ●──●
                   \    /         \    /
develop      ──●──●──●──●──●──●──●──●──●──   (intégration continue)
                  \              /
feature/x          ●──●──●──●──●
```

Branches : `main` (production), `develop` (intégration), `feature/*`, `release/*`, `hotfix/*`.

- **Avantages** : très structuré, adapté aux logiciels avec des cycles de release distincts (versions numérotées, ex: applications desktop, firmware).
- **Inconvénients** : lourd pour des équipes qui déploient en continu (web SaaS moderne).

#### 2. GitHub Flow (simple, moderne, le plus courant aujourd'hui)

```
main   ──●────●────●────●────●────●──   (toujours déployable)
            \      / \      /
feature/a    ●────●   ●────●  feature/b
```

Une seule branche longue (`main`), toujours stable et déployable. Chaque fonctionnalité = une branche courte, une PR, un merge, et c'est tout.

- **Avantages** : simple, rapide, adapté au déploiement continu.
- **Inconvénients** : moins adapté si vous devez maintenir plusieurs versions en parallèle (ex : v1 et v2 d'un logiciel client).

#### 3. Trunk-Based Development (le plus "moderne"/DevOps)

Tout le monde commite très fréquemment (parfois plusieurs fois par jour) directement sur `main` (le "trunk"), avec des branches très courtes (quelques heures) ou des **feature flags** pour cacher le code incomplet en production plutôt que de le garder isolé sur une branche longue.

- **Avantages** : intégration continue maximale, conflits minimisés (car on intègre tout, tout le temps).
- **Inconvénients** : exige une discipline forte (tests automatisés robustes, feature flags) - peu adapté aux équipes débutantes.

#### Tableau comparatif

| Critère | Git Flow | GitHub Flow | Trunk-Based |
|---|---|---|---|
| Complexité | Élevée | Faible | Moyenne (mais discipline forte) |
| Adapté à | Releases versionnées | SaaS / déploiement continu | DevOps mature, CI/CD avancé |
| Durée de vie des branches | Longue | Courte | Très courte / quasi inexistante |
| Fréquence de déploiement | Basse à moyenne | Élevée | Très élevée |

### Lab 9.1 - Pratiquer le GitHub Flow de bout en bout

**Étape 1.** Réutilisez votre dépôt `formation-git-pratique` du Module 8.

**Étape 2.** Simulez un sprint avec 3 fonctionnalités en parallèle :
```bash
git checkout main && git pull

git checkout -b feature/recette-tarte-citron
echo "## Tarte au citron" > tarte-citron.txt
git add . && git commit -m "feat: ajoute la tarte au citron"
git push -u origin feature/recette-tarte-citron

git checkout main
git checkout -b feature/recette-mousse-chocolat
echo "## Mousse au chocolat" > mousse-chocolat.txt
git add . && git commit -m "feat: ajoute la mousse au chocolat"
git push -u origin feature/recette-mousse-chocolat
```

**Étape 3.** Ouvrez une PR pour chacune sur GitHub, et fusionnez la première (`feature/recette-tarte-citron`) immédiatement (Squash and merge).

**Étape 4.** Mettez à jour la seconde branche avec les changements de `main` **avant** de la fusionner, pour éviter les conflits tardifs :
```bash
git checkout feature/recette-mousse-chocolat
git fetch origin
git merge origin/main      # ou : git rebase origin/main si la branche est encore privée
```

**Étape 5.** Fusionnez la seconde PR, puis nettoyez localement :
```bash
git checkout main
git pull
git branch -d feature/recette-tarte-citron feature/recette-mousse-chocolat
git log --oneline --graph --all
```

### Défi bonus
Mettez en place un dépôt simulant **Git Flow** : créez une branche `develop`, deux branches `feature/*` qui y fusionnent, puis une branche `release/1.0` créée depuis `develop`, qui fusionne ensuite à la fois dans `main` (avec un tag, voir Module 12) et de retour dans `develop`.

---

## Module 10 - Annuler et corriger : reset, revert, checkout, restore

### Objectifs
- Comprendre les trois modes de `git reset` (soft, mixed, hard)
- Savoir choisir entre `reset` et `revert` selon le contexte
- Utiliser `restore` et `checkout` pour annuler des modifications de fichiers

### Théorie

C'est l'un des modules les plus importants : savoir **annuler** est aussi crucial que savoir avancer. Git offre plusieurs outils selon **où** vous voulez annuler quelque chose.

#### `git reset` - déplacer le pointeur de branche (réécrit l'historique local)

`git reset` déplace `HEAD` (et la branche courante) vers un commit différent, avec 3 niveaux d'impact :

```
git reset --soft <commit>    : déplace HEAD, GARDE les changements en Staging Area
git reset --mixed <commit>   : déplace HEAD, GARDE les changements dans Working Dir (par défaut)
git reset --hard <commit>    : déplace HEAD, SUPPRIME tous les changements (irréversible sans reflog)
```

```
                    --soft : reste stagé
                   ┌─────────────────────┐
A ── B ── C ── D   │                      │
        ▲          │  --mixed : reste     │
        │          │  modifié non-stagé   │
   reset ici       │                      │
                    │  --hard : disparaît  │
                    └─────────────────────┘
```

 **`git reset --hard` est destructeur** : tout changement non commité est perdu définitivement (sauf récupération avancée via reflog, voir Module 22).

#### `git revert` - annuler en ajoutant un nouveau commit (sûr pour l'historique partagé)

Contrairement à `reset`, `revert` **ne réécrit rien** : il crée un **nouveau commit** qui annule les effets d'un commit précédent. C'est la méthode sûre pour annuler quelque chose qui a déjà été **poussé et partagé**.

```
A ── B ── C ── D            (avant revert de C)
A ── B ── C ── D ── C'      (C' annule exactement les changements de C)
```

#### `git checkout` / `git restore` - annuler des changements de fichiers

Depuis Git 2.23, `git checkout` (trop polyvalent, source de confusion) a été en partie remplacé par deux commandes plus claires :
- `git switch` : changer de branche (vu au Module 4)
- `git restore` : restaurer des fichiers

```bash
git restore fichier.txt              # annule les modifs non stagées (working dir → dernier commit)
git restore --staged fichier.txt      # désindexe (retire du stage, sans toucher au contenu)
git restore --source=HEAD~2 fichier.txt  # restaure un fichier depuis un commit précis
```

#### Tableau de décision

| Je veux... | Commande |
|---|---|
| Annuler un fichier modifié non stagé | `git restore fichier.txt` |
| Désindexer un fichier (sortir du stage) | `git restore --staged fichier.txt` |
| Annuler le dernier commit, garder les changements stagés | `git reset --soft HEAD~1` |
| Annuler le dernier commit, garder les changements mais non stagés | `git reset HEAD~1` (mixed, par défaut) |
| Annuler le dernier commit ET perdre les changements | `git reset --hard HEAD~1` |
| Annuler un commit déjà **poussé et partagé** | `git revert <hash>` |

### Commandes essentielles

```bash
git restore <fichier>                 # annule les modifs locales d'un fichier
git restore --staged <fichier>         # désindexe un fichier (reste modifié dans le working dir)
git restore .                         # annule TOUTES les modifs locales non commitées

git reset HEAD~1                      # annule le dernier commit (mixed par défaut)
git reset --soft HEAD~1                # idem mais garde tout stagé
git reset --hard HEAD~1                # idem mais supprime tout (irréversible sans reflog)
git reset --hard <hash>                # revenir précisément à un commit donné

git revert <hash>                      # crée un nouveau commit qui annule <hash>
git revert HEAD                       # annule le commit le plus récent
git revert --no-commit <hash>          # prépare le revert sans committer (pour ajuster avant)
```

### Lab 10.1 - Tester les trois modes de reset

**Étape 1.** Créez un dépôt avec quelques commits :
```bash
mkdir lab-reset && cd lab-reset
git init
echo "v1" > fichier.txt
git add . && git commit -m "commit 1"
echo "v2" > fichier.txt
git add . && git commit -m "commit 2"
echo "v3" > fichier.txt
git add . && git commit -m "commit 3"
git log --oneline
```

**Étape 2.** Testez `--soft` :
```bash
git reset --soft HEAD~1
git status              # le contenu de "commit 3" est repassé en staged
git log --oneline       # le commit 3 a disparu de l'historique
```

**Étape 3.** Re-committez pour continuer, puis testez `--mixed` :
```bash
git commit -m "commit 3 (recreated)"
git reset HEAD~1
git status               # le contenu est modifié, mais PAS stagé cette fois
```

**Étape 4.** Re-committez, puis testez `--hard` (attention, destructeur) :
```bash
git add . && git commit -m "commit 3 (recreated again)"
cat fichier.txt
git reset --hard HEAD~1
cat fichier.txt          # revenu à "v2" : le contenu de commit 3 a disparu du disque
git status               # rien à committer, tout est propre
```

### Lab 10.2 - Revert sur un historique "partagé"

**Étape 1.** Simulez un commit problématique déjà poussé :
```bash
mkdir lab-revert && cd lab-revert
git init
echo "config stable" > config.txt
git add . && git commit -m "config initiale"
echo "config CASSÉE" > config.txt
git add . && git commit -m "feat: nouvelle config (cassée par erreur)"
git log --oneline
```

**Étape 2.** Plutôt que de reset (ce qui réécrirait l'historique), revert proprement :
```bash
git revert HEAD
cat config.txt          # revenu à "config stable"
git log --oneline       # le commit cassé existe TOUJOURS dans l'historique, mais annulé par un nouveau commit
```

C'est la grande différence avec `reset` : **l'historique garde la trace de l'erreur ET de sa correction**, ce qui est précieux pour la traçabilité en équipe.

### Lab 10.3 - restore vs reset pour les fichiers

```bash
cd lab-reset
echo "modification non voulue" >> fichier.txt
git status                     # modifié, non stagé
git restore fichier.txt
git status                     # propre, modification annulée

echo "autre modification" >> fichier.txt
git add fichier.txt
git status                     # stagé
git restore --staged fichier.txt
git status                     # désindexé, mais le contenu modifié est toujours là sur le disque
cat fichier.txt
git restore fichier.txt        # cette fois on annule vraiment
```

### Pièges fréquents
- `git reset --hard` est **irréversible en apparence** : en pratique le commit existe encore quelques temps dans le `reflog` (Module 22), mais ne comptez jamais sur cette récupération comme un filet de sécurité normal.
- Faire un `reset --hard` sur un commit déjà **poussé** ne supprime rien du distant : un `push --force` serait nécessaire, ce qui est dangereux en équipe. Préférez toujours `revert` dans ce cas.
- Confondre `restore --staged` (désindexer, garde le contenu) avec `restore` tout court (annule le contenu).

### Auto-évaluation
- Quelle est la différence entre `reset --soft`, `--mixed` et `--hard` ?
- Pourquoi `revert` est-il préférable à `reset` sur un historique déjà partagé ?
- Comment désindexer un fichier sans perdre ses modifications ?

---

## Module 11 - Stash et travail temporaire

### Objectifs
- Mettre de côté un travail en cours sans le committer
- Gérer plusieurs stash simultanément
- Appliquer un stash sur une autre branche

### Théorie

`git stash` range temporairement vos modifications non commitées (working dir + staging area) dans une pile, et restaure un working directory propre. C'est extrêmement utile quand on doit, par exemple, basculer en urgence sur une autre branche sans avoir fini son travail en cours.

```
Working Dir (sale) ──git stash──▶ Pile de stash ──git stash pop──▶ Working Dir restauré
                                   [stash@{0}]
                                   [stash@{1}]
                                   [stash@{2}]
```

### Commandes essentielles

```bash
git stash                          # range les modifs en cours (working dir + staged)
git stash save "message descriptif" # idem, avec un message pour le retrouver plus tard
git stash -u                       # inclut aussi les fichiers untracked
git stash list                     # liste tous les stash en attente
git stash show stash@{0}            # voir le contenu d'un stash précis
git stash apply                    # réapplique le dernier stash SANS le retirer de la pile
git stash apply stash@{2}           # réapplique un stash précis
git stash pop                      # réapplique le dernier stash ET le retire de la pile
git stash drop stash@{0}            # supprime un stash sans l'appliquer
git stash clear                    # supprime TOUS les stash (irréversible)
git stash branch nouvelle-branche   # crée une branche à partir d'un stash (utile en cas de conflit)
```

### Lab 11.1 - Mettre de côté un travail en urgence

**Étape 1.** Créez un dépôt et commencez un travail :
```bash
mkdir lab-stash && cd lab-stash
git init
echo "version stable" > app.txt
git add . && git commit -m "Initial commit"
echo "travail en cours, pas fini..." >> app.txt
git status
```

**Étape 2.** Imaginez qu'on vous demande de corriger un bug urgent sur `main` immédiatement, mais votre travail actuel n'est pas prêt à être commité :
```bash
git stash save "WIP: travail en cours sur app.txt"
git status                    # working dir propre à nouveau !
cat app.txt                   # revenu à la version stable
```

**Étape 3.** Corrigez le bug urgent (simulé) :
```bash
echo "correction urgente" >> app.txt
git add . && git commit -m "fix: correction urgente"
```

**Étape 4.** Reprenez votre travail en cours :
```bash
git stash list
git stash pop
cat app.txt                   # vos deux changements sont là : correction urgente + travail en cours
```

### Lab 11.2 - Gérer plusieurs stash

```bash
echo "modif A" >> app.txt
git stash save "Modification A"

echo "modif B" >> app.txt
git stash save "Modification B"

git stash list
# stash@{0}: On main: Modification B
# stash@{1}: On main: Modification A

git stash apply stash@{1}     # applique la modif A sans la retirer de la pile
cat app.txt
git stash drop stash@{1}      # nettoyage une fois sûr de ne plus en avoir besoin
git stash list
```

### Pièges fréquents
- Oublier des stash empilés pendant des semaines - pensez à faire `git stash list` régulièrement et nettoyer.
- `git stash pop` peut générer un conflit s'il y a eu des changements incompatibles depuis - dans ce cas, résolvez comme un conflit normal (Module 5), le stash reste alors dans la pile jusqu'à suppression manuelle.
- Par défaut, le stash n'inclut **pas** les fichiers untracked (nouveaux fichiers jamais ajoutés) - utilisez `-u` si nécessaire.

### Auto-évaluation
- Quelle est la différence entre `git stash apply` et `git stash pop` ?
- Comment inclure les fichiers untracked dans un stash ?
- Comment visualiser le contenu d'un stash sans l'appliquer ?

---

## Module 12 - Tags et versions

### Objectifs
- Comprendre l'utilité des tags pour marquer des versions
- Différencier tags légers et tags annotés
- Pousser et gérer des tags sur un dépôt distant

### Théorie

Un **tag** est un pointeur, comme une branche, mais **immuable** (il ne se déplace jamais automatiquement). Il sert typiquement à marquer une version livrée : `v1.0.0`, `v2.3.1`, etc.

Convention très répandue : le **Semantic Versioning** (SemVer) - `MAJOR.MINOR.PATCH` :
- **MAJOR** : changement incompatible avec les versions précédentes
- **MINOR** : nouvelle fonctionnalité, rétrocompatible
- **PATCH** : correction de bug, rétrocompatible

#### Deux types de tags

| Type | Commande | Contient |
|---|---|---|
| **Léger** (lightweight) | `git tag v1.0` | juste un pointeur vers un commit |
| **Annoté** (annotated) | `git tag -a v1.0 -m "message"` | objet complet : auteur, date, message, signature possible |

**Recommandation professionnelle :** toujours utiliser des tags **annotés** pour les versions livrées - ils contiennent des métadonnées utiles et peuvent être signés cryptographiquement (GPG).

### Commandes essentielles

```bash
git tag                              # lister tous les tags
git tag v1.0.0                       # créer un tag léger sur HEAD
git tag -a v1.0.0 -m "Première version stable"  # tag annoté (recommandé)
git tag -a v0.9.0 <hash-commit> -m "..."         # tag annoté sur un commit précis (rétroactif)

git show v1.0.0                      # voir les détails d'un tag annoté
git tag -l "v1.*"                    # filtrer les tags par motif

git push origin v1.0.0                # pousser un tag précis
git push origin --tags                # pousser TOUS les tags locaux
git push --follow-tags                # pousser les commits ET les tags annotés associés

git tag -d v1.0.0                     # supprimer un tag localement
git push origin --delete v1.0.0       # supprimer un tag sur le distant

git checkout v1.0.0                   # se placer sur le commit du tag (mode "detached HEAD")
```

### Lab 12.1 - Versionner un projet

**Étape 1.** Créez un historique simple :
```bash
mkdir lab-tags && cd lab-tags
git init
echo "v0.1" > app.txt
git add . && git commit -m "feat: première version fonctionnelle"
```

**Étape 2.** Créez un tag annoté pour cette version :
```bash
git tag -a v1.0.0 -m "Première version stable, prête pour production"
git tag
git show v1.0.0
```

**Étape 3.** Continuez le développement et créez une nouvelle version :
```bash
echo "v0.2 - nouvelle fonctionnalité" >> app.txt
git add . && git commit -m "feat: ajoute une nouvelle fonctionnalité"
git tag -a v1.1.0 -m "Ajoute la fonctionnalité X"
```

**Étape 4.** Simulez un bug critique nécessitant un correctif :
```bash
echo "correctif urgent" >> app.txt
git add . && git commit -m "fix: corrige une faille de sécurité"
git tag -a v1.1.1 -m "Correctif de sécurité critique"
git log --oneline --decorate
```

**Étape 5.** Naviguez entre les versions :
```bash
git checkout v1.0.0
cat app.txt              # contenu tel qu'il était à cette version précise
git checkout main        # ou le nom de votre branche principale, pour revenir au présent
```

**Étape 6.** Si vous avez un dépôt distant (Module 8), poussez vos tags :
```bash
git push origin --tags
```

### Pièges fréquents
- `git checkout v1.0.0` place le dépôt en **detached HEAD** (vous n'êtes sur aucune branche) - tout commit fait dans cet état risque d'être perdu si vous ne créez pas une branche pour le conserver (`git checkout -b correctif-depuis-v1.0.0`).
- Par défaut, `git push` ne pousse **pas** les tags - il faut le faire explicitement.
- Oublier `-a` (tag léger au lieu d'annoté) prive le tag de métadonnées importantes pour une release officielle.

### Auto-évaluation
- Quelle est la différence entre un tag léger et un tag annoté ?
- Que signifie chaque chiffre dans le Semantic Versioning `2.4.1` ?
- Pourquoi faut-il `git push origin --tags` en plus de `git push` ?

---

## Module 13 - .gitignore et gestion des fichiers

### Objectifs
- Exclure correctement des fichiers du suivi Git
- Maîtriser la syntaxe des patterns `.gitignore`
- Gérer le cas d'un fichier déjà suivi qu'on veut ignorer rétroactivement

### Théorie

Le fichier `.gitignore` indique à Git quels fichiers/dossiers **ne jamais suivre** : fichiers générés (builds), dépendances (`node_modules/`), secrets (`.env`), fichiers spécifiques à l'OS ou à l'éditeur (`.DS_Store`, `.idea/`).

**Pourquoi c'est essentiel professionnellement :**
- Évite de polluer l'historique avec des fichiers volumineux ou générés automatiquement.
- Évite de **divulguer des secrets** (clés API, mots de passe) dans l'historique Git - une fuite très fréquente et grave en entreprise.
- Garde le dépôt léger et pertinent.

### Syntaxe de `.gitignore`

```gitignore
# Commentaire

# Ignorer un fichier précis
secret.env

# Ignorer tous les fichiers avec une extension
*.log
*.tmp

# Ignorer un dossier entier (et tout son contenu)
node_modules/
dist/
build/

# Ignorer partout dans l'arborescence (pas seulement à la racine)
**/__pycache__/

# Exception : NE PAS ignorer un fichier précis malgré une règle plus large
*.log
!important.log

# Ignorer un fichier seulement à la racine (pas dans les sous-dossiers)
/config.local.json
```

### Commandes essentielles

```bash
git status --ignored                  # voir aussi les fichiers ignorés
git check-ignore -v fichier.txt        # vérifier QUELLE règle ignore un fichier précis (débogage)

# Pour ignorer rétroactivement un fichier déjà suivi par Git :
git rm --cached fichier-deja-suivi.txt   # le retire du suivi SANS le supprimer du disque
# puis ajoutez-le à .gitignore

# Fichier d'exclusion personnel, non partagé avec l'équipe (ne touche pas .gitignore du projet)
# à éditer dans : .git/info/exclude
```

### Lab 13.1 - Mettre en place un .gitignore complet

**Étape 1.** Créez un projet simulant une vraie structure :
```bash
mkdir lab-gitignore && cd lab-gitignore
git init
mkdir node_modules
echo "dépendance fictive" > node_modules/package-fictif.js
echo "SECRET_KEY=abc123" > .env
echo "console.log('app')" > app.js
echo "logs de debug" > debug.log
```

**Étape 2.** Sans `.gitignore`, observez le problème :
```bash
git status
```
Tout apparaît comme untracked, y compris `node_modules/` et `.env` - un risque réel si on les committe par erreur.

**Étape 3.** Créez un `.gitignore` adapté :
```bash
cat > .gitignore << 'EOF'
# Dépendances
node_modules/

# Secrets et configuration locale
.env
*.local

# Logs
*.log

# Fichiers système
.DS_Store
EOF
```

**Étape 4.** Vérifiez l'effet :
```bash
git status
```
Seuls `.gitignore` et `app.js` apparaissent désormais - exactement ce qu'on veut suivre.

**Étape 5.** Testez `check-ignore` pour déboguer une règle :
```bash
git check-ignore -v .env
git check-ignore -v node_modules/package-fictif.js
```

**Étape 6.** Committez le tout proprement :
```bash
git add .
git status                # vérifiez qu'aucun secret n'apparaît avant de commiter !
git commit -m "Initial commit avec .gitignore approprié"
```

### Lab 13.2 - Corriger l'erreur d'avoir déjà suivi un fichier sensible

**Étape 1.** Simulez l'erreur classique : un fichier `.env` committé par accident avant d'avoir pensé au `.gitignore` :
```bash
mkdir lab-gitignore-fix && cd lab-gitignore-fix
git init
echo "API_KEY=secret123" > .env
echo "code" > app.js
git add . && git commit -m "Initial commit (erreur : .env inclus)"
```

**Étape 2.** Retirez-le du suivi (sans le supprimer du disque) :
```bash
echo ".env" > .gitignore
git rm --cached .env
git add .gitignore
git commit -m "fix: retire .env du suivi Git et ajoute .gitignore"
git status
ls -la                    # .env existe toujours sur le disque
```

 **Important :** cette correction retire le fichier des **futurs** commits, mais **il reste visible dans l'historique passé** (dans les anciens commits). Si le secret est sensible (clé API réelle), il faut le considérer comme compromis et le **régénérer**, puis éventuellement réécrire l'historique (voir Module 20) pour le faire disparaître complètement - mais la priorité absolue reste de révoquer/changer le secret exposé.

### Pièges fréquents
- Croire que `.gitignore` supprime un fichier déjà suivi - il n'empêche que le suivi **futur** de nouveaux fichiers correspondant aux règles.
- Mettre des règles trop larges qui ignorent accidentellement des fichiers de code utiles.
- Committer un secret puis "juste" l'ajouter au `.gitignore` ensuite, en pensant que le danger est écarté - le secret reste dans l'historique tant qu'on ne le réécrit pas (Module 20) et doit être révoqué.

### Auto-évaluation
- Que fait `git rm --cached` par rapport à `git rm` ?
- Si vous ajoutez `*.log` à `.gitignore`, que se passe-t-il pour un fichier `.log` déjà suivi depuis longtemps ?
- Quelle est la bonne pratique immédiate si une clé API a été committée par erreur ?

---

## Module 14 - Rebase interactif et réécriture d'historique

### Objectifs
- Maîtriser `git rebase -i` pour nettoyer un historique local
- Combiner, réordonner, modifier, supprimer des commits
- Comprendre les limites et dangers de la réécriture d'historique

### Théorie

Le **rebase interactif** (`git rebase -i`) ouvre un éditeur listant les commits à rejouer, avec une action possible pour chacun. C'est l'outil de prédilection pour **nettoyer son historique avant de le partager** (avant une PR par exemple).

```bash
git rebase -i HEAD~4
```
ouvre un éditeur avec quelque chose comme :
```
pick a1b2c3d Premier commit
pick e4f5g6h Deuxième commit (typo dans le message)
pick i7j8k9l WIP travail en cours
pick m0n1o2p Fix du WIP précédent

# Commandes possibles :
# p, pick   = garder le commit tel quel
# r, reword = garder le commit mais modifier son message
# e, edit   = s'arrêter sur ce commit pour le modifier (contenu)
# s, squash = fusionner avec le commit précédent (en gardant les 2 messages)
# f, fixup  = comme squash, mais SUPPRIME le message de ce commit
# d, drop   = supprimer complètement ce commit
```

### Commandes essentielles

```bash
git rebase -i HEAD~5                 # rebase interactif sur les 5 derniers commits
git rebase -i <hash-du-commit-parent> # rebase interactif depuis un commit précis

# Pendant le rebase (si "edit" choisi sur un commit) :
git commit --amend                   # modifier le commit sur lequel on s'est arrêté
git rebase --continue                # poursuivre après une modification ou résolution

git rebase --abort                   # tout annuler et revenir à l'état d'avant
git rebase --skip                    # ignorer le commit problématique actuel
```

### Lab 14.1 - Nettoyer un historique "brouillon" avant une PR

**Étape 1.** Simulez un historique de travail typique, avec des commits désordonnés :
```bash
mkdir lab-rebase-interactif && cd lab-rebase-interactif
git init
echo "fonction A" > app.txt
git add . && git commit -m "ajoute fonction A"

echo "fonction A corrigée" > app.txt
git add . && git commit -m "fix typo"

echo "fonction B en cours" >> app.txt
git add . && git commit -m "WIP fonction B"

echo "fonction B terminée" >> app.txt
git add . && git commit -m "fix fonction B (suite du WIP precedent)"

git log --oneline
```

**Étape 2.** Lancez le rebase interactif sur ces 4 commits :
```bash
git rebase -i HEAD~4
```

**Étape 3.** Dans l'éditeur, transformez le plan pour fusionner les commits liés. Par exemple :
```
pick a1b2c3d ajoute fonction A
fixup e4f5g6h fix typo
pick i7j8k9l WIP fonction B
fixup m0n1o2p fix fonction B (suite du WIP precedent)
```
(le `fixup` du 2e commit fusionne silencieusement la correction de typo dans le premier commit ; idem pour le 4e avec le 3e). Sauvegardez et fermez l'éditeur.

**Étape 4.** Si on a choisi `pick` au lieu de `fixup`/`squash` pour un message à reformuler, Git ouvrira un second éditeur pour le message final - ajustez-le proprement, par exemple :
```
feat: ajoute la fonction A
feat: ajoute la fonction B
```

**Étape 5.** Vérifiez le résultat :
```bash
git log --oneline
```
Vous êtes passé de 4 commits désordonnés à 2 commits propres et significatifs.

### Lab 14.2 - Réordonner et supprimer des commits

**Étape 1.** Créez un historique avec un commit à supprimer (ex: un fichier de debug oublié) :
```bash
mkdir lab-rebase-drop && cd lab-rebase-drop
git init
echo "v1" > app.txt
git add . && git commit -m "feat: version initiale"

echo "console.log('debug temporaire')" > debug.txt
git add . && git commit -m "oops: fichier de debug ajouté par erreur"

echo "v2" >> app.txt
git add . && git commit -m "feat: nouvelle fonctionnalité"
```

**Étape 2.** Lancez le rebase interactif et supprimez le commit indésirable :
```bash
git rebase -i HEAD~3
```
Changez `pick` en `drop` (ou supprimez simplement la ligne) pour le commit de debug :
```
pick xxxxx feat: version initiale
drop yyyyy oops: fichier de debug ajouté par erreur
pick zzzzz feat: nouvelle fonctionnalité
```

**Étape 3.** Vérifiez :
```bash
git log --oneline
ls                       # debug.txt n'existe plus
```

### Pièges fréquents
- **Règle d'or, encore et toujours :** ne jamais faire de rebase interactif sur des commits déjà poussés et récupérés par d'autres. Limitez-le à votre travail local non partagé, ou à votre propre branche de feature avant ouverture de PR (avec accord d'équipe si la branche a déjà été partagée).
- En cas d'erreur pendant un rebase interactif complexe, n'hésitez jamais à `git rebase --abort` plutôt que de s'enfoncer dans la confusion.
- L'ordre des lignes dans l'éditeur représente l'ordre chronologique du plus ancien (en haut) au plus récent (en bas) - c'est l'inverse de `git log` par défaut, source classique de confusion.

### Auto-évaluation
- Quelle est la différence entre `squash` et `fixup` ?
- Que se passe-t-il si vous supprimez (`drop`) un commit qui introduisait un fichier ?
- Pourquoi l'ordre des commits dans l'éditeur de rebase interactif est-il inversé par rapport à `git log` ?

---

## Module 15 - Cherry-pick et gestion fine des commits

### Objectifs
- Appliquer un commit précis d'une branche vers une autre
- Comprendre les cas d'usage typiques (hotfix, backport)
- Gérer les conflits pendant un cherry-pick

### Théorie

`git cherry-pick` applique **un seul commit précis** (avec son contenu et son message) sur la branche courante, sans toucher au reste de la branche d'origine. C'est utile quand vous voulez **un changement isolé**, sans fusionner toute une branche.

```
Avant :
main         ── A ── B
feature           \
                    C ── D ── E

Après "git cherry-pick D" (exécuté depuis main) :
main         ── A ── B ── D'   (D' = copie de D, nouveau hash)
feature           \
                    C ── D ── E
```

#### Cas d'usage typiques en entreprise
- **Hotfix urgent** : un correctif fait sur une branche de développement doit être appliqué immédiatement en production, sans attendre la fusion de toute la branche.
- **Backport** : porter un correctif de la branche principale vers une ancienne version maintenue en parallèle (ex : `release/1.x`).

### Commandes essentielles

```bash
git cherry-pick <hash>                 # applique ce commit précis sur la branche courante
git cherry-pick <hash1> <hash2>         # plusieurs commits à la suite
git cherry-pick <hash1>..<hash2>        # une plage de commits (exclut hash1, inclut hash2)
git cherry-pick --no-commit <hash>      # applique les changements sans committer (pour ajuster avant)
git cherry-pick --continue              # après résolution d'un conflit pendant le cherry-pick
git cherry-pick --abort                 # annuler un cherry-pick en cours
```

### Lab 15.1 - Appliquer un correctif isolé d'une branche à une autre

**Étape 1.** Créez un scénario réaliste : une branche de dev avec plusieurs commits, dont un seul doit partir en production immédiatement :
```bash
mkdir lab-cherry-pick && cd lab-cherry-pick
git init
echo "v1" > app.txt
git add . && git commit -m "feat: version initiale"

git checkout -b dev
echo "nouvelle fonctionnalité en cours" >> app.txt
git add . && git commit -m "feat: fonctionnalité en développement (pas encore prête)"

echo "correctif sécurité critique" >> app.txt
git add . && git commit -m "fix: corrige une faille de sécurité critique"

echo "autre fonctionnalité en cours" >> app.txt
git add . && git commit -m "feat: autre fonctionnalité non terminée"

git log --oneline
```

**Étape 2.** Identifiez le hash du commit de sécurité (2e commit de la liste) :
```bash
git log --oneline
# notez le hash du commit "fix: corrige une faille de sécurité critique"
```

**Étape 3.** Revenez sur `main` (qui représente la production) et appliquez uniquement ce commit :
```bash
git checkout main
git cherry-pick <hash-du-commit-fix>
git log --oneline
cat app.txt
```
Seul le correctif de sécurité est présent sur `main` - les fonctionnalités inachevées restent isolées sur `dev`.

### Lab 15.2 - Gérer un conflit pendant un cherry-pick

**Étape 1.** Créez une situation de conflit volontaire :
```bash
mkdir lab-cherry-conflit && cd lab-cherry-conflit
git init
echo "ligne originale" > fichier.txt
git add . && git commit -m "Initial commit"

git checkout -b branche-a
echo "modifiée par branche-a" > fichier.txt
git add . && git commit -m "Modification sur branche-a"

git checkout main
echo "modifiée par main" > fichier.txt
git add . && git commit -m "Modification sur main"
```

**Étape 2.** Tentez le cherry-pick - un conflit apparaît :
```bash
git log --oneline branche-a
git cherry-pick <hash-du-commit-sur-branche-a>
git status
```

**Étape 3.** Résolvez comme un conflit classique (Module 5) :
```bash
echo "version fusionnée manuellement" > fichier.txt
git add fichier.txt
git cherry-pick --continue
```

### Pièges fréquents
- Le commit créé par cherry-pick a un **hash différent** de l'original - ce qui peut créer une confusion si on cherry-pick puis qu'on merge plus tard la branche entière (le contenu identique mais hash différent peut compliquer la lecture de l'historique).
- Cherry-picker en chaîne de nombreux commits revient presque à un rebase manuel - si c'est le besoin réel, `git rebase` est souvent plus adapté.
- Oublier `--continue` après résolution d'un conflit pendant un cherry-pick multi-commits, laissant l'opération bloquée.

### Auto-évaluation
- Dans quel scénario professionnel le cherry-pick est-il particulièrement utile ?
- Le commit créé par cherry-pick a-t-il le même hash que l'original ?
- Quelle commande annule un cherry-pick en cours de conflit ?

---

## Module 16 - Git Bisect : débogage par dichotomie

### Objectifs
- Localiser automatiquement le commit ayant introduit un bug
- Utiliser bisect manuellement et en mode automatisé (avec un script de test)

### Théorie

`git bisect` utilise une **recherche dichotomique (binaire)** dans l'historique pour trouver rapidement quel commit a introduit une régression, même parmi des centaines de commits. Au lieu de tester un par un linéairement, vous indiquez à Git si le commit testé est "bon" ou "mauvais", et Git divise l'espace de recherche par deux à chaque itération.

Avec 1000 commits entre une version saine et une version cassée, une recherche linéaire prendrait jusqu'à 1000 tests ; bisect en prend environ **log2(1000) ≈ 10**.

### Commandes essentielles

```bash
git bisect start                      # démarrer une session de bisect
git bisect bad                        # marquer le commit actuel (HEAD) comme défectueux
git bisect bad <hash>                  # marquer un commit précis comme défectueux
git bisect good <hash>                 # marquer un commit précis comme sain
git bisect good                       # marquer le commit actuel comme sain

# Git checkout automatiquement un commit "au milieu" après chaque good/bad - testez, puis répétez

git bisect reset                      # terminer la session et revenir à l'état initial

# Mode automatisé avec un script de test (très puissant) :
git bisect run ./script-de-test.sh
```

### Lab 16.1 - Trouver un bug introduit dans l'historique

**Étape 1.** Construisez un historique avec un bug caché à un endroit précis :
```bash
mkdir lab-bisect && cd lab-bisect
git init

for i in $(seq 1 15); do
  echo "version $i" > app.txt
  if [ "$i" -eq 9 ]; then
    echo "BUG_INTRODUIT=true" >> app.txt
  fi
  git add . && git commit -m "commit $i"
done

git log --oneline
```
(le "bug" a été introduit au commit 9, mais imaginez ne pas le savoir)

**Étape 2.** Démarrez le bisect :
```bash
git bisect start
git bisect bad HEAD                    # le dernier commit est cassé
git bisect good $(git log --oneline | tail -1 | cut -d' ' -f1)   # le tout premier commit était sain
```

**Étape 3.** Git vous place automatiquement sur un commit "au milieu". Testez s'il contient le bug :
```bash
cat app.txt
```
Si `BUG_INTRODUIT=true` est présent → `git bisect bad`. Sinon → `git bisect good`. Répétez jusqu'à ce que Git annonce le commit responsable.

**Étape 4.** Une fois terminé, revenez à l'état normal :
```bash
git bisect reset
```

### Lab 16.2 - Automatiser la recherche avec un script

**Étape 1.** Dans le même dépôt, créez un script de test qui vérifie automatiquement la présence du bug :
```bash
cat > test-bug.sh << 'EOF'
#!/bin/bash
if grep -q "BUG_INTRODUIT=true" app.txt; then
  exit 1   # 1 = "bad" pour bisect
else
  exit 0   # 0 = "good" pour bisect
fi
EOF
chmod +x test-bug.sh
```

**Étape 2.** Lancez le bisect automatisé :
```bash
git bisect start HEAD $(git log --oneline | tail -1 | cut -d' ' -f1)
git bisect run ./test-bug.sh
```
Git teste automatiquement chaque commit candidat et identifie le coupable sans aucune intervention manuelle.

**Étape 3.** Terminez la session :
```bash
git bisect reset
```

### Pièges fréquents
- Oublier `git bisect reset` à la fin, laissant le dépôt dans un état "detached HEAD" déroutant.
- Un script de test pour `bisect run` doit retourner un code de sortie **0 pour "good"** et **différent de 0 pour "bad"** (convention Unix standard) - l'inverse de ce qu'on pourrait intuitivement penser.
- Le bisect suppose que le bug est **monotone** dans l'historique (une fois introduit, il reste présent) - si le bug apparaît et disparaît de façon non linéaire, les résultats seront incohérents.

### Auto-évaluation
- Pourquoi `git bisect` est-il beaucoup plus rapide qu'une recherche linéaire sur un historique de 1000 commits ?
- Quel code de sortie un script doit-il renvoyer pour signaler un commit "bad" à `git bisect run` ?
- Que faut-il faire impérativement à la fin d'une session de bisect ?

---

## Module 17 - Submodules et Subtrees

### Objectifs
- Comprendre quand et pourquoi inclure un dépôt Git dans un autre
- Utiliser les submodules
- Connaître l'alternative subtree et ses avantages

### Théorie

Parfois un projet doit inclure le code d'un **autre dépôt Git** (une bibliothèque partagée, un composant commun à plusieurs projets). Deux approches existent.

#### Submodules

Un **submodule** est une référence vers un commit précis d'un autre dépôt, stockée dans le dépôt parent. Le code du submodule **n'est pas dupliqué** dans l'historique parent - seul un pointeur (commit hash) y est stocké.

```
mon-projet/
├── src/
├── .gitmodules          ← fichier de config listant les submodules
└── librairie-partagee/  ← submodule, pointe vers un commit précis d'un autre dépôt
```

- **Avantages** : historique séparé propre, mises à jour explicites et contrôlées.
- **Inconvénients** : réputés peu intuitifs ; chaque clone nécessite une étape supplémentaire (`--recurse-submodules`), oubliée très souvent par les nouveaux contributeurs.

#### Subtrees

Un **subtree** **fusionne réellement** le code d'un autre dépôt dans l'historique du projet courant, comme s'il avait toujours fait partie du même dépôt.

- **Avantages** : aucune étape supplémentaire pour les autres contributeurs (`git clone` classique suffit), pas de risque d'oubli.
- **Inconvénients** : alourdit l'historique du dépôt parent, mises à jour un peu plus complexes en ligne de commande.

#### Quand utiliser quoi ?

| Critère | Submodule | Subtree |
|---|---|---|
| Simplicité pour les autres contributeurs | Faible (étape en plus) | Élevée (transparent) |
| Séparation propre des historiques | Oui | Non (fusionné) |
| Mises à jour fréquentes de la dépendance | Pratique | Plus lourd |
| Popularité actuelle | Encore utilisé, mais souvent remplacé par des gestionnaires de paquets (npm, pip...) | Moins courant, niche |

### Commandes essentielles - Submodules

```bash
git submodule add <url> chemin/dossier   # ajouter un submodule
git submodule init                       # initialiser les submodules après un clone classique
git submodule update                     # récupérer le contenu des submodules déjà initialisés
git submodule update --init --recursive   # tout faire en une commande (cas le plus courant)

git clone --recurse-submodules <url>      # cloner un dépôt ET ses submodules directement

git submodule update --remote             # mettre à jour un submodule vers le dernier commit de sa branche distante
git submodule status                      # voir l'état de chaque submodule (commit actuel, à jour ou non)

git submodule deinit chemin/dossier        # retirer un submodule (étape 1)
git rm chemin/dossier                      # retirer un submodule (étape 2)
```

### Commandes essentielles - Subtree

```bash
git subtree add --prefix=dossier <url> main --squash    # ajouter un dépôt externe en subtree
git subtree pull --prefix=dossier <url> main --squash    # récupérer les mises à jour
git subtree push --prefix=dossier <url> main             # repousser des changements locaux vers le dépôt source
```

### Lab 17.1 - Ajouter et utiliser un submodule

**Étape 1.** Créez deux dépôts : un projet principal, et une "librairie" séparée :
```bash
mkdir -p ~/git-formation/librairie-utils
cd ~/git-formation/librairie-utils
git init
echo "function utilFunction() { return 42; }" > utils.js
git add . && git commit -m "Initial commit de la librairie"
```

**Étape 2.** Créez le projet principal et ajoutez la librairie en submodule :
```bash
mkdir -p ~/git-formation/projet-principal
cd ~/git-formation/projet-principal
git init
echo "# Mon Projet" > README.md
git add . && git commit -m "Initial commit"

git submodule add ~/git-formation/librairie-utils libs/utils
git status
cat .gitmodules
```

**Étape 3.** Committez l'ajout du submodule :
```bash
git add .
git commit -m "feat: ajoute la librairie utils en submodule"
git log --oneline
```

**Étape 4.** Simulez un clone par un autre développeur, et observez ce qui se passe sans précaution :
```bash
cd ~/git-formation
git clone projet-principal projet-clone
cd projet-clone
ls libs/utils                # vide ! le submodule n'est pas initialisé automatiquement
```

**Étape 5.** Initialisez correctement le submodule :
```bash
git submodule update --init --recursive
ls libs/utils                # le contenu apparaît maintenant
```

### Pièges fréquents
- Cloner un dépôt avec submodules sans `--recurse-submodules` (ou sans faire `submodule update --init` après) laisse des dossiers vides - l'erreur la plus fréquente avec les submodules.
- Un submodule pointe vers un **commit précis**, pas vers une branche : il ne se met jamais à jour automatiquement, même si la librairie évolue - mise à jour manuelle requise.
- Beaucoup d'équipes modernes préfèrent un gestionnaire de paquets (npm, pip, cargo...) plutôt que des submodules quand c'est possible, réservant les submodules aux cas où aucun gestionnaire de paquets adapté n'existe.

### Auto-évaluation
- Quelle est la différence fondamentale entre submodule et subtree ?
- Pourquoi un dossier de submodule peut-il apparaître vide après un simple `git clone` ?
- Un submodule se met-il à jour automatiquement quand la librairie source évolue ?

---

## Module 18 - Hooks Git : automatiser des actions

### Objectifs
- Comprendre le rôle des hooks Git
- Créer un hook local pour automatiser une vérification
- Connaître les hooks les plus utilisés en entreprise

### Théorie

Un **hook** est un script que Git exécute automatiquement à des moments précis du cycle de vie (avant un commit, après un commit, avant un push, etc.). Ils permettent d'automatiser des vérifications de qualité, formater du code, empêcher des push erronés, etc.

Les hooks vivent dans `.git/hooks/` et **ne sont pas versionnés par défaut** (le dossier `.git` n'est jamais poussé) - pour les partager en équipe, on utilise généralement un outil comme **Husky** (JavaScript) ou on les stocke dans un dossier suivi par Git puis on les copie/symlinke vers `.git/hooks/`.

#### Hooks les plus courants

| Hook | Déclenché | Usage typique |
|---|---|---|
| `pre-commit` | avant la création du commit | linter, formatage automatique, tests rapides |
| `commit-msg` | après rédaction du message, avant validation | valider le format du message (Conventional Commits) |
| `pre-push` | avant l'envoi vers le distant | lancer la suite de tests complète, empêcher un push sur `main` |
| `post-merge` | après un merge réussi | réinstaller les dépendances si `package.json` a changé |
| `post-checkout` | après un changement de branche | rappeler de relancer un build |

### Mise en place

```bash
ls .git/hooks/                    # Git crée des exemples .sample par défaut, désactivés
cat .git/hooks/pre-commit.sample   # exemple fourni par Git lui-même

# Pour activer un hook : créer le fichier SANS l'extension .sample, et le rendre exécutable
chmod +x .git/hooks/pre-commit
```

### Lab 18.1 - Créer un hook pre-commit qui bloque les mots interdits

**Étape 1.** Créez un dépôt de test :
```bash
mkdir lab-hooks && cd lab-hooks
git init
```

**Étape 2.** Créez un hook `pre-commit` qui empêche de committer si le mot "TODO" ou "FIXME" traîne dans le code (cas réel fréquent en entreprise pour éviter d'oublier du travail inachevé) :
```bash
cat > .git/hooks/pre-commit << 'EOF'
#!/bin/bash
if git diff --cached | grep -E "^\+.*(TODO|FIXME)" > /dev/null; then
  echo " Commit bloqué : du code contient TODO ou FIXME non résolu."
  echo "Retirez-les ou utilisez 'git commit --no-verify' pour forcer (déconseillé)."
  exit 1
fi
exit 0
EOF
chmod +x .git/hooks/pre-commit
```

**Étape 3.** Testez le hook :
```bash
echo "// TODO: corriger ce bug plus tard" > app.js
git add .
git commit -m "ajoute app.js"
```
Le commit doit être **refusé** par le hook.

**Étape 4.** Corrigez et retentez :
```bash
echo "// code propre et terminé" > app.js
git add .
git commit -m "feat: ajoute app.js"
```
Cette fois, le commit passe.

**Étape 5.** (Information) Pour forcer un commit malgré un hook, en cas réellement justifié :
```bash
git commit --no-verify -m "message"
```

### Lab 18.2 - Hook commit-msg pour valider le format Conventional Commits

**Étape 1.** Créez un hook qui vérifie que le message respecte le format `type: description` :
```bash
cat > .git/hooks/commit-msg << 'EOF'
#!/bin/bash
MESSAGE=$(cat "$1")
PATTERN="^(feat|fix|docs|style|refactor|test|chore)(\(.+\))?: .+"

if ! [[ "$MESSAGE" =~ $PATTERN ]]; then
  echo " Format de message invalide."
  echo "Format attendu : type: description (ex: feat: ajoute le filtre produit)"
  echo "Types valides : feat, fix, docs, style, refactor, test, chore"
  exit 1
fi
exit 0
EOF
chmod +x .git/hooks/commit-msg
```

**Étape 2.** Testez avec un message non conforme :
```bash
echo "test" >> app.js
git add .
git commit -m "ajout test"          # devrait échouer
```

**Étape 3.** Testez avec un message conforme :
```bash
git commit -m "test: ajoute une ligne de test"   # devrait réussir
```

### Pièges fréquents
- Les hooks dans `.git/hooks/` **ne sont jamais partagés** automatiquement via `git clone` - pour les partager en équipe, stockez-les dans un dossier versionné (ex : `scripts/git-hooks/`) avec un script d'installation, ou utilisez un outil dédié (Husky pour Node.js, pre-commit pour Python).
- Oublier `chmod +x` sur le script de hook - il sera silencieusement ignoré par Git sans cette permission.
- Des hooks trop lents (ex : lancer toute la suite de tests à chaque commit) découragent leur usage - réservez les vérifications lourdes au `pre-push`.

### Auto-évaluation
- Pourquoi les hooks ne sont-ils pas partagés automatiquement entre collaborateurs via `git clone` ?
- Quelle commande permet de forcer un commit en ignorant les hooks ?
- Citez un cas d'usage pertinent pour un hook `pre-push` plutôt que `pre-commit`.

---

## Module 19 - Plumbing et internals : comment Git fonctionne vraiment

### Objectifs
- Comprendre les objets internes de Git (blob, tree, commit, ref)
- Manipuler directement la base de données Git avec les commandes "plumbing"
- Démystifier complètement le fonctionnement interne de Git

### Théorie

Git distingue les commandes **"porcelain"** (l'interface conviviale qu'on utilise au quotidien : `commit`, `branch`, `merge`...) des commandes **"plumbing"** (les briques bas niveau sur lesquelles tout repose). Comprendre le plumbing permet de vraiment démystifier Git.

#### Les 4 types d'objets stockés dans `.git/objects/`

| Objet | Contient |
|---|---|
| **blob** | le contenu brut d'un fichier (juste les données, pas le nom !) |
| **tree** | une structure de dossier : liste de noms de fichiers/dossiers + leurs hash blob/tree |
| **commit** | pointeur vers un tree (l'état racine du projet), un ou plusieurs parents, auteur, message |
| **tag** (annoté) | pointeur vers un commit, avec métadonnées additionnelles |

```
commit ──▶ tree (racine) ──▶ tree (sous-dossier) ──▶ blob (contenu fichier1.txt)
                          └─▶ blob (contenu fichier2.txt)
                ▲
                │ parent
            commit précédent
```

Chaque objet est identifié par le **hash SHA-1 (ou SHA-256 sur les dépôts récents configurés ainsi) de son contenu**. C'est pourquoi le hash d'un commit change si n'importe quoi en amont change (le contenu d'un fichier, le message, l'auteur, le parent...) : c'est un système de stockage **adressé par contenu**.

### Commandes plumbing essentielles

```bash
git hash-object fichier.txt              # calcule le hash SHA d'un contenu (sans le stocker)
git hash-object -w fichier.txt            # calcule ET stocke ce contenu comme objet blob

git cat-file -t <hash>                    # affiche le TYPE d'un objet (blob/tree/commit/tag)
git cat-file -p <hash>                    # affiche le CONTENU d'un objet (pretty-print)

git rev-parse HEAD                        # résout une référence en son hash complet
git rev-parse --short HEAD                 # version courte du hash

git ls-tree HEAD                          # liste le contenu du tree racine du commit HEAD
git ls-tree -r HEAD                        # récursivement, jusqu'aux fichiers

git update-ref refs/heads/ma-branche <hash>  # créer/déplacer une branche manuellement (bas niveau)
```

### Lab 19.1 - Créer un commit "à la main" avec les commandes plumbing

Cet exercice est volontairement pédagogique : en pratique, on utilise toujours `git add`/`git commit`, mais le refaire à la main dévoile entièrement la mécanique.

**Étape 1.** Créez un dépôt vide et observez sa structure :
```bash
mkdir lab-internals && cd lab-internals
git init
find .git/objects -type f     # vide pour l'instant, aucun objet stocké
```

**Étape 2.** Créez un blob manuellement, sans passer par `git add` :
```bash
echo "Contenu de mon premier fichier" > fichier1.txt
git hash-object -w fichier1.txt
```
Notez le hash retourné (ex : `8f94139...`).

**Étape 3.** Inspectez cet objet directement :
```bash
git cat-file -t 8f94139...    # remplacez par votre hash réel
git cat-file -p 8f94139...
```
Vous voyez : type = `blob`, contenu = exactement le texte du fichier.

**Étape 4.** Créez un tree référençant ce blob (associe un nom de fichier au blob) :
```bash
git update-index --add --cacheinfo 100644 8f94139... fichier1.txt
git write-tree
```
Notez le hash du tree retourné.

**Étape 5.** Créez un commit pointant vers ce tree :
```bash
echo "Premier commit créé manuellement" | git commit-tree <hash-du-tree>
```
Git retourne le hash du commit créé !

**Étape 6.** Pointez votre branche `main` vers ce commit créé manuellement :
```bash
git update-ref refs/heads/main <hash-du-commit>
git log --oneline
cat fichier1.txt
```
Vous venez de recréer, étape par étape, ce que `git add` + `git commit` font automatiquement.

### Lab 19.2 - Explorer un commit existant en profondeur

**Étape 1.** Reprenez un dépôt avec quelques commits (par exemple `lab-recettes` du Module 2).

**Étape 2.** Trouvez le hash du dernier commit et explorez sa structure :
```bash
git rev-parse HEAD
git cat-file -p HEAD              # affiche : tree, parent, author, committer, message
```

**Étape 3.** Suivez le pointeur vers le tree :
```bash
git cat-file -p HEAD^{tree}
```
Vous voyez la liste des fichiers à la racine, chacun avec son propre hash de blob ou de sous-tree.

**Étape 4.** Récupérez le contenu d'un blob précis pointé par ce tree :
```bash
git cat-file -p <hash-du-blob-affiché>
```
Vous retrouvez exactement le contenu du fichier correspondant.

### Pièges fréquents
- Confondre le hash d'un **contenu** (qui ne change jamais pour un contenu identique, même dans des fichiers différents - Git dédoublonne automatiquement) avec le hash d'un **commit** (qui inclut métadonnées + parent, donc unique).
- Sous-estimer que `.git/` EST la base de données complète - la copier suffit à dupliquer tout l'historique, sans réseau.
- Penser que Git stocke des "diffs" entre versions : en réalité **chaque commit pointe vers un instantané complet** (via les trees/blobs), Git calcule les diffs à l'affichage, pas au stockage (avec une compression intelligente en arrière-plan pour l'efficacité).

### Auto-évaluation
- Quels sont les 4 types d'objets stockés par Git ?
- Pourquoi deux fichiers identiques (même contenu, noms différents) partagent-ils le même hash de blob ?
- Git stocke-t-il des différences (diffs) ou des instantanés complets à chaque commit ?

---

## Module 20 - Gérer un historique propre (rewriting avancé, filter-repo)

### Objectifs
- Supprimer définitivement un fichier sensible de tout l'historique
- Utiliser `git filter-repo` pour des réécritures massives
- Comprendre l'impact d'une réécriture d'historique sur un dépôt partagé

### Théorie

Parfois, une correction simple (Module 13 : ajouter au `.gitignore` et `rm --cached`) ne suffit pas : le fichier sensible (mot de passe, clé API, fichier volumineux) **existe toujours dans les anciens commits**. Il faut alors réécrire **tout l'historique** pour le faire disparaître complètement.

L'outil recommandé aujourd'hui par Git lui-même est **`git filter-repo`** (l'ancien `git filter-branch`, plus lent et plus dangereux, est officiellement déconseillé depuis plusieurs années).

 **Conséquence majeure :** réécrire l'historique change le hash de **tous les commits affectés et de tous ceux qui suivent**. Si le dépôt est déjà partagé, cela impose à **tous les collaborateurs** de re-cloner ou de se resynchroniser soigneusement. C'est une opération d'équipe à coordonner, jamais à faire seul en silence sur un dépôt partagé.

### Installation et commandes essentielles

```bash
# Installation (Python requis)
pip install git-filter-repo --break-system-packages
# ou via le gestionnaire de paquets de votre OS

# Supprimer un fichier précis de TOUT l'historique
git filter-repo --path fichier-secret.env --invert-paths

# Garder uniquement certains chemins (utile pour extraire un sous-dossier en nouveau dépôt)
git filter-repo --path dossier-a-garder/

# Remplacer un texte sensible partout dans l'historique (ex: une clé API en dur dans le code)
echo "ancienne-cle-api-secrete==>CLE_SUPPRIMEE" > remplacements.txt
git filter-repo --replace-text remplacements.txt
```

### Lab 20.1 - Supprimer définitivement un secret de l'historique

**Étape 1.** Simulez l'erreur grave : un secret committé il y a plusieurs commits, donc présent dans l'historique :
```bash
mkdir lab-filter-repo && cd lab-filter-repo
git init
echo "# Mon app" > README.md
git add . && git commit -m "Initial commit"

echo "API_KEY=sk-vraiment-secret-12345" > config.env
git add . && git commit -m "ajoute la config"

echo "feat: nouvelle fonctionnalité" > feature.txt
git add . && git commit -m "feat: nouvelle fonctionnalité"

git log --oneline
git log -p -- config.env       # le secret est bien visible dans l'historique
```

**Étape 2.** Une correction "simple" (rm --cached) ne suffit pas pour le passé :
```bash
echo "config.env" > .gitignore
git rm --cached config.env
git add .gitignore
git commit -m "fix: retire config.env du suivi"
git log -p -- config.env       # le secret est TOUJOURS visible dans les anciens commits !
```

**Étape 3.** Utilisez `filter-repo` pour l'effacer de tout l'historique :
```bash
pip install git-filter-repo --break-system-packages
git filter-repo --path config.env --invert-paths --force
```

**Étape 4.** Vérifiez que le fichier n'existe plus nulle part dans l'historique :
```bash
git log --oneline
git log -p -- config.env       # aucun résultat : le fichier n'a jamais existé dans cet historique réécrit
```

### Pièges fréquents
- **`filter-repo` ne supprime rien sur un dépôt distant** - après l'opération en local, il faut pousser en force (`git push --force --all`) ET, plus important encore, **révoquer/régénérer le secret exposé** (la clé a pu être copiée par n'importe qui entre temps : la suppression de l'historique n'efface pas une éventuelle copie déjà faite ailleurs).
- Réécrire l'historique d'un dépôt déjà cloné par d'autres **casse leur synchronisation** : ils devront re-cloner ou suivre une procédure de récupération spécifique. C'est une opération à annoncer et coordonner, jamais à faire silencieusement.
- `git filter-branch` (l'ancien outil) reste documenté dans de vieux tutoriels mais est officiellement déconseillé par le projet Git lui-même pour des raisons de performance et de pièges de sécurité ; préférez toujours `filter-repo`.

### Auto-évaluation
- Pourquoi un simple `git rm --cached` ne suffit-il pas à effacer un secret de l'historique complet ?
- Quelle action est **plus importante encore** que la réécriture d'historique, en cas de fuite de secret réelle ?
- Quel impact une réécriture d'historique a-t-elle sur les collaborateurs ayant déjà cloné le dépôt ?

---

## Module 21 - Git avancé en équipe : CODEOWNERS, branch protection, signing

### Objectifs
- Mettre en place des règles de protection de branche sur GitHub
- Configurer des relecteurs obligatoires avec CODEOWNERS
- Comprendre la signature cryptographique des commits

### Théorie

#### Branch protection rules (GitHub/GitLab)

Des règles serveur empêchant certaines actions sur des branches critiques (typiquement `main`) :
- interdire le push direct (tout doit passer par une PR),
- exiger un nombre minimum de review approuvées avant fusion,
- exiger que les tests CI passent (statut "vert") avant fusion,
- interdire le force-push et la suppression de la branche.

#### CODEOWNERS

Un fichier `.github/CODEOWNERS` (à la racine, ou dans `.github/` ou `docs/`) qui assigne automatiquement des relecteurs obligatoires selon les fichiers touchés par une PR :

```
# Format : chemin   @utilisateur-ou-équipe

*                        @lead-dev
/backend/                @equipe-backend
/frontend/                @equipe-frontend
/infra/                   @equipe-devops @lead-dev
*.sql                     @dba-team
```

#### Signature des commits (GPG/SSH)

Signer un commit prouve cryptographiquement qu'il provient bien de vous (et n'a pas été altéré), utile en environnement où l'intégrité de l'historique est critique (open source sensible, conformité réglementaire).

```bash
# Configurer une clé GPG pour signer (après avoir généré/importé une clé GPG)
git config --global user.signingkey <ID-de-votre-clé-GPG>
git config --global commit.gpgsign true

git commit -S -m "commit signé manuellement"   # signature ponctuelle si pas configuré en global

git log --show-signature -1     # vérifier la signature d'un commit
```
GitHub affiche un badge **"Verified"** sur les commits signés correctement reconnus.

### Lab 21.1 - Configurer la protection de branche sur GitHub

**Étape 1.** Sur votre dépôt `formation-git-pratique` (créé au Module 8), allez dans **Settings → Branches → Add branch protection rule**.

**Étape 2.** Configurez la règle pour `main` :
- Cochez **Require a pull request before merging**.
- Cochez **Require approvals** (mettez 1, même en solo, pour comprendre le mécanisme).
- Cochez **Do not allow bypassing the above settings**.

**Étape 3.** Testez l'effet : essayez de pousser directement sur `main` :
```bash
git checkout main
echo "test direct" >> README.md
git add . && git commit -m "test push direct"
git push
```
Le push doit être **rejeté** par GitHub avec un message expliquant la règle de protection.

**Étape 4.** Annulez ce commit local et passez par le bon chemin (branche + PR) :
```bash
git reset --hard HEAD~1
git checkout -b fix/petit-changement
echo "test via PR" >> README.md
git add . && git commit -m "test: changement via PR"
git push -u origin fix/petit-changement
```
Puis ouvrez la PR sur GitHub comme appris au Module 8.

### Lab 21.2 - Créer un fichier CODEOWNERS

**Étape 1.** Dans votre dépôt, créez la structure :
```bash
mkdir -p .github
mkdir -p backend frontend
echo "code backend" > backend/app.py
echo "code frontend" > frontend/app.js
```

**Étape 2.** Créez le fichier CODEOWNERS (remplacez par votre propre nom d'utilisateur GitHub) :
```bash
cat > .github/CODEOWNERS << 'EOF'
# Relecteur par défaut pour tout le dépôt
*                  @VOTRE-NOM-GITHUB

# Relecteurs spécifiques par dossier
/backend/          @VOTRE-NOM-GITHUB
/frontend/         @VOTRE-NOM-GITHUB
EOF
git add .
git commit -m "chore: ajoute le fichier CODEOWNERS"
git push
```

**Étape 3.** Ouvrez une PR modifiant un fichier de `backend/` et observez sur GitHub que le relecteur est automatiquement assigné dans la section "Reviewers".

### Pièges fréquents
- Activer la protection de branche **avant** d'avoir un second compte/collaborateur pour tester peut bloquer son propre travail en solo - pensez à ajouter une exception pour vous-même si besoin pédagogique, ou testez avec un compte secondaire.
- CODEOWNERS ne **bloque** rien par défaut : il faut aussi cocher, dans les règles de branche, **"Require review from Code Owners"** pour rendre la review réellement obligatoire.
- Une signature de commit prouve l'origine **du commit**, pas la qualité du code - ce n'est pas un substitut à la code review.

### Auto-évaluation
- Que permet de garantir une règle "Require a pull request before merging" ?
- Quel est le rôle exact du fichier CODEOWNERS ?
- Que signifie le badge "Verified" sur un commit GitHub ?

---

## Module 22 - Dépannage et récupération (reflog, fsck)

### Objectifs
- Retrouver des commits "perdus" après un reset --hard ou une suppression de branche
- Utiliser `git reflog` comme filet de sécurité ultime
- Diagnostiquer un dépôt avec `git fsck`

### Théorie

Le **reflog** (reference log) enregistre **chaque déplacement de HEAD et des branches locales** sur votre machine - chaque commit, checkout, reset, rebase, merge. C'est un journal local (jamais poussé, jamais partagé) qui sert de filet de sécurité quand on a "perdu" un commit qui semblait disparu.

**Point clé à comprendre :** quand vous faites un `reset --hard` ou que vous supprimez une branche, **le commit n'est pas immédiatement détruit** - il devient simplement inaccessible par les références normales (branches, tags), mais reste dans `.git/objects` jusqu'au prochain nettoyage automatique (garbage collection, généralement après ~30 jours par défaut).

### Commandes essentielles

```bash
git reflog                           # historique de TOUS les mouvements de HEAD sur cette machine
git reflog show nom-branche           # reflog spécifique à une branche

git checkout HEAD@{2}                 # revenir à l'état de HEAD il y a 2 mouvements
git reset --hard HEAD@{2}              # restaurer complètement cet état perdu

git fsck --full --unreachable          # lister les objets orphelins (potentiellement récupérables)
git fsck --lost-found                  # variante plus ancienne, place les objets trouvés dans .git/lost-found

git cherry-pick <hash-retrouvé>         # réintégrer un commit retrouvé dans la branche actuelle
```

### Lab 22.1 - Récupérer un commit après un reset --hard accidentel

**Étape 1.** Créez un historique puis "perdez" volontairement un commit :
```bash
mkdir lab-reflog && cd lab-reflog
git init
echo "v1" > app.txt
git add . && git commit -m "commit 1"
echo "v2" > app.txt
git add . && git commit -m "commit 2 - travail important"
echo "v3" > app.txt
git add . && git commit -m "commit 3"

git log --oneline
```

**Étape 2.** Simulez l'accident classique : un reset --hard trop agressif qui efface le "commit 2 important" et le "commit 3" :
```bash
git reset --hard HEAD~2
git log --oneline          # "commit 2" et "commit 3" semblent avoir disparu !
```

**Étape 3.** Paniquez... puis utilisez le reflog :
```bash
git reflog
```
Vous verrez une ligne du type :
```
a1b2c3d HEAD@{0}: reset: moving to HEAD~2
e4f5g6h HEAD@{1}: commit: commit 3
i7j8k9l HEAD@{2}: commit: commit 2 - travail important
```

**Étape 4.** Récupérez l'état perdu :
```bash
git reset --hard HEAD@{1}     # ou directement git reset --hard e4f5g6h
git log --oneline             # "commit 2" et "commit 3" sont revenus !
```

### Lab 22.2 - Récupérer une branche supprimée par erreur

**Étape 1.** Créez et "perdez" une branche :
```bash
git checkout -b branche-importante
echo "travail crucial" > crucial.txt
git add . && git commit -m "feat: travail crucial sur cette branche"
git checkout main
git branch -D branche-importante      # supprimée par erreur !
git branch                            # n'apparaît plus
```

**Étape 2.** Retrouvez son dernier commit via le reflog :
```bash
git reflog
```
Cherchez la ligne mentionnant le commit "feat: travail crucial..." (souvent visible juste avant l'entrée du checkout vers main).

**Étape 3.** Recréez la branche à partir de ce commit :
```bash
git branch branche-importante-recuperee <hash-trouvé>
git checkout branche-importante-recuperee
cat crucial.txt          # le fichier est de retour !
```

### Pièges fréquents
- Le reflog est **local à votre machine** : il ne se clone pas, ne se pousse pas, et est inutile pour récupérer le travail d'un collègue sur sa propre machine.
- Le reflog a une durée de rétention par défaut (souvent 90 jours pour les entrées atteignables, 30 jours pour les inatteignables) - ce n'est pas un filet de sécurité éternel ; il ne remplace jamais une vraie discipline de commit/push réguliers.
- Ne paniquez jamais immédiatement après un reset hasardeux : dans l'immense majorité des cas, le reflog permet une récupération complète tant qu'aucune autre opération Git majeure n'a eu lieu depuis.

### Auto-évaluation
- Pourquoi un commit "supprimé" par un `reset --hard` n'est-il généralement pas perdu immédiatement ?
- Le reflog est-il partagé entre collaborateurs via le dépôt distant ?
- Quelle commande permet de visualiser tous les mouvements récents de HEAD ?

---

## Module 23 - Bonnes pratiques et conventions professionnelles

### Objectifs
- Synthétiser les bonnes pratiques vues dans tout le cours
- Adopter des conventions professionnelles reconnues
- Savoir structurer un workflow Git pour une équipe réelle

### Théorie et synthèse

#### Messages de commit

- Utilisez un format cohérent dans toute l'équipe - **Conventional Commits** (`feat:`, `fix:`, `docs:`, `refactor:`, `test:`, `chore:`) est devenu un standard de facto, notamment car il permet de générer automatiquement des changelogs.
- Ligne de résumé courte (50 caractères), à l'impératif ("ajoute" plutôt que "ajouté" ou "ajoute des trucs").
- Le corps du message explique le **pourquoi**, pas le quoi (le diff montre déjà le quoi).

#### Taille et fréquence des commits

- Privilégiez des **commits atomiques** : chaque commit représente un seul changement logique cohérent, qui pourrait théoriquement être reverté seul sans casser autre chose.
- Committez fréquemment en local (votre propre historique de travail), puis nettoyez avant de partager (rebase interactif, Module 14) si la convention d'équipe le permet.

#### Branches

- Nommage cohérent : `feature/nom-court`, `fix/nom-du-bug`, `hotfix/urgence`, `release/1.2.0`, `chore/nom-de-la-tache`.
- Branches courtes (quelques jours maximum) pour limiter les divergences et conflits - synchronisez régulièrement avec `main` pendant le développement.
- Supprimez les branches après fusion (la plupart des plateformes le proposent automatiquement).

#### Pull Requests

- PR de taille raisonnable (quelques centaines de lignes maximum si possible) - une PR de 5000 lignes ne sera jamais relue sérieusement.
- Description claire : quoi, pourquoi, comment tester. Liez les Issues concernées (`Closes #42`).
- Demandez une review même seul sur un petit projet : c'est un excellent réflexe à construire pour le travail en équipe future.

#### Sécurité

- Jamais de secret en dur dans le code, même temporairement "pour tester" - utilisez des variables d'environnement et `.gitignore` dès le premier commit d'un projet.
- Vérifiez systématiquement `git status` et `git diff --staged` avant chaque commit.
- En cas de fuite de secret : révoquez/régénérez immédiatement, **puis** envisagez la réécriture d'historique (Module 20).

#### Workflow d'équipe

- Choisissez un workflow adapté à votre contexte (Module 9) et **documentez-le** dans un fichier `CONTRIBUTING.md` à la racine du dépôt.
- Mettez en place des règles de protection de branche dès que plusieurs personnes travaillent sur le même dépôt (Module 21).
- Automatisez ce qui peut l'être : hooks (Module 18), CI/CD (tests automatiques sur chaque PR).

### Lab 23.1 - Rédiger un CONTRIBUTING.md professionnel

**Étape 1.** Dans votre dépôt `formation-git-pratique`, créez un guide de contribution :
```bash
cat > CONTRIBUTING.md << 'EOF'
# Guide de contribution

## Workflow

Ce projet suit le **GitHub Flow** :
1. Créez une branche depuis `main` : `feature/nom-court` ou `fix/nom-du-bug`
2. Committez avec des messages au format Conventional Commits
3. Ouvrez une Pull Request dès que possible (même en brouillon avec "Draft PR")
4. Demandez une review avant fusion
5. Utilisez "Squash and merge" pour garder un historique `main` propre

## Convention de commits

- `feat:` nouvelle fonctionnalité
- `fix:` correction de bug
- `docs:` documentation uniquement
- `refactor:` changement de code sans nouvelle fonctionnalité ni correction
- `test:` ajout/modification de tests
- `chore:` tâches diverses (dépendances, configuration...)

## Avant d'ouvrir une PR

- [ ] Le code a été testé localement
- [ ] Les messages de commit respectent la convention
- [ ] La branche est à jour avec `main`
- [ ] Aucun secret n'est présent dans le diff
EOF
git add CONTRIBUTING.md
git commit -m "docs: ajoute le guide de contribution"
git push
```

### Défi de synthèse final

Pour valider l'ensemble du cours, reportez-vous à l'**Annexe B - Projet final récapitulatif**, qui combine la quasi-totalité des notions vues dans les 23 modules au sein d'un unique scénario réaliste de bout en bout.

---

## Annexe A - Aide-mémoire (Cheat Sheet) complet

### Configuration
```bash
git config --global user.name "Nom"
git config --global user.email "email"
git config --list
```

### Démarrage
```bash
git init                              # nouveau dépôt
git clone <url>                        # copier un dépôt distant
```

### Cycle de base
```bash
git status                            # état actuel
git add <fichier>                      # stager un fichier
git add .                             # stager tout
git add -p                            # stager interactivement
git commit -m "message"                # committer
git commit --amend                     # modifier le dernier commit
```

### Historique
```bash
git log --oneline --graph --all        # vue compacte et graphique
git diff                              # diff non stagé
git diff --staged                      # diff stagé
git show <hash>                        # détails d'un commit
```

### Branches
```bash
git branch                            # lister
git switch -c nom-branche               # créer + basculer
git switch nom-branche                  # basculer
git branch -d nom-branche               # supprimer (sûr)
git merge nom-branche                   # fusionner
```

### Distant
```bash
git remote -v                         # lister les distants
git fetch origin                       # récupérer sans fusionner
git pull                              # récupérer + fusionner
git push -u origin nom-branche          # pousser + lier
```

### Annuler
```bash
git restore <fichier>                  # annuler modif non stagée
git restore --staged <fichier>          # désindexer
git reset --soft HEAD~1                 # annuler commit, garder stagé
git reset --hard HEAD~1                 # annuler commit, tout perdre
git revert <hash>                       # annuler via nouveau commit (sûr si partagé)
```

### Stash
```bash
git stash save "message"
git stash list
git stash pop
```

### Tags
```bash
git tag -a v1.0.0 -m "message"
git push origin --tags
```

### Avancé
```bash
git rebase -i HEAD~5                    # rebase interactif
git cherry-pick <hash>                   # appliquer un commit précis
git bisect start                         # recherche dichotomique de bug
git reflog                              # filet de sécurité ultime
```

---

## Annexe B - Projet final récapitulatif

### Objectif

Mettre en pratique l'intégralité du cours sur un scénario réaliste : la création et la vie d'un petit projet web en équipe simulée, du premier commit jusqu'à une version taguée en production, en passant par des branches, des conflits, une PR, et une erreur corrigée.

### Scénario

Vous développez un site vitrine pour une boulangerie. Vous travaillerez seul mais en simulant un contexte d'équipe (deux clones locaux représentant deux développeurs).

### Étape 1 - Initialisation (Modules 0-2)
```bash
mkdir -p ~/git-formation/boulangerie-finale && cd ~/git-formation/boulangerie-finale
git init
echo "# Boulangerie Dupont" > README.md
echo "node_modules/
.env
*.log" > .gitignore
git add . && git commit -m "chore: initialise le projet"
```

### Étape 2 - Création d'un dépôt distant et premier push (Modules 7-8)
Créez un dépôt sur GitHub nommé `boulangerie-finale`, puis :
```bash
git remote add origin https://github.com/VOTRE-NOM/boulangerie-finale.git
git branch -M main
git push -u origin main
```

### Étape 3 - Développement en branches (Modules 4, 9)
```bash
git checkout -b feature/page-produits
echo "<h1>Nos Pains</h1>" > produits.html
git add . && git commit -m "feat: ajoute la page produits"
git push -u origin feature/page-produits
```
Ouvrez une PR sur GitHub, fusionnez-la (Squash and merge), puis nettoyez localement.

### Étape 4 - Conflit volontaire (Module 5)
```bash
git checkout main && git pull
git checkout -b feature/horaires
echo "Lundi-Vendredi: 7h-19h" > horaires.txt
git add . && git commit -m "feat: ajoute les horaires"

git checkout main
echo "Tous les jours: 7h-20h" > horaires.txt
git add . && git commit -m "fix: corrige les horaires d'ouverture"

git merge feature/horaires
# résolvez le conflit manuellement, puis :
git add horaires.txt
git commit
```

### Étape 5 - Erreur et correction (Modules 10, 13)
```bash
echo "API_KEY=secret-boulangerie-123" > config.env
git add . && git commit -m "oops: ajoute la config (erreur)"
# Correction immédiate :
echo "config.env" >> .gitignore
git rm --cached config.env
git add .gitignore
git commit -m "fix: retire config.env du suivi"
```

### Étape 6 - Nettoyage d'historique avant publication (Module 14)
```bash
git log --oneline
git rebase -i HEAD~2    # fusionnez le "oops" et son "fix" en un seul commit propre via fixup
```

### Étape 7 - Mise en stash d'un travail interrompu (Module 11)
```bash
echo "travail en cours sur la newsletter..." > newsletter.html
git stash save "WIP: newsletter pas terminée"
echo "fix: correction urgente du logo" > logo-fix.txt
git add . && git commit -m "fix: corrige l'affichage du logo"
git push
git stash pop
```

### Étape 8 - Versionner la release (Module 12)
```bash
git add . && git commit -m "feat: termine la newsletter"
git push
git tag -a v1.0.0 -m "Première version du site en production"
git push origin --tags
```

### Étape 9 - Hotfix isolé via cherry-pick (Module 15)
```bash
git checkout -b dev
echo "fix: corrige une faille XSS" > securite.txt
git add . && git commit -m "fix: corrige une faille de sécurité critique"
echo "feat: fonctionnalité non finie" > en-cours.txt
git add . && git commit -m "feat: fonctionnalité non terminée"

git checkout main
git cherry-pick <hash-du-commit-securite>
git tag -a v1.0.1 -m "Correctif de sécurité critique"
git push origin --tags
```

### Étape 10 - Récupération après erreur (Module 22)
```bash
git reset --hard HEAD~1     # erreur simulée
git reflog                  # retrouvez le commit perdu
git reset --hard HEAD@{1}   # récupérez-le
```

### Validation finale

Vous avez, dans ce projet unique : initialisé un dépôt, géré le cycle add/commit, travaillé avec des branches, résolu un conflit, corrigé une erreur de sécurité, nettoyé un historique, utilisé le stash, taggé des versions, appliqué un cherry-pick, et récupéré un commit perdu. C'est l'essentiel du quotidien professionnel avec Git.

---

## Annexe C - Glossaire

| Terme | Définition |
|---|---|
| **Repository (dépôt)** | l'ensemble versionné d'un projet, stocké dans le dossier `.git` |
| **Working Directory** | les fichiers tels qu'ils existent sur le disque, modifiables librement |
| **Staging Area / Index** | zone tampon où l'on prépare le contenu du prochain commit |
| **Commit** | un instantané enregistré de façon permanente dans l'historique |
| **Branch (branche)** | un pointeur mobile vers un commit |
| **HEAD** | pointeur vers le commit/la branche actuellement active |
| **Remote (distant)** | une copie du dépôt hébergée ailleurs (serveur, GitHub...) |
| **Origin** | nom conventionnel donné au dépôt distant principal |
| **Clone** | copie complète d'un dépôt distant en local |
| **Fork** | copie d'un dépôt sous votre propre compte sur une plateforme |
| **Merge** | fusion de deux branches, pouvant créer un commit à deux parents |
| **Rebase** | rejeu de commits sur une nouvelle base, réécrivant leur hash |
| **Conflict (conflit)** | situation où Git ne peut pas fusionner automatiquement deux versions |
| **Pull Request / Merge Request** | proposition d'intégrer une branche dans une autre, avec discussion |
| **Tag** | pointeur immuable, généralement utilisé pour marquer une version |
| **Stash** | mise de côté temporaire de modifications non commitées |
| **Cherry-pick** | application d'un commit précis sur une autre branche |
| **Bisect** | recherche dichotomique du commit ayant introduit un bug |
| **Hook** | script exécuté automatiquement à un moment du cycle de vie Git |
| **Submodule** | référence vers un commit précis d'un autre dépôt Git |
| **Blob** | objet Git stockant le contenu brut d'un fichier |
| **Tree** | objet Git représentant une structure de dossier |
| **Reflog** | journal local de tous les mouvements de HEAD, filet de sécurité |
| **Detached HEAD** | état où HEAD pointe directement sur un commit, sans branche associée |
| **Fast-forward** | type de fusion où la branche cible avance simplement sans nouveau commit |
| **Squash** | fusion de plusieurs commits en un seul |
| **Force push** | envoi forcé qui peut écraser l'historique distant - dangereux en équipe |
| **SemVer** | convention de version `MAJOR.MINOR.PATCH` |

---

## Annexe D - Ressources complémentaires

### Documentation officielle
- [git-scm.com/doc](https://git-scm.com/doc) - documentation officielle complète
- [Pro Git Book](https://git-scm.com/book/fr/v2) - le livre de référence, disponible gratuitement en français

### Pratique interactive
- [Learn Git Branching](https://learngitbranching.js.org/) - visualisation interactive des branches, merges et rebases
- [GitHub Skills](https://skills.github.com/) - parcours guidés officiels GitHub

### Plateformes
- [GitHub](https://github.com) - la plus utilisée mondialement
- [GitLab](https://gitlab.com) - alternative très utilisée en entreprise, avec CI/CD intégrée
- [Bitbucket](https://bitbucket.org) - alternative orientée Atlassian (Jira, Confluence)

### Outils complémentaires
- **GitHub CLI (`gh`)** - gérer GitHub depuis le terminal
- **Husky** - gérer les hooks Git partagés en équipe sur des projets Node.js
- **git-filter-repo** - réécriture avancée d'historique (Module 20)
- **GitKraken / Sourcetree / GitHub Desktop** - interfaces graphiques pour visualiser et manipuler Git

### Pour aller plus loin
- [Conventional Commits](https://www.conventionalcommits.org/) - spécification complète
- [Semantic Versioning](https://semver.org/) - spécification complète du SemVer

---

## Conclusion

Ce cours a couvert l'intégralité du spectre Git : des tout premiers concepts (zones de travail, commits) jusqu'aux mécanismes internes (objets, plumbing), en passant par la collaboration moderne (PR, workflows d'équipe), les techniques de récupération (reflog, bisect), et les bonnes pratiques professionnelles.

La maîtrise de Git ne vient jamais de la seule lecture, mais de la pratique répétée : refaites les labs, cassez volontairement des choses dans un dépôt de test, et utilisez le reflog comme filet de sécurité pour explorer sans crainte. Bon courage, et bon code !
