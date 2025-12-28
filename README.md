# Memo
Mémos personnels – Git, Linux, Test logiciel, Data &amp; IA
# 📘 Mémo personnel – John NG

Ce dépôt est mon **carnet de mémoire technique**.  
Il contient **tout ce que j’ai fait et appris**, étape par étape, pour pouvoir :
- recommencer sur un nouvel ordinateur
- travailler en formation (Test Logiciel, Data, IA)
- ne pas paniquer quand j’oublie

👉 **Je n’ai pas besoin de tout retenir : tout est écrit ici.**

---

## 🧠 Comprendre l’essentiel (avant les commandes)

- GitHub = un service **en ligne**
- Mon ordinateur = environnement **local**
- Git = l’outil qui permet de travailler et synchroniser
- SSH = l’autorisation sécurisée entre mon PC et GitHub
- Cloner = copier un dépôt GitHub sur mon PC pour travailler

---

# 🔹 ÉTAPE 1 — Vérifier si Git est installé
Dans le terminal :

```bash
git --version

Résultat possible :
.git version X.X.X → Git est déjà installé
.command not found → Git n’est PAS installé

⚠️ Attention :
. # au début d’une ligne = commentaire (la commande ne s’exécute pas)
. ~sudo est une erreur → il faut écrire sudo

# 🔹 ÉTAPE 2 — Installer Git (si absent)
sudo apt update
sudo apt install git

Vérifier :
git --version

# 🔹 ÉTAPE 3 — Configuration Git (UNE SEULE FOIS PAR MACHINE)
Ces informations identifient l’auteur des commits.

git config --global user.name "John NG"
git config --global user.email "johnmarereng06@gmail.com"

Définir main comme branche par défaut :
git config --global init.defaultBranch main

Améliorer l’affichage :
git config --global color.ui auto

Vérifier toute la configuration :
git config --global --list

# 🔹 ÉTAPE 4 — Tester Git localement (premier dépôt)
mkdir test-git
cd test-git
git init

Renommer la branche si besoin :
git branch -m main

Créer un fichier test :
touch README.md
git status

# 🔹 ÉTAPE 5 — Comprendre GitHub vs local
GitHub = dépôt distant (en ligne)
Mon PC = dépôt local

Pour travailler, j’ai besoin d’une copie locale
➡️ Cette copie s’obtient avec git clone

# 🔹 ÉTAPE 6 — Créer une clé SSH (nouvel ordinateur)
Vérifier si une clé existe :
ls ~/.ssh

Si le dossier n’existe pas → créer une clé :
ssh-keygen -t ed25519 -C "johnmarereng06@gmail.com"
➡️ Appuyer sur Entrée à toutes les questions

Vérifier :
ls ~/.ssh

Résultat attendu :
id_ed25519
id_ed25519.pub

Afficher la clé publique :
cat ~/.ssh/id_ed25519.pub

➡️ Copier la clé et l’ajouter sur GitHub :
https://github.com/settings/keys

# 🔹 ÉTAPE 7 — Tester la connexion PC ↔ GitHub
ssh -T git@github.com

Premier message possible :
Are you sure you want to continue connecting (yes/no)?
➡️ Taper yes

Résultat attendu :
Hi jng06600! You've successfully authenticated, but GitHub does not provide shell access.

# 🔹 ÉTAPE 8 — Cloner un dépôt GitHub sur mon PC
Exemple :
cd ~
git clone git@github.com:jng06600/Memo.git
cd Memo
ls

1️⃣ Ouvre le fichier
nano README.md

2️⃣ Supprime tout le contenu
Colle le README complet que je t’ai donné dans le message précédent

3️⃣ Enregistre
Ctrl + O
Entrée
Ctrl + X

🚀 DERNIÈRE ÉTAPE — Sauvegarder sur GitHub
Toujours dans ~/Memo :

git status
git add README.md
git commit -m "README complet : installation Git, configuration et liaison GitHub"
git push

💤 Après ça : STOP

J'ai installé Git
compris local vs distant
sécurisé ton PC avec SSH
créé un repo perso
documenté tout mon apprentissage
