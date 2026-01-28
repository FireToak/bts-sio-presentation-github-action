# Procédure - Initiation à GitHub Pages

[Dépôt git ressources](https://github.com/FireToak/bts-sio-presentation-github-action)

![Logo GitHub Pages](https://github.com/FireToak/bts-sio-presentation-github-action/images/logo_github-pages.png)

---
## Informations générales

- **Date de création :** 28/01/2026
- **Dernière modification :** 28/01/2026
- **Auteur :** MEDO Louis

---
## Sommaire

- A. Présentation de GitHub Pages
- B. Mise en place de GitHub Pages pour vos projets

---
## A. Présentation de GitHub Pages

GitHub Pages est un service d'hébergement de sites web statiques proposé par GitHub (racheté par Microsoft en 2018). Lancé initialement en 2008, ce service permet de publier des pages web directement depuis un dépôt Git. Il est conçu pour héberger des pages personnelles, des documentations de projets ou des portfolios sans avoir besoin de gérer une infrastructure serveur complexe.

### 1. La problématique résolue

Pour un développeur ou un étudiant en informatique, la mise en ligne d'un site web implique traditionnellement plusieurs barrières techniques et financières :
* **Coût :** Nécessité de louer un nom de domaine et un hébergement (VPS ou mutualisé).
* **Complexité d'administration :** Configuration d'un serveur web (Nginx, Apache), gestion des certificats SSL (HTTPS), et maintenance de l'OS.
* **Flux de travail lourd :** Utilisation de protocoles anciens comme FTP pour transférer les fichiers manuellement à chaque modification.

**Solution :** GitHub Pages automatise ce processus. Il transforme le code déjà présent sur votre dépôt en un site consultable mondialement, gratuitement, et sécurisé (HTTPS par défaut).

### 2. Fonctionnement

GitHub Pages va utiliser les éléments WEB de votre dépôt pour en générer un site internet.
1.  **Source :** Le service lit les fichiers (HTML, CSS, JS) situés dans une branche spécifique (souvent `main`).
2.  **Build (Construction) :**
    * Si le dépôt contient du HTML standard, il est servi tel quel.
    * Si le dépôt contient du Markdown, GitHub utilise **Jekyll** (un générateur de site statique) pour transformer le texte en HTML.
3.  **Déploiement :** Le contenu est rendu accessible via une URL structurée ainsi : `https://<nom-utilisateur>.github.io/<nom-du-projet>`.

### 3. Point de vigilance

* **Sites statiques uniquement :** GitHub Pages ne supporte pas les langages côté serveur comme PHP, Python (Django/Flask) ou les bases de données (MySQL, PostgreSQL). Si votre projet nécessite une base de données ou un traitement backend, GitHub Pages ne suffira pas.

* **Visibilité du code :** Pour bénéficier de la gratuité totale, le dépôt doit souvent être **Public** (sauf avec l'abonnement Pro). Tout ce que vous publiez (y compris les clés API ou mots de passe oubliés dans le code) est visible par tout le monde.

* **Mise en cache :** Les modifications peuvent prendre quelques minutes à apparaître en ligne à cause du délai de propagation et de mise en cache.

---
## B. Mise en place de GitHub Pages pour vos projets

> Dans cette partie, nous allons créer un dépôt simple contenant une page d'accueil et activer le service d'hébergement pour la rendre accessible sur le web.

### Prérequis

- Un compte GitHub actif.

### 1. Création d'un dépôt

**1.1 Création du nouveau projet.**
Depuis votre tableau de bord GitHub, cliquez sur le bouton `+` en haut à droite, puis sélectionnez **New repository**.

**1.2 Configuration du dépôt.**
Remplissez les champs suivants :
* **Repository name :** `mon-site-web` (ou tout autre nom sans espaces).
* **Visibility :** Sélectionnez **Public**.
* **Initialize this repository with :** Cochez **Add a README file** (cela crée automatiquement la branche `main`).
* Cliquez sur **Create repository**.

**1.3 Ajout d'une page d'index.**
Une fois dans le dépôt :
1.  Cliquez sur le bouton **Add file** > **Create new file**.
2.  Nommez le fichier `index.html`.
3.  Collez le code suivant pour tester :
    ```html
    <!DOCTYPE html>
    <html>
    <body>
        <h1>Mon premier site GitHub Pages</h1>
        <p>Hébergé gratuitement !</p>
    </body>
    </html>
    ```
4.  Cliquez sur **Commit changes** (bouton vert en haut à droite) puis confirmez avec **Commit changes**.

### 2. Activation de GitHub Pages sur le dépôt

**2.1 Accès aux paramètres.**
Dans votre dépôt, cliquez sur l'onglet **Settings** (icône d'engrenage) situé dans la barre de navigation du haut.

**2.2 Configuration de la source.**
Dans le menu latéral gauche, descendez jusqu'à la section "Code and automation" et cliquez sur **Pages**.

**2.3 Déploiement de la branche.**
Dans la section **Build and deployment** :
1.  Sous **Source**, assurez-vous que `Deploy from a branch` est sélectionné.
2.  Sous **Branch**, cliquez sur le menu déroulant (souvent marqué "None") et sélectionnez `main`.
3.  Laissez le dossier sur `/ (root)`.
4.  Cliquez sur **Save**.

![Capture d'écran de la configuration de la branche source](/path/to/pages-branch-select.png)

**2.4 Vérification.**
Après avoir cliqué sur Save, attendez environ 1 à 2 minutes. Rafraîchissez la page des paramètres. Un bandeau en haut de la page apparaîtra avec le message :
> "Your site is live at `https://[votre-pseudo].github.io/mon-site-web/`"

Cliquez sur le lien pour vérifier que votre fichier `index.html` s'affiche correctement.

---
## Notes

* **HTTPS :** GitHub force automatiquement le HTTPS, assurant une connexion sécurisée sans configuration supplémentaire.
* **Nom de domaine personnalisé :** Il est possible de relier votre propre nom de domaine (ex: `www.mon-nom.com`) dans la section "Custom domain" des paramètres Pages.