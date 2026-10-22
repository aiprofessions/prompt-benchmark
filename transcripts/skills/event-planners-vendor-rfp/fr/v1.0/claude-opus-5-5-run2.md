# Transcript — skill event-planners-vendor-rfp [fr] — claude-opus-5-5 — run 2

- model_id: `claude-opus-5-5` (provider `anthropic`)
- started_utc: 2026-10-21T06:30:34+00:00
- duration_s: 50.0
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

APPEL D'OFFRES TRAITEUR — SÉMINAIRE ANNUEL EXEMPLE CONSEIL


1. EN-TÊTE DE LA CONSULTATION

Objet : Appel d'offres — Prestation traiteur (accueil café, déjeuner assis, cocktail) — Séminaire annuel de la société Exemple Conseil
Émetteur : [NON FOURNI] — Contact : [NON FOURNI]
Date d'envoi : [NON FOURNI] — Référence : [NON FOURNI]


2. PRÉSENTATION DE L'ÉVÉNEMENT

Client : Exemple Conseil
Nature : séminaire annuel
Lieu : Domaine Modèle, près de Bordeaux. Adresse exacte : [NON FOURNI]
Date : jeudi 10 juin 2027
Programme :
  - Accueil café : 8h30
  - Déjeuner assis : 12h30
  - Cocktail : 18h00–19h30
Participants : 120
Budget : [NON FOURNI]


3. PÉRIMÈTRE ET BESOINS

Prestations et équipements :
  - Accueil café à 8h30, pour 120 participants. Effectif à confirmer pour ce temps.
  - Déjeuner assis à 12h30, pour 120 participants. Effectif à confirmer pour ce temps.
  - Cocktail de 18h00 à 19h30, pour 120 participants. Effectif à confirmer pour ce temps.
  - Boissons alcoolisées : aucune boisson alcoolisée n'est incluse dans la prestation. Le client fournit lui-même les vins.
  - Boissons sans alcool, vaisselle, verrerie, nappage, mobilier et personnel de service : [NON FOURNI]. Le prestataire précise ce qu'il propose et le chiffre ligne par ligne.

Régimes et allergies :
  - 9 végétariens
  - 3 végans
  - 2 sans gluten
  - 1 personne avec une allergie sévère à l'arachide

Programme, livraisons, montage et démontage :
  - Horaires du programme : accueil café 8h30, déjeuner assis 12h30, cocktail 18h00–19h30.
  - Heure de fin du déjeuner : [NON FOURNI].
  - Horaires de livraison : [NON FOURNI].
  - Horaires de montage : [NON FOURNI].
  - Horaires de démontage et d'enlèvement : [NON FOURNI].

Calculs nécessaires :
  - Nombre de repas sans régime particulier = 120 − (participants concernés par au moins un régime ou une allergie) = [NON FOURNI].
  - Les catégories peuvent se recouper : une personne peut être à la fois végane et sans gluten. Les végans peuvent aussi être comptés parmi les végétariens. Leur somme (9 + 3 + 2 + 1 = 15) ne représente donc pas forcément 15 personnes distinctes. Elle ne doit pas être utilisée tant que la répartition n'est pas confirmée.


4. CONTRAINTES DU LIEU

  - Pas de cuisine équipée. Le prestataire doit expliquer comment il organise la production (par exemple en laboratoire extérieur), le transport, la remise en température et le maintien en température des trois prestations sans cuisine sur place.
  - Le lieu dispose d'un office avec point d'eau. Le prestataire doit expliquer comment il utilise cet office pour le dressage, la plonge éventuelle et le rangement, ou s'il n'en a pas besoin.
  - L'alimentation électrique se limite à 2 prises 16 A. Le prestataire doit lister chaque appareil électrique prévu avec sa puissance. Il doit expliquer comment son installation respecte cette limite. Tout autre moyen d'alimentation (groupe électrogène ou autre) ne doit être proposé que sous réserve d'une autorisation du lieu, non acquise à ce stade.
  - Accès, stationnement, quai ou zone de livraison, distance entre véhicule et office, ascenseur ou monte-charge : [NON FOURNI].
  - Capacités de froid sur place, espaces de stockage, mobilier, gestion et évacuation des déchets : [NON FOURNI]. Le prestataire ne doit supposer aucun équipement ni aucune autorisation du lieu.


5. FORMAT DU DEVIS

  - Présenter chaque prestation sur une ligne distincte : accueil café, déjeuner assis, cocktail, menus adaptés aux régimes et à l'allergie, boissons sans alcool le cas échéant.
  - Présenter chaque équipement sur une ligne distincte : matériel de maintien en température, froid, vaisselle, verrerie (y compris pour le service des vins fournis par le client, le cas échéant), nappage, mobilier éventuel.
  - Pour chaque ligne, indiquer : désignation, quantité, unité, prix unitaire HT et montant HT.
  - Présenter sur des lignes séparées :
      - la main-d'œuvre (nombre de personnes, fonction, durée)
      - la livraison
      - l'enlèvement
      - les frais de service
  - Présenter les pourboires ou gratifications sur une ligne distincte.
  - Présenter séparément :
      - le total HT
      - la TVA, par taux, avec son montant
      - les autres taxes éventuelles
      - le total TTC
  - Indiquer explicitement les postes sans objet et les exclusions de l'offre.
  - Si un droit de bouchon ou des frais liés au service des vins fournis par le client sont appliqués, les présenter sur une ligne distincte.


6. DOCUMENTS DEMANDÉS AU PRESTATAIRE

  - Attestation d'assurance responsabilité civile professionnelle en cours de validité.
  - Procédure écrite de gestion des allergènes et de prévention des contaminations croisées, couvrant la préparation, le transport et le service. Elle précise notamment :
      - les mesures prévues pour la personne présentant une allergie sévère à l'arachide ;
      - l'identification et la séparation des plats sans gluten, végétariens et végans ;
      - l'information des convives et du personnel de service.
  - Liste des allergènes par plat proposé.
  - Conditions d'acompte, de paiement, d'annulation et de report.
  - Récépissé d'entrepreneur de spectacles : sans objet, aucun spectacle vivant n'est mentionné dans le brief.


7. CALENDRIER ET CRITÈRES DE CHOIX

Date limite de réponse : avant le 15 janvier 2027
Date de décision : 29 janvier 2027

Critères : [NON FOURNI]
Hypothèse : grille proposée, à valider par le client :
  - conformité au périmètre et réponse aux contraintes du lieu (absence de cuisine, 2 prises 16 A) ;
  - qualité de la procédure allergènes et régimes ;
  - prix et clarté du devis ;
  - références et expérience sur des événements comparables ;
  - souplesse des conditions d'annulation et de report.
Pondération : [NON FOURNI].

Confidentialité : limiter les données au nécessaire, les pseudonymiser et utiliser uniquement un outil approuvé par la structure. Les effectifs sont transmis sans identité des participants.

Le professionnel responsable vérifie les règles applicables.


8. POINTS À CONFIRMER

Informations administratives :
  - Émetteur de la consultation (Exemple Conseil ou agence), coordonnées du contact, date d'envoi et référence ?
  - Budget : montant, et indication HT ou TTC ?
  - Adresse exacte du Domaine Modèle ?

Effectifs :
  - L'effectif de 120 participants s'applique-t-il aux trois temps (accueil café, déjeuner, cocktail) ?
  - Répartition exacte des régimes : les 3 végans sont-ils inclus dans les 9 végétariens ? Les 2 personnes sans gluten et la personne allergique à l'arachide appartiennent-elles aussi à une autre catégorie ? Cette réponse est nécessaire pour calculer le nombre de repas sans régime particulier, actuellement [NON FOURNI].

Horaires :
  - Heure de fin du déjeuner ?
  - Horaires autorisés de livraison, de montage, de démontage et d'enlèvement ?

Contenu de la prestation :
  - Le « déjeuner assis » doit-il être servi à table ou sous forme de buffet avec places assises ?
  - Nombre de plats ?
  - Boissons sans alcool attendues (eaux, jus, softs, café au déjeuner) ?
  - Le personnel du traiteur doit-il servir les vins fournis par le client et fournir la verrerie ?
  - Vaisselle, nappage, mobilier et personnel de service à inclure ?

Lieu :
  - Conditions d'accès, de stationnement et de livraison ?
  - Présence d'espaces de froid ou de stockage ?
  - Gestion des déchets ?
  - Possibilité d'une source d'électricité supplémentaire au-delà des 2 prises 16 A, et sous quelles conditions ?

Critères :
  - Validation ou modification de la grille de critères proposée en hypothèse, et de sa pondération ?

Hygiène et allergènes :
  - Le client souhaite-t-il exclure l'arachide de l'ensemble de la prestation compte tenu de l'allergie sévère ?
  - Le lieu impose-t-il des règles d'hygiène ou de stockage pour l'office ?

Sécurité du lieu :
  - Règles du domaine concernant les appareils électriques, les appareils de cuisson ou de maintien en température, et l'occupation de l'office ?

Débit de boissons :
  - Le client fournit les vins : l'organisateur doit vérifier auprès du lieu et des interlocuteurs compétents les conditions applicables à la mise à disposition et au service de boissons alcoolisées, ainsi que la répartition des responsabilités entre client, lieu et traiteur.

Spectacle vivant :
  - Confirmer qu'aucune animation ni aucun spectacle vivant n'est prévu. Si c'est le cas, vérifier si un récépissé d'entrepreneur de spectacles est exigible et qui doit le fournir.

