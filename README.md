# Configurer php-cs-fixer avec PHPStorm sur un nouveau projet

Faire en sortes qu'il formatte lors de la sauvegarde, utilisé sur un MAC M1 avec MACOS 12.6 ou inférieur.

- Installer php-cs-fixer avec composer

`composer require --dev friendsofphp/php-cs-fixer`

- Mettre le fichier .php-cs-fixer.php à la racine du projet
- Aller dans les préférences de PHPStorm > Tools > File Watchers et ajouter un File Watcher
  - Name: `PHP CS Fixer`
  - File Type: `PHP`
  - Scope: `Current file`
  - Program: `$ProjectFileDir$/vendor/bin/php-cs-fixer`
  - Argument: `fix $FileDirRelativeToProjectRoot$/$FileName$`
  - Working directory: `$ProjectFileDir$`
  - Décocher les 2 cases dans Advanced options
  - (Optionnel): Désactiver le reformat on save en mettant */**.php dans Editor > Code Style > Formatter > Do not format (ne le faire que sur le projet courant)
