# Générer l'APK depuis un téléphone Android (sans installer Android Studio)

Le dépôt contient un workflow GitHub Actions qui peut compiler l'APK dans le cloud. Il faut un compte GitHub gratuit. L'APK n'est pas joint à ce projet : il sera produit après une compilation réussie.

## Étapes
1. Télécharge le ZIP du projet et décompresse-le avec l'application Fichiers ou un gestionnaire ZIP sur Android.
2. Ouvre https://github.com et crée un compte si nécessaire.
3. Crée un nouveau dépôt, par exemple `adventure-trip-mg`. Pour un premier essai, choisis **Private**.
4. Dans le dépôt, utilise **Add file → Upload files**. Téléverse le contenu du dossier du projet, y compris le dossier caché `.github/workflows` contenant `build-apk.yml`. Si l'import depuis le téléphone est difficile, ouvre GitHub dans Chrome → ⋮ → **Version pour ordinateur**.
5. Une fois les fichiers importés sur la branche `main`, ouvre l'onglet **Actions**. Choisis **Construire APK Android**, puis **Run workflow** si le workflow n'a pas démarré automatiquement.
6. Attends la fin du travail. Une coche verte indique que les étapes se sont terminées ; une croix rouge indique qu'il faut ouvrir les journaux pour voir l'erreur.
7. Dans le résultat du workflow, descends jusqu'à **Artifacts**, puis télécharge `Adventure-Trip-MG-APK`. Décompresse l'archive téléchargée pour récupérer `app-release.apk`.
8. Sur Android, ouvre le fichier APK et accepte l'installation si tu fais confiance au fichier que tu viens de compiler. Android peut demander l'autorisation d'installer depuis cette source.

## Important
- Le workflow compile le prototype Flutter. Il ne configure pas Firebase, ne crée pas de comptes marchands et n'active pas les paiements.
- Si la vérification `flutter analyze` échoue, l'APK ne sera pas produit. Ouvre Actions → exécution échouée → étape rouge pour lire l'erreur ; ne partage pas de mot de passe ou de clé privée.
- L'app peut ouvrir son catalogue de démonstration sans Firebase, mais les comptes, demandes sauvegardées en ligne et soumissions prestataires nécessitent une configuration Firebase correcte.
- Ne publie pas de vraies données de clients dans la démo administrateur. Le fichier `admin/index.html` conserve les changements localement dans le navigateur et n'est pas connecté à l'app Android.
