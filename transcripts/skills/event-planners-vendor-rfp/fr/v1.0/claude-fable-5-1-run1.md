# Transcript — skill event-planners-vendor-rfp [fr] — claude-fable-5-1 — run 1

- model_id: `claude-fable-5-1` (provider `anthropic`)
- started_utc: 2026-10-21T05:45:21+00:00
- duration_s: 57.2
- exit_code: 0
- attempts: 1
- completed: True
- rubric_sha256: 2527d85617b6f679b69587f29400d01403165633c4c8a5bef06e246b1e14eb37
- skill_sha256: 74851faaed09e64e30fe7b2d8ba03d6832d85c14c7dc301eaf533562cc227386

## Query (verbatim, from query file)

````text
<skill_instructions>
---
name: event-planners-vendor-rfp
description: "Utilisez-la quand vous collez un brief événementiel pour obtenir un appel d'offres prestataires structuré, avec les informations manquantes à confirmer."
---

# Appel d'offres pour prestataires événementiels

## Ce qu'elle fait

Elle rédige un appel d'offres à partir du brief d'un organisateur d'événements ou d'un chef de projet en agence, pour une consultation en France. Elle reprend les données du brief sans les modifier et demande une offre chiffrée détaillée ainsi que les documents nécessaires. Le document est complet dès la première réponse ; les informations manquantes sont signalées pour validation avant envoi.

## Ce dont elle a besoin

- Client, nature de l'événement et prestations à consulter.
- Dates, programme horaire, horaires de livraison, de montage et de démontage.
- Lieu et contraintes connues : cuisine, accroches, accès, stationnement, équipements disponibles.
- Effectif total, effectifs par régime alimentaire et allergies, sans identité des participants.
- Exigences techniques, quantités, dimensions et puissances.
- Date limite de réponse, date de décision et critères de choix.
- Budget, montants HT ou TTC, référence de consultation et coordonnées professionnelles, s'ils sont fournis.

Les éléments manquants sont marqués [NON FOURNI] et les questions sont regroupées à la fin, sans interrompre la rédaction. Une « Hypothèse : … » peut proposer une méthode ou des critères, jamais remplacer un fait absent du brief.

## Procédure

1. Livrer toujours la sortie complète dès la première réponse : ne jamais s'arrêter pour poser des questions, attendre une confirmation, retenir une section ou un calcul. Signaler les données absentes ou ambiguës par [NON FOURNI] ; réserver « Hypothèse : … » aux propositions clairement identifiées. Regrouper toutes les questions dans la dernière section, « Points à confirmer ».
2. Recopier exactement chaque chiffre, date, horaire, quantité et exigence technique du brief, notamment les effectifs alimentaires, le programme, le montage et le démontage. Conserver les unités, la précision et la présentation des montants fournis ; ne pas arrondir ni corriger silencieusement une incohérence.
3. Pour chaque chiffre dérivé, afficher les valeurs utilisées et l'opération. Ne pas additionner ni soustraire des catégories alimentaires dont le chevauchement est inconnu : inscrire [NON FOURNI] pour le résultat et demander la répartition dans la dernière section. Signaler toute contradiction sans choisir arbitrairement une valeur.
4. Transformer chaque contrainte du lieu en obligation de préparation pour le prestataire : il doit expliquer comment son offre respecte les limites de cuisine, les accroches autorisées et les accès indiqués. Ne jamais supposer une capacité, un équipement ou une autorisation du lieu.
5. Pour toute prestation alimentaire, demander une procédure écrite de gestion des allergènes et de prévention des contaminations croisées, couvrant préparation, transport et service. Reprendre exactement les allergies et effectifs connus ; ne pas déduire l'absence d'allergies d'une absence d'information.
6. Exiger une ligne distincte pour chaque prestation et chaque équipement, puis pour la main-d'œuvre, la livraison, l'enlèvement, les frais de service et les pourboires ou gratifications. Demander les prix HT, la TVA avec taux et montant sur des lignes séparées, toute autre taxe éventuelle distinctement, puis les totaux HT et TTC. Le prestataire indique les postes sans objet ; ne préremplir aucun taux ni montant absent.
7. Demander une attestation d'assurance responsabilité civile professionnelle en cours de validité et les conditions d'acompte, de paiement, d'annulation et de report.
8. Si un spectacle vivant est prévu, inscrire dans les points à confirmer la vérification par l'organisateur de la nécessité d'un récépissé de déclaration d'entrepreneur de spectacles et de la personne concernée. Demander ce document uniquement sous réserve de cette vérification, sans l'imposer automatiquement au prestataire.
9. Indiquer la date limite de réponse, la date de décision et les critères de choix. Recopier ceux du brief ; marquer les dates absentes [NON FOURNI]. Pour les critères absents, écrire [NON FOURNI] et, si utile, ajouter une proposition sous « Hypothèse : … », à valider.
10. Marquer [NON FOURNI] tout fait absent : budget, noms, téléphones, courriels, adresse, date d'envoi, référence et capacités du lieu notamment. Ne pas remplacer une donnée absente par une valeur plausible ou par la date du jour.
11. Ne conserver que les données de participants nécessaires, sous forme d'effectifs non nominatifs. Inclure une ligne de rappel demandant de pseudonymiser les données et d'utiliser uniquement un outil approuvé par la structure ; ce rappel ne doit jamais provoquer un refus ni une pause.
12. Ne citer dans la sortie aucune loi, aucun article, aucune doctrine d'autorité, aucune décision ni aucune source, sauf si l'entrée de l'utilisateur contient cette référence. Ne pas compléter une référence fournie. Une mention obligatoire à reproduire est du contenu, pas une citation. La ligne de limites de la sortie dit seulement : « Le professionnel responsable vérifie les règles applicables. »
13. Rédiger les huit rubriques dans l'ordre du modèle. Placer les rappels avant « Points à confirmer » ; terminer par les questions, les éléments manquants et les hypothèses à valider. Inclure les vérifications d'hygiène, d'allergènes, de sécurité du lieu et de débit de boissons, selon les prestations.
14. Avant de livrer, comparer chaque valeur du document au brief, vérifier les calculs et la reprise de chaque contrainte, puis contrôler les lignes de devis et les documents demandés. Vérifier que les huit rubriques sont présentes, que chaque manque ou ambiguïté fait l'objet d'un point final et qu'aucun contenu ne suit « Points à confirmer ».

## Format de sortie

Utiliser ce modèle ; remplacer les indications par les données du brief ou [NON FOURNI]. Les demandes faites au prestataire ne constituent pas des faits ajoutés à l'événement.

```markdown
## En-tête de la consultation
Objet : Appel d'offres — [prestations] — [événement]
Émetteur : [client ou agence] — Contact : [coordonnées professionnelles]
Date d'envoi : [date ou NON FOURNI] — Référence : [référence ou NON FOURNI]

## Présentation de l'événement
Client : [client] — Nature : [nature] — Lieu : [lieu]
Dates et horaires : [reprise exacte] — Participants : [effectif exact]
Budget : [montant et qualification fournis, sinon NON FOURNI]

## Périmètre et besoins
- Prestations et équipements : [quantités et exigences exactes]
- Régimes et allergies : [informations exactes ou NON FOURNI]
- Programme, livraisons, montage et démontage : [horaires exacts]
- Calculs nécessaires : [opérations explicites, ou résultat NON FOURNI]

## Contraintes du lieu
- [Contrainte du brief] : le prestataire doit expliquer comment il la respecte.
- Capacités ou équipements nécessaires non précisés : [NON FOURNI].

## Format du devis
Présenter chaque prestation et chaque équipement sur une ligne distincte.
Pour chaque ligne : désignation, quantité, unité, prix unitaire HT et montant HT.
Séparer également : main-d'œuvre, livraison, enlèvement, frais de service.
Présenter les pourboires ou gratifications sur une ligne distincte.
Séparer le total HT, la TVA par taux avec son montant, les autres taxes éventuelles et le total TTC.
Indiquer explicitement les postes sans objet et les exclusions de l'offre.

## Documents demandés au prestataire
- Attestation d'assurance responsabilité civile professionnelle en cours de validité.
- Procédure écrite allergènes et prévention des contaminations croisées si prestation alimentaire.
- Conditions d'acompte, de paiement, d'annulation et de report.
- Si spectacle vivant : récépissé uniquement si son exigibilité et la personne concernée sont confirmées.

## Calendrier et critères de choix
Date limite de réponse : [date exacte ou NON FOURNI]
Date de décision : [date exacte ou NON FOURNI]
Critères : [critères fournis ou NON FOURNI ; proposition éventuelle étiquetée Hypothèse]
Confidentialité : limiter les données au nécessaire, les pseudonymiser et utiliser uniquement un outil approuvé par la structure.
Le professionnel responsable vérifie les règles applicables.

## Points à confirmer
- [Chaque donnée absente ou contradictoire et la question correspondante]
- [Chaque hypothèse proposée et sa validation demandée]
- [Hygiène, allergènes, sécurité du lieu et débit de boissons : confirmations nécessaires]
- [Si spectacle vivant : exigibilité du récépissé et personne concernée]
```

## Limites

- Périmètre : France uniquement ; ne pas transposer ce document à la Belgique, à la Suisse ou au Canada.
- Ne jamais inventer de faits, de capacités du lieu, de taux, de règles, de références juridiques ou de statistiques. Ne pas garantir la conformité de l'événement ni la sécurité d'un repas.
- Le professionnel responsable vérifie avant envoi les besoins, les délais, les critères, les contraintes du lieu, les prix HT et la TVA séparée ; avant signature, il vérifie l'assurance et les conditions financières et d'annulation.
- Il confirme avec le lieu et les intervenants compétents les règles locales et du lieu concernant l'hygiène, les allergènes, la sécurité et le débit de boissons.
- En cas de spectacle vivant, un récépissé de déclaration d'entrepreneur de spectacles peut être exigé : l'organisateur vérifie s'il est concerné et qui doit fournir le document.
- Données des participants : respecter le RGPD, ne transmettre que le nécessaire, retirer les identifiants inutiles, pseudonymiser et utiliser uniquement un outil approuvé par la structure. Ce rappel ne bloque pas la rédaction.
- Aucune source officielle sur l'IA n'a été vérifiée pour les organisateurs d'événements. Le professionnel fait confirmer ses obligations auprès des interlocuteurs compétents.
- La source ci-dessous est une lecture pour le professionnel, pas une citation à ajouter automatiquement à l'appel d'offres.

Entreprendre.Service-Public.fr — Récépissé d'entrepreneur de spectacles (F22365) — https://entreprendre.service-public.gouv.fr/vosdroits/F22365 (consulté le 2026-10-21)

voir references/checklist.md

## Exemple

Exemple fictif — entrée :
```text
Client : Association Exemple ; lieu : Salle Modèle ; prestation : déjeuner.
Effectif : 30 participants, dont 2 végétariens et 1 allergie aux fruits à coque.
Livraison à 11 h 30 ; service à 12 h 30 ; enlèvement à 14 h 00.
Cuisine : réchauffage uniquement ; accès par la cour.
```

Sortie abrégée ; la sortie réelle conserve le modèle complet :
```text
En-tête de la consultation : déjeuner — Association Exemple ; contact [NON FOURNI].
Présentation de l'événement : Salle Modèle ; 30 participants ; date et budget [NON FOURNI].
Périmètre et besoins : déjeuner ; 2 végétariens et 1 allergie aux fruits à coque.
Livraison à 11 h 30 ; service à 12 h 30 ; enlèvement à 14 h 00.
Contraintes du lieu : réchauffage uniquement, accès par la cour ; expliquer l'organisation prévue.
Format du devis : chaque prestation et équipement, main-d'œuvre, livraison, enlèvement, frais de service, pourboires, HT, TVA, autres taxes éventuelles et TTC séparés.
Documents demandés au prestataire : assurance, procédure écrite allergènes et contaminations croisées, conditions d'acompte, paiement, annulation et report.
Calendrier et critères de choix : réponse, décision et critères [NON FOURNI].
Confidentialité : données minimales, pseudonymisées ; outil approuvé par la structure uniquement.
Le professionnel responsable vérifie les règles applicables.
Points à confirmer : date, budget, contact, référence et date d'envoi ? Délais et critères ? Régimes cumulés ? Autres besoins et contraintes ? Hygiène, allergènes, sécurité et boissons à confirmer.
```
</skill_instructions>

Follow the skill instructions above for the user's request below.

User request:
Prépare l'appel d'offres traiteur à partir de ce brief.
Événement : séminaire annuel de la société Exemple Conseil (fictive). Jeudi 10 juin 2027. Lieu : Domaine Modèle, près de Bordeaux (fictif). Pas de cuisine équipée : un office avec point d'eau et 2 prises 16 A.
Participants : 120. Programme : accueil café 8h30, déjeuner assis 12h30, cocktail 18h00–19h30.
Le client fournit lui-même les vins : aucune boisson alcoolisée dans la prestation.
Régimes : 9 végétariens, 3 végans, 2 sans gluten, 1 personne avec une allergie sévère à l'arachide.
Réponses attendues avant le 15 janvier 2027. Décision le 29 janvier 2027.
````

## Output (verbatim stdout, session metadata stripped)

Objet : Appel d'offres — Prestation traiteur (accueil café, déjeuner assis, cocktail) — Séminaire annuel Exemple Conseil
Émetteur : Exemple Conseil (société fictive) — Contact : [NON FOURNI]
Date d'envoi : [NON FOURNI] — Référence : [NON FOURNI]

PRÉSENTATION DE L'ÉVÉNEMENT
Client : Exemple Conseil — Nature : séminaire annuel — Lieu : Domaine Modèle, près de Bordeaux (fictif) ; adresse précise [NON FOURNI]
Dates et horaires : jeudi 10 juin 2027 — accueil café 8h30, déjeuner assis 12h30, cocktail 18h00–19h30
Participants : 120
Budget : [NON FOURNI]

PÉRIMÈTRE ET BESOINS
- Prestations à chiffrer (boissons alcoolisées exclues : le client fournit lui-même les vins) :
  1. Accueil café à 8h30 pour 120 participants (contenu attendu : [NON FOURNI] ; le prestataire propose et détaille).
  2. Déjeuner assis à 12h30 pour 120 participants (nombre de services/plats, formule, durée prévue : [NON FOURNI] ; le prestataire propose et détaille).
  3. Cocktail de 18h00 à 19h30 pour 120 participants (nombre de pièces par personne, formule : [NON FOURNI] ; le prestataire propose et détaille).
- Équipements : mobilier, tables, chaises, nappage, vaisselle, verrerie, matériel de maintien en température, équipements de service — fournis par le lieu ou à apporter par le prestataire : [NON FOURNI]. Le prestataire chiffre ce qu'il fournit et liste ce qu'il suppose fourni par ailleurs.
- Boissons sans alcool (eaux, softs, café/thé pour les trois temps) : incluses dans le périmètre à chiffrer, quantités à proposer par le prestataire. Service des vins fournis par le client (verrerie, débouchage, service en salle, droit de bouchon) : [NON FOURNI], à chiffrer si applicable.
- Personnel de service : effectif proposé par le prestataire pour chaque temps, avec le ratio retenu.
- Régimes et allergies (effectifs tels que fournis, sans identité) :
  - 9 végétariens
  - 3 végans
  - 2 sans gluten
  - 1 personne avec une allergie sévère à l'arachide
  Le chevauchement entre ces catégories n'est pas indiqué ; le nombre total de repas spécifiques et le nombre de repas « standard » restants sont [NON FOURNI] (voir Points à confirmer). Le prestataire doit indiquer comment chaque régime est identifié et servi en salle et au cocktail.
- Programme, livraisons, montage et démontage :
  - Horaires du programme : 8h30 (accueil café), 12h30 (déjeuner assis), 18h00–19h30 (cocktail).
  - Horaires de livraison, de montage, de démontage et d'enlèvement : [NON FOURNI]. Le prestataire indique les créneaux qu'il demande pour chaque temps.
- Calculs nécessaires : aucun total dérivé n'est calculé. Repas spécifiques cumulés = [NON FOURNI] (répartition des recoupements inconnue). Effectif total = 120 (valeur du brief, reprise sans calcul).

CONTRAINTES DU LIEU
- Pas de cuisine équipée sur place : le prestataire doit expliquer comment son offre est réalisable sans cuisine (préparation en laboratoire, transport, maintien/remise en température, dressage), pour les trois temps.
- Office disponible avec un point d'eau et 2 prises 16 A : le prestataire doit indiquer son besoin électrique total et détaillé par appareil (puissance en W ou A, nombre de circuits), confirmer que l'offre tient dans 2 prises 16 A ou chiffrer distinctement les solutions alternatives qu'il propose (groupe électrogène, matériel au gaz, etc.), sous réserve d'accord du lieu.
- Accès, stationnement, livraison, zone de déchargement, ascenseur/monte-charge, stockage réfrigéré, gestion des déchets, eau chaude : [NON FOURNI]. Le prestataire liste les capacités du lieu qu'il suppose nécessaires ; aucune ne doit être considérée comme acquise.
- Surface et configuration des espaces (salle du déjeuner, espace cocktail, espace accueil café), capacité d'accueil assise, accroches et décoration autorisées : [NON FOURNI].

FORMAT DU DEVIS
Présenter chaque prestation et chaque équipement sur une ligne distincte.
Pour chaque ligne : désignation, quantité, unité, prix unitaire HT et montant HT.
Lignes attendues au minimum : accueil café ; déjeuner assis (par composante si la formule est modulaire) ; cocktail ; boissons sans alcool par temps ; repas spécifiques (végétarien, végan, sans gluten, sans arachide) ; service des vins du client / droit de bouchon ; chaque équipement loué ou fourni ; solution électrique ou matériel autonome le cas échéant.
Séparer également : main-d'œuvre (par fonction, nombre de personnes, durée et taux horaire ou forfait, avec heures supplémentaires éventuelles), livraison, enlèvement, frais de service.
Présenter les pourboires ou gratifications sur une ligne distincte.
Séparer le total HT, la TVA par taux avec son montant (une ligne par taux), les autres taxes éventuelles et le total TTC.
Indiquer explicitement les postes sans objet et les exclusions de l'offre (notamment les boissons alcoolisées, exclues par le brief).
Préciser la durée de validité de l'offre et les conditions de révision en cas de variation de l'effectif.

DOCUMENTS DEMANDÉS AU PRESTATAIRE
- Attestation d'assurance responsabilité civile professionnelle en cours de validité.
- Procédure écrite de gestion des allergènes et de prévention des contaminations croisées couvrant préparation, transport et service, avec le traitement spécifique de l'allergie sévère à l'arachide (séparation, étiquetage, personnel informé, dressage et service distincts) et des régimes végétarien, végan et sans gluten.
- Description de l'organisation sans cuisine équipée : chaîne du froid et du chaud, maintien en température, matériel apporté, plan de charge électrique.
- Conditions d'acompte, de paiement, d'annulation et de report.
- Références sur des prestations comparables (séminaire, effectif similaire, site sans cuisine) : [NON FOURNI si non exigé par le client ; à confirmer].
- Aucun spectacle vivant n'est mentionné dans le brief : pas de récépissé demandé.

CALENDRIER ET CRITÈRES DE CHOIX
Date limite de réponse : 15 janvier 2027
Date de décision : 29 janvier 2027
Critères : [NON FOURNI]
Hypothèse : pondération à valider — qualité et adéquation de la proposition culinaire (incluant les régimes et l'allergie à l'arachide) ; faisabilité technique sans cuisine équipée et respect de la limite électrique ; prix total HT ; références et organisation de l'équipe de service ; conditions financières et d'annulation.
Modalités de réponse (adresse, format, visite préalable du site) : [NON FOURNI].
Confidentialité : limiter les données au nécessaire, les pseudonymiser et utiliser uniquement un outil approuvé par la structure.
Le professionnel responsable vérifie les règles applicables.

POINTS À CONFIRMER
- Coordonnées professionnelles de l'émetteur (nom du contact, courriel, téléphone), date d'envoi et référence de consultation ?
- Adresse précise du Domaine Modèle et modalités d'accès, de stationnement, de déchargement et d'horaires d'ouverture du site ?
- Budget total ou enveloppe par temps, en HT ou TTC ?
- Horaires de livraison, de montage, de démontage et d'enlèvement autorisés par le lieu pour chaque temps (café, déjeuner, cocktail) ?
- Régimes alimentaires : les 9 végétariens, 3 végans, 2 sans gluten et la personne allergique à l'arachide sont-ils des personnes distinctes ou certaines cumulent-elles plusieurs régimes ? Répartition exacte demandée pour éviter tout total erroné.
- L'allergie à l'arachide concerne-t-elle aussi d'autres fruits à coque ou huiles ? Faut-il prévoir un menu totalement exempt d'arachide pour l'ensemble des 120 participants ?
- Contenu attendu pour chaque temps : formule du déjeuner (entrée/plat/dessert ?), nombre de pièces au cocktail, composition de l'accueil café ?
- Équipements fournis par le lieu (mobilier, vaisselle, verrerie, nappage, réfrigération, stockage) ou à apporter par le prestataire ?
- Autres équipements électriques utilisés le même jour sur les 2 prises 16 A (régie, sono, éclairage) ? Autorisation du lieu pour matériel au gaz ou groupe électrogène ?
- Service des vins fournis par le client : par le personnel du prestataire ? Droit de bouchon accepté ? Qui fournit la verrerie ? Le client a-t-il vérifié avec le lieu les conditions de service de boissons alcoolisées (débit de boissons, autorisation du domaine) ?
- Critères de choix : la pondération proposée en Hypothèse est-elle validée ou remplacée par les critères du client ?
- Modalités de réponse : adresse d'envoi des offres, format, visite de site possible et date ?
- Références exigées du prestataire : oui/non ?
- Hygiène et sécurité : règles du lieu concernant l'hygiène, le stockage, les déchets, la sécurité incendie et l'usage de l'office à confirmer avec le Domaine Modèle ; le prestataire doit s'y conformer.
- Effectif de 120 : définitif ou estimé, avec date de confirmation du nombre final ?

