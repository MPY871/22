# SC4R — application native iPhone

Les sources complètes de l'application SwiftUI sont dans `SC4R-iOS-sources.zip`, sous le dossier `ios/`. Elles comprennent le projet Xcode, les ressources, les tests natifs et les scripts de compilation et de signature. L'application fonctionne directement sur l'iPhone, sans serveur PC. Les recherches réseau utilisent directement Internet ou le réseau local.

La branche `codex/sc4r-ios-native` conserve l'archive Python existante. GitHub Actions extrait les sources, compile l'application et les tests, puis exécute les tests sur simulateur iPhone à chaque mise à jour des sources ou du workflow. L'attente de démarrage du simulateur est limitée à cinq minutes.

La [validation finale sur Mac](https://github.com/MPY871/22/actions/runs/37239686964) est réussie : **27 tests passent, zéro échec** (25 tests unitaires et 2 tests d'interface). Xcode 26.6 a compilé une application iPhone ARM64 avec le SDK iOS 26.5, pour iOS 16 et versions suivantes. L'avertissement Swift sur l'affichage de la photo a été corrigé.

Les tests vérifient notamment le parcours quantité → opérateur → résultats, le retour et la remise à zéro, la relecture de la photo depuis le stockage local et la protection contre les anciens imports. Les deux captures des tests d'interface montrent le choix de l'opérateur puis les résultats. Un contrôle sur un iPhone physique reste nécessaire pour le sélecteur Photos, les autorisations réseau et les imports/exports Fichiers.

L'artefact `SC4R-iPhone-non-signe` contient l'IPA **non signée** : une signature Apple est nécessaire avant installation. Le workflow `sc4r-testflight.yml` prépare une signature manuelle et un envoi optionnel à App Store Connect, désactivé par défaut. Aucun certificat Apple ni envoi TestFlight n'a été configuré.

**8 outils sont portés nativement.** L'obfuscateur Python, l'analyseur Windows et le décompilateur Python restent dans le code original. Les comptes, licences et l'assistant IA de la version bureau ne sont pas portés. Le fichier `ios/FONCTIONS.md` détaille les fonctions de chaque outil.

`ios/INSTALLER_DEPUIS_WINDOWS.md` décrit les modes d'installation. La fiche `ios/VALIDATION.md` conserve l'état de la préparation initiale du 4 octobre 2026 ; les résultats de compilation et de tests effectués ensuite sont ceux liés ci-dessus.
