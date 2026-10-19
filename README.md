# Suivi Santé

Application de suivi d'analyses biochimiques avec graphiques. Une valeur qui dépasse sa limite de plus de 20 % passe en rouge (seuil réglable).

Créée par Kamel Nasralli. Version 1.5.7 (19 octobre 2026).

## Fichiers à déposer

Déposez ces cinq fichiers à la racine du dépôt :

- `index.html` : l'application
- `manifest.json` : nom et icône de l'application installée
- `sw.js` : permet d'ouvrir l'application sans connexion
- `icon-192.png` et `icon-512.png` : l'icône

## Publier sur GitHub Pages

1. Sur github.com, cliquez sur **New repository**. Donnez-lui un nom, par exemple `suivi-sante`.
2. Cliquez sur **uploading an existing file**, sélectionnez les cinq fichiers, puis **Commit changes**.
3. Ouvrez **Settings**, puis **Pages**.
4. Sous **Build and deployment**, choisissez **Deploy from a branch**, la branche `main` et le dossier `/ (root)`, puis **Save**.
5. Attendez une minute. L'adresse apparaît en haut de la page Pages : `https://VOTRE-NOM.github.io/suivi-sante/`.

## Mettre l'icône sur l'écran d'accueil

Ouvrez l'adresse GitHub Pages (pas le lien claude.ai), puis :

- **Android (Chrome)** : menu ⋮, puis **Installer l'application** ou **Ajouter à l'écran d'accueil**.
- **iPhone et iPad (Safari)** : bouton Partager, puis **Sur l'écran d'accueil**.

L'application s'ouvre ensuite en plein écran, comme une application, et fonctionne aussi sans connexion.

## Plusieurs personnes

En haut de la page, la liste « Qui utilise l'application ? » permet de choisir une personne, d'en ajouter, de la renommer ou de la supprimer. Chaque personne a ses propres mesures et son propre seuil d'alerte.

- Le premier profil, « Moi » par défaut (vous pouvez le renommer), contient les analyses de votre fichier. Il ne peut pas être supprimé.
- Les autres profils démarrent vides. On y ajoute des mesures à la main ou avec l'onglet **Import / Export**.
- Les profils ne sont pas protégés par un mot de passe : toute personne qui utilise le même navigateur peut ouvrir tous les profils.
- Les données restent dans le navigateur de l'appareil utilisé. Si chaque personne ouvre l'application sur son propre téléphone, chacune a sa propre liste, et rien n'est partagé entre les appareils. Pour transférer un profil, exportez-le en JSON ou en CSV, puis importez-le sur l'autre appareil.

## Ajouter une analyse absente de la liste

Dans le formulaire « Ajouter une mesure », cliquez sur **+ Analyse absente de la liste ? Ajoutez-la**. Indiquez le nom, l'unité et au moins une limite (basse, haute, ou les deux), telles qu'elles figurent sur votre bilan. Les limites sont celles de votre laboratoire.

- La nouvelle analyse a son graphique et son alerte rouge, comme les autres. Le seuil de 20 % s'applique de la même façon.
- Elle appartient à la personne choisie. Les autres profils ne la voient pas.
- Pour la corriger ou la supprimer, ouvrez-la dans la liste : les boutons **Modifier l'analyse** et **Supprimer l'analyse** apparaissent sous son titre. La suppression efface aussi ses mesures.
- La sauvegarde JSON contient la définition de ces analyses. En important ce fichier sur un autre appareil, elles sont recréées automatiquement. Un fichier CSV ne contient pas les limites : créez d'abord l'analyse, puis importez.

## Numéro de version

La version s'affiche sous le titre et en bas de page, avec l'historique des versions. Elle est aussi écrite dans les sauvegardes JSON.

## Confidentialité

`index.html` contient vos résultats d'analyses. Avec un compte GitHub gratuit, un site GitHub Pages est public : toute personne qui connaît l'adresse peut les voir.

- Pour un usage privé, utilisez un dépôt privé avec une offre GitHub qui autorise Pages sur les dépôts privés (Pro, Team ou Enterprise).
- Les mesures ajoutées avec le formulaire restent dans le navigateur de la personne qui les saisit. Elles ne sont pas envoyées à GitHub.

## Sauvegarde

Les mesures ajoutées sont enregistrées dans le navigateur (localStorage). Utilisez l'onglet **Import / Export** pour les sauvegarder en CSV ou JSON avant de vider les données du navigateur ou de changer d'appareil.

## Scanner une analyse (appareil photo)

Dans « Ajouter une mesure », le bouton **Scanner une analyse** ouvre l'appareil photo ; **Choisir une photo** prend une image de la galerie.
L'application lit le texte sur votre appareil (la photo n'est pas envoyée), reconnaît les analyses (glycémie, HbA1c, cholestérol, LDL, HDL, triglycérides, créatinine, acide urique et vos analyses ajoutées) et la date du prélèvement, puis affiche un écran de contrôle. Vérifiez chaque valeur, corrigez si besoin, puis touchez **Enregistrer**.

- Il faut une connexion internet la première fois : le moteur de lecture (environ 10 Mo) se télécharge, puis il est gardé par le navigateur.
- Pour une meilleure lecture : photo bien droite, nette, bien éclairée, sans reflet.
- La photo est lue par bandes (plus précis) ; cela peut prendre une à deux minutes sur un téléphone. Seule la ligne du résultat actuel est lue ; les lignes « Dernier résultat » sont ignorées.

Note : dans l'application Claude (page publiée sur claude.ai), la photo est lue par Claude, sur votre compte, avec votre autorisation. Sur GitHub Pages, la lecture se fait uniquement sur votre appareil. Un bouton « Arrêter la lecture » et des délais maximum évitent tout blocage ; en cas d'échec, vous saisissez les valeurs à la main.

## Langues
La version 1.5.7 ajoute un sélecteur Français / العربية / Deutsch. La langue est mémorisée sur l'appareil ; l'arabe active l'orientation droite-à-gauche. Certaines notifications générées dynamiquement peuvent encore apparaître en français.
