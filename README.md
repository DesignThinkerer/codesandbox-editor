# CodeSandbox URL Decoder & Editor

Un outil puissant pour décoder, visualiser et éditer les projets CodeSandbox stockés directement dans les URLs (compressés via LZ-String).

Ce projet permet de transformer les longues chaînes de caractères `parameters` des URLs CodeSandbox en une structure de projet lisible et modifiable, sans avoir besoin de passer par l'interface complète de CodeSandbox.

## 🚀 Fonctionnalités

- **Décodage LZ-String** : Décompresse instantanément les paramètres d'URL CodeSandbox (`parameters=...`).
- **Éditeur de Code Intégré** : Visualisez et modifiez le contenu des fichiers avec une coloration syntaxique basique et des numéros de ligne.
- **Gestionnaire de Fichiers Complet** :

    - 📂 Création de dossiers et fichiers.
    - ✏️ Renommage et déplacement.
    - 🗑️ Suppression (avec gestion intelligente des dossiers).
- **Régénération d'URL** : Chaque modification re-compresse automatiquement le projet et génère une nouvelle URL prête à être partagée ou ouverte.
- **Support "Projet Vide"** : Possibilité de démarrer un projet *from scratch* et de générer une URL CodeSandbox à partir de rien.
- **Liens Directs** : Bouton pour ouvrir directement votre création dans CodeSandbox.

## 🛠️ Technologies Utilisées

- **React** : Framework UI.
- **lz-string** : Pour la compression/décompression des données (compatible avec l'algo de CodeSandbox).
- **lucide-react** : Pour les icônes (interface moderne et épurée).
- **Tailwind CSS** : Pour le styling (implémenté via classes utilitaires).

## 📦 Installation et Utilisation

Ce projet est conçu pour être léger. Si vous l'intégrez dans une application React existante :

1. **Cloner le dépôt**

        git clone [https://github.com/votre-username/codesandbox-decoder.git](https://github.com/votre-username/codesandbox-decoder.git)cd codesandbox-decoder
2. **Installer les dépendances**

        npm install lucide-react# Note : lz-string est chargé via CDN dans cet exemple pour la portabilité, # mais peut être installé via 'npm install lz-string'
3. **Lancer le projet**

        npm start

## 💡 Comment ça marche ?

CodeSandbox permet de définir des projets entiers via l'API `define`. Au lieu de stocker les fichiers dans une base de données, ils compressent un objet JSON contenant tous les fichiers en une chaîne **LZ-String Base64**.

Ce projet :

1. Nettoie la chaîne d'entrée (remplacement des caractères URL-safe `-` et `_`).
2. Décompresse la chaîne pour obtenir le JSON du projet.
3. Construit une arborescence virtuelle pour l'explorateur de fichiers.
4. À chaque modification, effectue l'opération inverse pour fournir une URL à jour.

## 🤝 Contribution

Les contributions sont les bienvenues ! N'hésitez pas à ouvrir une *issue* ou une *pull request* pour améliorer l'éditeur (ajout de coloration syntaxique avancée, support de plusieurs fichiers ouverts, etc.).

## 📄 Licence

MIT
