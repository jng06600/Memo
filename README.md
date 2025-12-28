# 📘 Mémo Git & GitHub — Comprendre ce que je fais (pas juste exécuter)

Ce document explique **pas à pas** les commandes Git que j’utilise,
avec **le rôle de chaque ligne**, pour comprendre même quand je suis fatigué.

---

## 🧠 Les concepts essentiels (avant les commandes)

- **Working directory** : le dossier de mon projet sur mon ordinateur
- **Stage / index** : zone intermédiaire où je prépare ce qui va être sauvegardé
- **Repository local** : l’historique des versions sur mon PC
- **Repository distant (GitHub)** : l’historique en ligne
- **Commit** : une sauvegarde/version de mon projet
- **Push** : envoyer mes commits vers GitHub

---

## 🔹 Vérifier si Git est installé

git --version
👉 Demande à l’ordinateur :

“Est-ce que Git est installé, et quelle version ?”

Si une version s’affiche → Git est installé

Si command not found → Git n’est pas installé

🔹 Installer Git (si nécessaire)

sudo apt update
👉 Met à jour la liste des logiciels disponibles sur Linux.

sudo apt install git
👉 Installe Git sur l’ordinateur.

🔹 Configurer Git (UNE SEULE FOIS PAR MACHINE)

git config --global user.name "Prenom Nom"
👉 Indique à Git qui est l’auteur des commits.

git config --global user.email "mon-mail@gmail.com"
👉 Associe un email à chaque commit (identité, pas un mot de passe).

git config --global init.defaultBranch main
👉 Définit main comme branche par défaut pour tous les nouveaux projets.

git config --global color.ui auto
👉 Active les couleurs pour mieux lire les messages Git.

git config --global --list
👉 Affiche toute la configuration Git actuelle.

🔹 Créer un nouveau projet Git
mkdir PremierProjet
👉 Crée un dossier de projet.

cd PremierProjet
👉 Entre dans le dossier du projet.

git init
👉 Initialise un dépôt Git dans ce dossier
(crée le dossier caché .git).

🔹 Vérifier l’état du projet
git status
👉 Montre :

quels fichiers sont modifiés

lesquels sont prêts à être sauvegardés

s’il y a des erreurs

➡️ Commande réflexe à utiliser souvent.

🔹 Ajouter des fichiers au stage (index)

git add index.html styles.css
👉 Dit à Git :

“Je veux inclure ces fichiers dans la prochaine sauvegarde.”

Les fichiers passent du working directory → stage.

🔹 Créer une version (commit)

git commit -m "Ajout des fichiers HTML et CSS de base"
👉 Crée une version officielle du projet avec un message explicatif.

-m = message

Le message doit expliquer ce qui a changé

🔹 Créer une clé SSH (connexion sécurisée à GitHub)

ssh-keygen -t ed25519 -C "mon-mail@gmail.com"
👉 Crée une paire de clés :

clé privée (reste sur mon PC)

clé publique (à donner à GitHub)

➡️ Appuyer sur Entrée à toutes les questions.

ls ~/.ssh
👉 Vérifie que les clés existent.

cat ~/.ssh/id_ed25519.pub
👉 Affiche la clé publique à copier sur GitHub.

🔹 Tester la connexion avec GitHub

ssh -T git@github.com
👉 Vérifie que mon PC est reconnu par GitHub.

Résultat attendu :

“You’ve successfully authenticated…”

🔹 Relier le projet local à GitHub

git remote add origin git@github.com:USERNAME/NOM_DU_REPO.git
👉 Dit à Git :

“Le dépôt distant (GitHub) s’appelle origin et voici son adresse.”

⚠️ Cette commande se fait une seule fois.

git remote -v
👉 Vérifie l’adresse du dépôt distant.

🔹 Corriger l’adresse du dépôt distant (si erreur)

git remote set-url origin git@github.com:USERNAME/NOM_DU_REPO.git
👉 Remplace l’ancienne adresse par la bonne
(ex : erreur de majuscules dans le nom du repo).

🔹 Envoyer le projet sur GitHub (push)

git push -u origin main
👉 Envoie les commits locaux vers GitHub.

origin = dépôt distant

main = branche

-u = mémorise la destination pour les prochains push

Ensuite, il suffira de faire :

git push
🔁 Le cycle Git à retenir (le plus important)

git status
git add .
git commit -m "message clair"
git push
👉 Toujours dans cet ordre.

🧯 Erreur fréquente : terminal bloqué avec >
Si le terminal affiche > :

la commande n’est pas terminée

souvent à cause de guillemets ou caractères spéciaux

👉 Solution immédiate :
Ctrl + C
🧠 Ce que je sais faire maintenant
Créer un projet Git

Sauvegarder mon travail avec des commits

Relier un projet à GitHub

Corriger une erreur de dépôt distant

Comprendre ce que je fais, pas juste copier-coller
