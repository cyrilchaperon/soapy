# Soapy — atelier provençal

Application statique en HTML, CSS et JavaScript, issue de la V8. Le site fonctionne sans compte serveur : recettes, progression, préférences et étapes sont stockées dans le navigateur de l’appareil.

## Lancer en local

Depuis ce dossier, servir les fichiers avec un serveur HTTP statique (par exemple `python3 -m http.server 8080`) puis ouvrir `http://localhost:8080`.

## Publier avec GitHub et Cloudflare Pages

- Dépôt GitHub : pousser le contenu de ce dossier sur la branche `main`.
- Cloudflare Pages : connecter le dépôt GitHub, choisir `main` comme branche de production, laisser la commande de build vide et définir `/` comme répertoire de sortie.
- Aucun secret, service de build ni variable d’environnement n’est nécessaire pour la version statique.

## Modifier Soapy directement sur GitHub

Le site est maintenant organisé en fichiers séparés, sans étape de compilation :

- `index.html` : structure des pages, sections, libellés et navigation ;
- `styles.css` : couleurs, cadres, tailles, disposition et adaptation mobile ;
- `app.js` : calculateur, recettes, badges, mascottes et interactions ;
- `assets/` : images et décors.

Pour faire une modification en ligne, ouvre le fichier concerné dans le dépôt GitHub, clique sur le crayon **Edit this file**, effectue tes changements puis clique sur **Commit changes**. Cloudflare Pages redéploie automatiquement le site après l’enregistrement sur `main`. Il n’y a pas de commande de build à régler.

Cette organisation te permet de modifier le code depuis GitHub, mais ne crée pas encore un éditeur visuel avec blocs comme WordPress. Pour modifier le contenu sans toucher au code, il faudra ensuite connecter un CMS à GitHub.

## Calculateur

Les SAP NaOH du catalogue sont des valeurs de référence arrondies à 0,001 g/g, alignées sur la table publique de SoapCalc (https://soapcalc.net/oil-list). Les lots et fournisseurs peuvent différer : remplacer ces valeurs par les données du fournisseur est préférable. La soude à peser corrige la masse active selon la pureté saisie. L’eau est calculée sur la masse de NaOH actif : `eau = NaOH actif × (100 / concentration − 1)`. Le surgraissage réduit la quantité théorique de NaOH actif.

Ce calculateur n’est pas une validation de sécurité. Il ne remplace ni le certificat du lot, ni une seconde vérification indépendante, ni un protocole de fabrication sûr.

## Mobile

Le layout est prévu pour les petits écrans, avec prise en compte des zones de sécurité iOS. Le test d’émulation iPhone 12 mini utilise un viewport de 375 × 812 CSS pixels ; cela vérifie la mise en page, sans remplacer un essai sur appareil physique.
