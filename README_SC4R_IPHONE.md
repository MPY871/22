# SC4R — application native iPhone

Les sources complètes de l'application SwiftUI sont dans `SC4R-iOS-sources.zip`, sous le dossier `ios/`. Elles comprennent le projet Xcode, les ressources, les 27 tests natifs et les scripts de compilation et de signature. L'application fonctionne directement sur l'iPhone, sans serveur PC.

La branche `codex/sc4r-ios-native` conserve l'archive Python existante. GitHub Actions extrait les sources, exécute les tests sur simulateur iPhone puis compile une archive pour iPhone physique à chaque mise à jour des sources ou du workflow.

Une compilation réussie fournit `SC4R-iPhone-non-signe` et les résultats des tests. L'IPA produite est **non signée** : une signature Apple est nécessaire avant installation. Les fichiers `ios/FONCTIONS.md`, `ios/INSTALLER_DEPUIS_WINDOWS.md` et `ios/VALIDATION.md` dans l'archive décrivent les fonctions portées et les étapes restantes.

La compilation et les tests doivent être vérifiés dans Actions ; la présence des sources ne prouve pas leur réussite. La distribution TestFlight nécessite la configuration Apple Developer.
