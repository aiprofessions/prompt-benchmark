# Transcript — skill event-planners-vendor-rfp [fr] — claude-fable-5-1 — run 3

- model_id: `claude-fable-5-1` (provider `anthropic`)
- started_utc: 2026-10-21T09:37:51+00:00
- duration_s: 73.7
- exit_code: 0
- attempts: 1
- completed: True
- rubric_sha256: 2527d85617b6f679b69587f29400d01403165633c4c8a5bef06e246b1e14eb37
- skill_sha256: 2c89eee7c9941bea85db73a769b07778e9c87f18ce43893163577a7a60c1027d

## Query (verbatim, from query file)

````text
<skill_instructions>
---
name: event-planners-vendor-rfp
description: "Utilisez-la quand vous collez un brief événementiel pour obtenir un appel d'offres prestataires structuré, avec les informations manquantes à confirmer."
---

# Appel d'offres pour prestataires événementiels

## Ce qu'elle fait

Elle rédige un appel d'offres à partir du brief d'un organisateur d'événements ou d'un chef de projet en agence, pour une consultation en France. Elle reprend les données fournies sans les modifier et demande un devis détaillé ainsi que les documents nécessaires. Le document comporte toutes les rubriques dès la première réponse ; les informations manquantes et les critères proposés restent à valider avant envoi.

## Ce dont elle a besoin

- Client, nature de l'événement et prestations à consulter.
- Dates, programme, horaires de livraison, d'installation, de montage, de démontage et d'enlèvement.
- Lieu et contraintes connues : cuisine, accroches, accès, stationnement, équipements disponibles.
- Effectif total, effectifs par régime alimentaire et allergies, sans identité des participants.
- Exigences techniques, quantités, dimensions et puissances.
- Date limite de réponse, date de décision et critères de choix.
- Budget, montants HT ou TTC, référence de consultation et coordonnées professionnelles, s'ils sont fournis.

Les éléments manquants sont marqués [NON FOURNI] et les questions sont regroupées à la fin, sans interrompre la rédaction. Les critères de choix absents sont toujours proposés sous l'intitulé « Critères de choix proposés — à valider avec le client avant envoi ». Aucune hypothèse ne remplace un fait absent.

## Procédure

1. Livrer toujours la sortie complète dès la première réponse : ne jamais s'arrêter pour poser des questions, attendre une confirmation, retenir une section ou un calcul. Signaler les données absentes ou ambiguës par [NON FOURNI]. Réserver « Hypothèse : … » aux propositions d'organisation à valider, sans inventer de donnée factuelle. Regrouper toutes les questions dans la dernière section, « Points à confirmer ».
2. Recopier exactement chaque chiffre, date, horaire, quantité et exigence technique du brief, notamment les effectifs alimentaires, le programme et les horaires d'intervention. Conserver les unités, la précision et la présentation des montants fournis ; ne pas arrondir ni corriger silencieusement une incohérence.
3. Pour chaque chiffre dérivé, afficher les valeurs utilisées et l'opération. Ne pas additionner ni soustraire des catégories alimentaires dont le chevauchement est inconnu : inscrire [NON FOURNI] pour le résultat et demander la répartition dans la dernière section. Signaler toute contradiction en conservant les valeurs fournies, sans en choisir une arbitrairement.
4. Transformer chaque contrainte du lieu en obligation de préparation pour le prestataire : il doit expliquer comment son offre respecte les limites de cuisine, les accroches autorisées et les accès indiqués. Ne jamais supposer une capacité, un équipement ou une autorisation du lieu.
5. Pour toute prestation alimentaire, demander une procédure écrite de gestion des allergènes et de prévention des contaminations croisées, couvrant préparation, transport et service. Reprendre exactement les allergies et effectifs connus ; ne pas déduire l'absence d'allergies d'une absence d'information.
6. Imposer des lignes séparées pour chaque prestation (repas, boissons, équipement), le personnel, la livraison, l'installation / mise en place, le démontage / l'enlèvement, les frais de service et les pourboires ou gratifications. Demander ensuite des lignes distinctes pour le total HT, la TVA avec taux et montant, chaque autre taxe éventuelle et le total TTC. Le prestataire indique « sans objet » pour tout poste non concerné. Ne préremplir aucun taux ni montant absent.
7. Demander une attestation d'assurance responsabilité civile professionnelle en cours de validité et les conditions d'acompte, de paiement, d'annulation et de report.
8. Si un spectacle vivant est prévu, inscrire dans les points à confirmer la vérification par l'organisateur de la nécessité d'un récépissé de déclaration d'entrepreneur de spectacles et de la personne concernée. Demander ce document uniquement sous réserve de cette vérification, sans l'imposer automatiquement au prestataire.
9. Dans « Calendrier et critères de choix », indiquer la date limite de réponse et la date de décision, recopiées du brief ou marquées [NON FOURNI]. Recopier exactement les critères fournis. À défaut, proposer une courte liste de critères concrets sous l'intitulé « Critères de choix proposés — à valider avec le client avant envoi » : conformité aux besoins, clarté et exhaustivité du devis, références comparables, organisation face aux contraintes du lieu, procédure allergènes / sécurité si pertinent, assurance et conditions. Ne jamais remplacer ces critères par [NON FOURNI] ni par une simple hypothèse. Rappeler leur validation dans « Points à confirmer ».
10. Marquer [NON FOURNI] tout fait absent : budget, noms, téléphones, courriels, adresse, date d'envoi, référence et capacités du lieu notamment. Ne jamais le remplacer par une valeur plausible ou par la date du jour.
11. Ne conserver que les données de participants nécessaires, sous forme d'effectifs non nominatifs. Inclure une ligne rappelant de pseudonymiser les données et d'utiliser uniquement un outil approuvé par la structure ; ce rappel ne doit jamais provoquer un refus ni une pause.
12. Ne citer dans la sortie aucune loi, aucun article, aucune recommandation d'autorité, aucune décision ni aucune source, sauf si l'entrée de l'utilisateur contient cette référence. Ne pas compléter une référence fournie. Une mention obligatoire à reproduire est du contenu, pas une citation. La ligne de limites dit seulement : « Le professionnel responsable vérifie les règles applicables. »
13. Rédiger les huit rubriques dans l'ordre du modèle. Placer les rappels avant « Points à confirmer » ; terminer par les questions, les éléments manquants et les propositions à valider. Y inclure les vérifications d'hygiène, d'allergènes, de sécurité du lieu et de débit de boissons selon les prestations.
14. Avant de livrer, comparer chaque valeur au brief, vérifier les calculs et chaque contrainte. Contrôler toutes les lignes séparées de l'étape 6, les critères fournis ou proposés et les documents demandés. Vérifier les huit rubriques, un point final pour chaque manque, et l'absence de contenu après la section « Points à confirmer ».

## Format de sortie

Utiliser ce modèle en remplaçant les indications par les données exactes ou [NON FOURNI]. Les demandes au prestataire ne constituent pas des faits ajoutés. Choisir uniquement la variante de critères applicable et adapter les demandes conditionnelles aux prestations.

```
## En-tête de la consultation
Objet : Appel d'offres — [prestations] — [événement]
Émetteur : [client ou agence] — Contact : [coordonnées professionnelles]
Date d'envoi : [date] — Référence : [référence]

## Présentation de l'événement
Client : [client] — Nature : [nature] — Lieu : [lieu et adresse]
Dates et horaires : [reprise exacte] — Participants : [effectif exact]
Budget : [montant et qualification fournis]

## Périmètre et besoins
- Prestations et équipements : [quantités et exigences exactes]
- Régimes et allergies : [informations exactes]
- Programme et horaires d'intervention : [reprise exacte]
- Calculs nécessaires : [opérations explicites ; résultat NON FOURNI si impossible]

## Contraintes du lieu
- [Chaque contrainte fournie] : expliquer comment l'offre la respecte.
- [Capacités ou équipements nécessaires non précisés] : [NON FOURNI].

## Format du devis
Chaque prestation (repas, boissons, équipement) doit avoir sa propre ligne :
désignation, quantité, unité, prix unitaire HT et montant HT.
Prévoir une ligne distincte pour chacun des postes suivants :
personnel ; livraison ; installation / mise en place ; démontage / enlèvement ;
frais de service ; pourboires ou gratifications.
Présenter ensuite sur des lignes séparées :
- Total HT
- TVA : taux et montant, en distinguant les taux si nécessaire
- Chaque autre taxe éventuelle
- Total TTC
Indiquer « sans objet » pour tout poste non concerné et préciser les exclusions.

## Documents demandés au prestataire
- Attestation d'assurance responsabilité civile professionnelle en cours de validité.
- Si prestation alimentaire : procédure écrite allergènes et prévention des contaminations croisées, de la préparation au service, transport compris.
- Conditions d'acompte, de paiement, d'annulation et de report.
- Si spectacle vivant : récépissé uniquement si son exigibilité et la personne concernée sont confirmées.

## Calendrier et critères de choix
Date limite de réponse : [date exacte]
Date de décision : [date exacte]
Critères de choix : [critères du brief recopiés exactement]
[Si aucun critère n'est fourni, remplacer la ligne précédente par :]
Critères de choix proposés — à valider avec le client avant envoi :
- Conformité aux besoins exprimés
- Clarté et exhaustivité du devis détaillé
- Références sur des événements comparables
- Organisation proposée face aux contraintes du lieu
- Procédure allergènes / sécurité, si pertinent
- Assurance et conditions
Confidentialité : limiter les données au nécessaire, les pseudonymiser et utiliser uniquement un outil approuvé par la structure.
Le professionnel responsable vérifie les règles applicables.

## Points à confirmer
- [Chaque donnée absente ou contradictoire et la question correspondante]
- [Si critères proposés : validation avec le client avant envoi]
- [Chaque hypothèse d'organisation proposée et sa validation demandée]
- [Hygiène, allergènes, sécurité du lieu et débit de boissons : confirmations pertinentes]
- [Si spectacle vivant : exigibilité du récépissé et personne concernée]
```

## Limites

- Périmètre : France uniquement ; ne pas transposer ce document à la Belgique, à la Suisse ou au Canada.
- Ne jamais inventer de faits, de prix, de budget, de noms, de capacités du lieu, de taux, de règles, de références juridiques ou de statistiques. Ne pas garantir la conformité de l'événement ni la sécurité d'un repas.
- Le professionnel responsable vérifie avant envoi les besoins, les délais, les critères de choix, les contraintes du lieu et le cadre du devis, notamment les lignes HT et TVA séparées. Avant signature, il vérifie les montants, l'adéquation et la validité de l'assurance, ainsi que les conditions financières et d'annulation.
- Il confirme avec le lieu et les intervenants compétents les règles locales et du lieu concernant l'hygiène, les allergènes, la sécurité et le débit de boissons.
- En cas de spectacle vivant, un récépissé de déclaration d'entrepreneur de spectacles peut être exigé : l'organisateur vérifie s'il est concerné et qui doit fournir le document.
- Données des participants : respecter le RGPD, ne transmettre que le nécessaire, retirer les identifiants inutiles, pseudonymiser et utiliser uniquement un outil approuvé par la structure. Ce rappel ne bloque pas la rédaction.
- Aucune source officielle sur l'IA n'a été vérifiée pour les organisateurs d'événements. Le professionnel fait confirmer ses obligations auprès des interlocuteurs compétents.
- La source ci-dessous est une lecture pour le professionnel, pas une citation à ajouter automatiquement à l'appel d'offres.

Entreprendre.Service-Public.fr — Récépissé d'entrepreneur de spectacles (F22365) — https://entreprendre.service-public.gouv.fr/vosdroits/F22365 (consulté le 2026-10-21)

voir references/checklist.md

## Exemple

Exemple fictif — entrée :
```
Client : Association Exemple ; lieu : Salle Modèle ; prestation : déjeuner.
Effectif : 30 participants, dont 2 végétariens et 1 allergie aux fruits à coque.
Livraison à 11 h 30 ; service à 12 h 30 ; enlèvement à 14 h 00.
Cuisine : réchauffage uniquement ; accès par la cour.
```

Sortie abrégée ; la sortie réelle conserve le modèle complet :
```
En-tête de la consultation : déjeuner — Association Exemple ; contact, date d'envoi et référence [NON FOURNI].
Présentation de l'événement : Salle Modèle ; 30 participants ; adresse, date et budget [NON FOURNI].
Périmètre et besoins : déjeuner ; 2 végétariens et 1 allergie aux fruits à coque.
Livraison à 11 h 30 ; service à 12 h 30 ; enlèvement à 14 h 00 ; installation et démontage [NON FOURNI].
Contraintes du lieu : réchauffage uniquement, accès par la cour ; expliquer l'organisation prévue.
Format du devis : lignes séparées repas, boissons, équipement, personnel, livraison, installation / mise en place, démontage / enlèvement, frais de service, pourboires ; puis lignes distinctes HT, TVA (taux et montant), autres taxes éventuelles, TTC ; « sans objet » si non concerné.
Documents demandés au prestataire : assurance, procédure écrite allergènes et contaminations croisées (préparation, transport, service), conditions d'acompte, paiement, annulation et report.
Calendrier et critères de choix : réponse et décision [NON FOURNI].
Critères de choix proposés — à valider avec le client avant envoi : conformité aux besoins, devis clair et complet, références comparables, organisation face aux contraintes du lieu, procédure allergènes, assurance et conditions.
Confidentialité : données minimales, pseudonymisées ; outil approuvé par la structure uniquement.
Le professionnel responsable vérifie les règles applicables.
Points à confirmer : date, adresse, budget, contact, référence et date d'envoi ? Délais de réponse et de décision ? Validation des critères avec le client ? Horaires d'installation et de démontage ? Chevauchement des régimes et allergies ? Hygiène, allergènes, sécurité et boissons à confirmer selon les prestations.
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

APPEL D'OFFRES — PRESTATION TRAITEUR
Séminaire annuel Exemple Conseil — jeudi 10 juin 2027

1. EN-TÊTE DE LA CONSULTATION

Objet : Appel d'offres — prestation traiteur (accueil café, déjeuner assis, cocktail) — séminaire annuel Exemple Conseil
Émetteur : Exemple Conseil (société fictive) — Contact : [NON FOURNI]
Date d'envoi : [NON FOURNI] — Référence : [NON FOURNI]

2. PRÉSENTATION DE L'ÉVÉNEMENT

Client : société Exemple Conseil (fictive)
Nature : séminaire annuel
Lieu : Domaine Modèle, près de Bordeaux (fictif) — adresse : [NON FOURNI]
Dates et horaires : jeudi 10 juin 2027 — accueil café 8h30, déjeuner assis 12h30, cocktail 18h00–19h30
Participants : 120
Budget : [NON FOURNI]

3. PÉRIMÈTRE ET BESOINS

Prestations demandées :
  - Accueil café à 8h30 pour 120 participants (contenu, quantités et boissons chaudes/froides souhaitées : [NON FOURNI] — le prestataire propose et chiffre)
  - Déjeuner assis à 12h30 pour 120 participants (nombre de services, format du menu, vaisselle, nappage, mobilier : [NON FOURNI] — le prestataire précise ce qui est inclus)
  - Cocktail de 18h00 à 19h30 pour 120 participants (nombre de pièces par personne, dînatoire ou non : [NON FOURNI] — le prestataire propose et chiffre)
  - Boissons : le client fournit lui-même les vins ; aucune boisson alcoolisée dans la prestation. Boissons non alcoolisées à prévoir par le prestataire sur les trois temps : [NON FOURNI] — le prestataire précise et chiffre. Service des vins du client (verrerie, mise au frais, personnel de service) : [NON FOURNI] — le prestataire indique s'il le prend en charge et à quelles conditions.

Régimes et allergies (effectifs non nominatifs, recopiés du brief) :
  - 9 végétariens
  - 3 végans
  - 2 sans gluten
  - 1 personne avec une allergie sévère à l'arachide
  Chevauchement éventuel entre ces catégories : [NON FOURNI]. Le prestataire propose pour chacun des trois temps une offre adaptée à chaque régime et une garantie écrite d'absence d'arachide pour la personne concernée.

Programme et horaires d'intervention :
  - Accueil café : 8h30
  - Déjeuner assis : 12h30
  - Cocktail : 18h00–19h30
  - Horaires de livraison, d'installation, de montage, de démontage et d'enlèvement : [NON FOURNI] — le prestataire indique les créneaux dont il a besoin ; ils seront validés avec le lieu.

Calculs nécessaires :
  - Durée du cocktail : 19h30 − 18h00 = 1 h 30
  - Nombre de menus « standard » (sans régime particulier) : 120 − (9 végétariens + 3 végans + 2 sans gluten + 1 allergie arachide) = [NON FOURNI], le chevauchement entre catégories n'étant pas connu (une même personne peut relever de plusieurs catégories). Répartition exacte demandée en section 8.
  - Aucun autre chiffre dérivé.

4. CONTRAINTES DU LIEU

  - Pas de cuisine équipée sur place : le prestataire explique comment il produit, transporte, maintient en température et dresse l'ensemble des prestations sans cuisine (cuisine centrale, liaison froide/chaude, matériel mobile apporté).
  - Office disponible : un point d'eau et 2 prises 16 A uniquement. Le prestataire liste tout le matériel électrique qu'il prévoit de brancher avec la puissance de chacun, démontre que l'ensemble tient dans 2 prises 16 A, et précise s'il a besoin d'une alimentation supplémentaire (groupe électrogène, autre circuit) — toute alimentation complémentaire reste à confirmer avec le lieu, jamais présumée.
  - Accès, horaires d'accès, stationnement et déchargement : [NON FOURNI] — le prestataire indique ses besoins (gabarit des véhicules, durée, proximité de l'office).
  - Accroches, décoration, signalétique autorisées : [NON FOURNI].
  - Mobilier, vaisselle, nappage, matériel de froid et de réchauffage disponibles sur place : [NON FOURNI] — le prestataire chiffre une solution complète par ses propres moyens et indique séparément ce qu'il pourrait retirer si le lieu fournit certains éléments.
  - Espaces (salle du déjeuner, espace cocktail, espace café), surfaces et capacités : [NON FOURNI].
  - Gestion des déchets et évacuation : [NON FOURNI] — le prestataire décrit sa proposition.

5. FORMAT DU DEVIS

Chaque prestation (accueil café, déjeuner assis, cocktail, boissons non alcoolisées, équipement et matériel) doit faire l'objet d'une ligne propre : désignation, quantité, unité, prix unitaire HT et montant HT. Les menus adaptés (végétarien, végan, sans gluten, sans arachide) apparaissent sur des lignes distinctes avec leur quantité et leur éventuel surcoût.

Prévoir une ligne distincte pour chacun des postes suivants :
  - personnel (nombre, fonctions, horaires, taux)
  - livraison
  - installation / mise en place
  - démontage / enlèvement
  - frais de service
  - pourboires ou gratifications
  - service des vins fournis par le client, s'il est proposé (verrerie, mise au frais, personnel)

Présenter ensuite sur des lignes séparées :
  - Total HT
  - TVA : taux et montant, en distinguant les taux si plusieurs s'appliquent
  - Chaque autre taxe éventuelle
  - Total TTC

Indiquer « sans objet » pour tout poste non concerné. Préciser les exclusions, la durée de validité de l'offre et les options chiffrées à part.

6. DOCUMENTS DEMANDÉS AU PRESTATAIRE

  - Attestation d'assurance responsabilité civile professionnelle en cours de validité.
  - Procédure écrite de gestion des allergènes et de prévention des contaminations croisées, de la préparation au service, transport compris, traitant explicitement de l'allergie sévère à l'arachide (identification des plats, séparation, information du personnel de service, conduite à tenir).
  - Description écrite de la logistique sans cuisine : production, transport, maintien en température, matériel apporté, puissance électrique requise.
  - Conditions d'acompte, de paiement, d'annulation et de report.
  - Références sur des événements comparables (effectif, lieu sans cuisine, format journée complète).
  - Aucun spectacle vivant n'est prévu dans le brief : aucun récépissé demandé.

7. CALENDRIER ET CRITÈRES DE CHOIX

Date limite de réponse : avant le 15 janvier 2027
Date de décision : 29 janvier 2027

Critères de choix proposés — à valider avec le client avant envoi :
  - Conformité aux besoins exprimés (trois temps, 120 participants, régimes et allergie)
  - Clarté et exhaustivité du devis détaillé (lignes séparées, HT / TVA / TTC)
  - Références sur des événements comparables
  - Organisation proposée face aux contraintes du lieu (absence de cuisine, 2 prises 16 A)
  - Procédure allergènes / sécurité alimentaire, notamment pour l'arachide
  - Assurance et conditions financières, d'annulation et de report

Confidentialité : limiter les données au nécessaire, les pseudonymiser et utiliser uniquement un outil approuvé par la structure.
Le professionnel responsable vérifie les règles applicables.

8. POINTS À CONFIRMER

Données absentes à compléter avant envoi :
  - Coordonnées professionnelles du contact émetteur, date d'envoi et référence de consultation ?
  - Adresse exacte du Domaine Modèle ?
  - Budget (montant et qualification HT ou TTC) ?
  - Contenu attendu pour l'accueil café, le déjeuner assis et le cocktail (format, nombre de pièces, boissons non alcoolisées) ou laisse-t-on le prestataire proposer ?
  - Horaires de livraison, d'installation, de montage, de démontage et d'enlèvement, et heures d'ouverture du lieu ?
  - Accès, stationnement, zone de déchargement, distance jusqu'à l'office ?
  - Mobilier, vaisselle, nappage, matériel de froid disponibles sur place, ou tout à apporter ?
  - Possibilité d'alimentation électrique au-delà des 2 prises 16 A, ou groupe électrogène autorisé ?
  - Espaces et capacités pour chaque temps (café, déjeuner assis, cocktail) ?
  - Répartition exacte des régimes : les 9 végétariens, 3 végans, 2 sans gluten et 1 personne allergique à l'arachide sont-ils 15 personnes distinctes ou certaines relèvent-elles de plusieurs catégories ? La personne allergique à l'arachide a-t-elle un autre régime ? Y a-t-il d'autres allergies non recensées ?

Propositions à valider :
  - Critères de choix proposés ci-dessus : validation avec le client avant envoi.
  - Hypothèse : le prestataire chiffre une solution autonome complète (matériel, vaisselle, froid) faute d'information sur les équipements du lieu — à valider.
  - Hypothèse : le service des vins fournis par le client est demandé en option chiffrée séparément — à valider (qui sert, qui fournit la verrerie, qui met au frais sans cuisine équipée ?).

Vérifications hygiène, allergènes, sécurité et boissons :
  - Confirmer avec le lieu les règles d'hygiène et les conditions d'utilisation de l'office (point d'eau, stockage, déchets).
  - Confirmer la procédure interne pour l'allergie sévère à l'arachide (information du prestataire, identification de la personne de façon non nominative, conduite en cas de réaction).
  - Confirmer les règles du lieu en matière de sécurité (accès, électricité, effectif maximal des espaces).
  - Vérifier les conditions applicables au service des vins fournis par le client dans ce lieu (débit de boissons, autorisation du Domaine, responsabilité du service).
  - Confirmer qu'aucun spectacle vivant n'est prévu ; sinon, vérifier l'exigibilité d'un récépissé de déclaration d'entrepreneur de spectacles et la personne concernée.

