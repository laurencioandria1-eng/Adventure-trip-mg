# Adventure Trip MG — Kit de démarrage v0.3.0

Ce ZIP contient :
- l'application Flutter Android de démonstration (`lib/`),
- un tableau de bord web administrateur **de démonstration locale** (`admin/index.html`),
- les règles Firestore et un squelette Cloud Functions,
- un workflow GitHub Actions pour tenter de compiler l'APK dans le cloud depuis un téléphone,
- un guide de compilation sans ordinateur (`BUILD_APK_FR.md`).

## Ce que tu peux essayer gratuitement
1. Ouvre `admin/index.html` dans un navigateur pour essayer le tableau de bord local.
2. Modifie/ajoute des prestations, change les statuts de réservations et de prestataires, calcule la commission théorique et exporte le catalogue en CSV.
3. Importe les sources sur GitHub et lance le workflow pour compiler l'APK dans le cloud.

## Limites importantes
- L'administrateur web est une maquette locale : les données sont enregistrées dans le navigateur utilisé, ne sont ni sécurisées ni partagées avec l'application Android.
- Les prix de démonstration et conversions EUR/USD dans l'app ne sont pas des tarifs contractuels ni des taux de change en temps réel.
- Les demandes, comptes, notifications e-mail, validation et paiements en production nécessitent configuration, sécurité et tests.
- Aucun paiement réel ni transfert de commission n'est activé. Pour Orange Money/MVola, il faut les comptes marchands et les accès API officiels. Les secrets doivent rester côté serveur.

## Construire l'APK depuis Android
Suis `BUILD_APK_FR.md`. GitHub Actions compile le code sur une machine cloud et publie un artefact téléchargeable si toutes les étapes réussissent. Cela ne garantit pas que l'app est prête pour des clients réels.

## Sécurité admin
L'adresse d'administration prévue dans le code est `laurenciodria1@gmail.com`, mais l'adresse seule ne confère aucun privilège. Le rôle admin doit être attribué côté serveur et vérifié par des règles sécurisées. Ne donne pas de droits admin depuis l'app cliente.
