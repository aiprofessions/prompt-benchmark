# Transcript — skill event-planners-vendor-rfp [fr] — claude-fable-5-1 — run 2

- model_id: `claude-fable-5-1` (provider `anthropic`)
- started_utc: 2026-10-21T06:20:13+00:00
- duration_s: 87.8
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

APPEL D'OFFRES — PRESTATION TRAITEUR
Document préparé à partir du brief ; les éléments marqués [NON FOURNI] sont à compléter avant envoi.

1. EN-TÊTE DE LA CONSULTATION

Objet : Appel d'offres — prestation traiteur (accueil café, déjeuner assis, cocktail) — Séminaire annuel Exemple Conseil
Émetteur : Exemple Conseil (fictive) — Contact : [NON FOURNI]
Date d'envoi : [NON FOURNI] — Référence : [NON FOURNI]

2. PRÉSENTATION DE L'ÉVÉNEMENT

Client : Exemple Conseil (société fictive)
Nature : séminaire annuel
Lieu : Domaine Modèle, près de Bordeaux (fictif) — adresse exacte : [NON FOURNI]
Date : jeudi 10 juin 2027
Horaires du programme (reprise exacte du brief) :
  - accueil café : 8h30 (heure de fin [NON FOURNI])
  - déjeuner assis : 12h30 (heure de fin [NON FOURNI])
  - cocktail : 18h00–19h30
Participants : 120
Budget : [NON FOURNI]

3. PÉRIMÈTRE ET BESOINS

Prestations à chiffrer :
  - Accueil café à 8h30 pour 120 participants (contenu attendu : [NON FOURNI] — café, thé, jus, viennoiseries ou autre à préciser par le client).
  - Déjeuner assis à 12h30 pour 120 participants (nombre de services / plats, formule, nombre de tables : [NON FOURNI]).
  - Cocktail de 18h00 à 19h30 pour 120 participants (nombre de pièces par personne, cocktail dînatoire ou apéritif : [NON FOURNI]).
  - Boissons : le client fournit lui-même les vins ; aucune boisson alcoolisée dans la prestation. Boissons non alcoolisées (eaux, softs, café) incluses ou non : [NON FOURNI]. Service des vins du client par le prestataire (ouverture, service, verrerie, droit de bouchon) : [NON FOURNI].
  - Vaisselle, verrerie, nappage, mobilier (tables, chaises, mange-debout), personnel de service : fourni par le lieu ou par le prestataire : [NON FOURNI].

Régimes et allergies (reprise exacte, effectifs non nominatifs) :
  - 9 végétariens
  - 3 végans
  - 2 sans gluten
  - 1 personne avec une allergie sévère à l'arachide
  Le prestataire doit prévoir ces régimes aux trois temps de restauration (accueil café, déjeuner, cocktail) et garantir une identification claire des plats concernés en service.

Programme, livraisons, montage et démontage :
  - Horaires de livraison, de montage et de démontage : [NON FOURNI].
  - Heure de fin de l'accueil café et du déjeuner : [NON FOURNI].
  - Pause-café d'après-midi entre le déjeuner et le cocktail : non mentionnée dans le brief ; à confirmer.

Calculs nécessaires :
  - Total des régimes spécifiques : 9 + 3 + 2 + 1 = 15 si les quatre catégories sont disjointes. Le chevauchement entre catégories est inconnu (ex. un végan peut aussi être sans gluten). Résultat retenu : [NON FOURNI] — répartition demandée en section 8.
  - Nombre de menus standards : 120 − [total régimes spécifiques] = [NON FOURNI] pour la même raison.
  - Puissance électrique disponible en watts : non fournie ; seules les données « 2 prises 16 A » sont connues. Aucune conversion n'est effectuée ; le prestataire indique ses besoins en puissance et vérifie la compatibilité avec le lieu.

4. CONTRAINTES DU LIEU

  - Pas de cuisine équipée : le prestataire doit expliquer son mode de production (cuisine centrale, livraison en liaison froide ou chaude), les moyens de maintien et de remise en température qu'il apporte, et l'organisation du dressage sur place.
  - Un office avec point d'eau : le prestataire doit indiquer si ce point d'eau suffit à son organisation (lavage des mains, plonge éventuelle) et ce qu'il prévoit à défaut.
  - 2 prises 16 A : le prestataire doit lister les équipements électriques qu'il compte brancher, leur puissance, et démontrer que l'ensemble est compatible avec deux prises 16 A ; indiquer toute alternative (groupe électrogène, équipements gaz, etc.) et son coût sur une ligne distincte.
  - Accès, stationnement, quai de livraison, distance entre le point de livraison et l'office / les espaces de service : [NON FOURNI] — le prestataire précisera ses besoins.
  - Espaces disponibles pour le déjeuner assis de 120 personnes et pour le cocktail, surfaces, mobilier existant : [NON FOURNI].
  - Accroches, signalétique, autorisations particulières du lieu : [NON FOURNI].
  - Espace de stockage réfrigéré sur place : [NON FOURNI] — ne pas supposer son existence ; le prestataire prévoit ses propres moyens de froid.

5. FORMAT DU DEVIS

Présenter chaque prestation et chaque équipement sur une ligne distincte :
  - accueil café, déjeuner assis, cocktail, chacun séparément ;
  - menus spécifiques (végétarien, végan, sans gluten, sans arachide) identifiés par ligne si tarifés différemment ;
  - boissons non alcoolisées, si incluses, sur une ligne distincte ;
  - service des vins fournis par le client (verrerie, droit de bouchon le cas échéant) sur une ligne distincte ;
  - chaque matériel : vaisselle, verrerie, nappage, mobilier, équipements de maintien en température, groupe électrogène éventuel.
Pour chaque ligne : désignation, quantité, unité, prix unitaire HT et montant HT.
Séparer également : main-d'œuvre (nombre de personnes, fonctions, horaires, taux), livraison, enlèvement, frais de service.
Présenter les pourboires ou gratifications sur une ligne distincte.
Séparer le total HT, la TVA par taux avec son montant pour chaque taux, les autres taxes éventuelles et le total TTC.
Indiquer explicitement les postes sans objet et les exclusions de l'offre.
Indiquer la durée de validité de l'offre.

6. DOCUMENTS DEMANDÉS AU PRESTATAIRE

  - Attestation d'assurance responsabilité civile professionnelle en cours de validité.
  - Procédure écrite de gestion des allergènes et de prévention des contaminations croisées, couvrant préparation, transport et service, avec le dispositif spécifique prévu pour l'allergie sévère à l'arachide (exclusion de l'arachide, traçabilité des ingrédients, séparation physique, identification en service, consigne au personnel) et pour les régimes végétarien, végan et sans gluten.
  - Description écrite de l'organisation logistique au regard des contraintes du lieu (section 4), avec le plan de production hors site et les besoins électriques.
  - Fiche technique de la prestation : effectifs de personnel par temps de service, horaires d'arrivée et de départ prévus, besoins en accès et stationnement.
  - Conditions d'acompte, de paiement, d'annulation et de report, incluant les délais d'ajustement des effectifs et des régimes.
  - Références de prestations comparables (séminaire, 120 personnes, site sans cuisine).
  - Spectacle vivant : aucun n'est mentionné dans le brief ; aucun récépissé de déclaration d'entrepreneur de spectacles n'est demandé.

7. CALENDRIER ET CRITÈRES DE CHOIX

Date limite de réponse : réponses attendues avant le 15 janvier 2027 (heure limite et inclusion ou non du 15 janvier : [NON FOURNI]).
Date de décision : 29 janvier 2027.
Date de l'événement : jeudi 10 juin 2027.
Visite du lieu avant remise des offres : [NON FOURNI].
Critères : [NON FOURNI].
  Hypothèse (à valider par le client) : qualité et adéquation de la proposition culinaire au programme ; gestion des régimes et de l'allergie sévère à l'arachide ; solidité de l'organisation logistique face aux contraintes du lieu ; prix total TTC et transparence du devis ; références comparables. Pondération à définir par le client.
Confidentialité : limiter les données au nécessaire, les pseudonymiser et utiliser uniquement un outil approuvé par la structure. Aucune identité de participant ne doit figurer dans les échanges avec les prestataires ; seuls les effectifs sont transmis.
Le professionnel responsable vérifie les règles applicables.

8. POINTS À CONFIRMER

Données absentes ou ambiguës :
  - Coordonnées professionnelles de l'émetteur (nom, téléphone, courriel), date d'envoi et référence de consultation ?
  - Adresse exacte du Domaine Modèle ?
  - Budget alloué à la prestation traiteur, en HT ou TTC ?
  - Heures de fin de l'accueil café et du déjeuner ? Pause-café d'après-midi prévue ?
  - Horaires de livraison, de montage et de démontage autorisés par le lieu ?
  - Contenu attendu de l'accueil café, du déjeuner (nombre de plats, formule) et du cocktail (nombre de pièces, apéritif ou dînatoire) ?
  - Boissons non alcoolisées : incluses dans la prestation ou fournies par le client ?
  - Vins fournis par le client : le prestataire doit-il les servir, fournir la verrerie, et un droit de bouchon est-il accepté ? Quantités et conditions de stockage au frais ?
  - Mobilier, vaisselle, nappage : fournis par le lieu, par le client ou à chiffrer par le prestataire ?
  - Accès, stationnement, quai de livraison, distance de portage, ascenseur ou escaliers ?
  - Espaces disponibles pour 120 couverts assis et pour le cocktail ; surfaces ; plan du lieu ?
  - Stockage réfrigéré disponible sur place ?
  - Possibilité d'ajouter de la puissance électrique au-delà des 2 prises 16 A, ou d'utiliser des équipements gaz ou un groupe électrogène ?
  - Visite du lieu possible pour les candidats avant le 15 janvier 2027 ?
  - La date limite « avant le 15 janvier 2027 » inclut-elle le 15 janvier ? À quelle heure ?

Répartition alimentaire :
  - Les catégories 9 végétariens, 3 végans, 2 sans gluten et 1 allergie à l'arachide se chevauchent-elles ? Fournir le nombre exact de participants concernés par au moins un régime et les combinaisons, afin de fixer le nombre de menus standards.
  - Les régimes s'appliquent-ils aux trois temps (café, déjeuner, cocktail) ? Y a-t-il d'autres allergies ou régimes non encore recensés ?

Hypothèses à valider :
  - Critères de choix proposés en section 7 (qualité culinaire, gestion des allergènes, logistique, prix, références) et leur pondération.

Vérifications d'hygiène, d'allergènes, de sécurité et de boissons :
  - Confirmer avec le Domaine Modèle les règles du lieu en matière d'hygiène, d'usage de l'office, d'accroches, de sécurité et d'évacuation pour 120 personnes.
  - Confirmer le dispositif de gestion de l'allergie sévère à l'arachide avec la personne concernée (ou son référent) et avec le prestataire retenu, y compris la conduite à tenir en cas d'incident.
  - Débit de boissons : le client fournit les vins et le prestataire ne vend pas d'alcool ; vérifier avec le lieu et les interlocuteurs compétents si le service d'alcool fourni par le client lors d'un événement privé d'entreprise appelle une démarche ou une autorisation particulière, et qui en est responsable.
  - Spectacle vivant : aucun prévu dans le brief ; confirmer qu'aucune animation (musicien, DJ, artiste) ne sera ajoutée, sinon vérifier l'exigibilité d'un récépissé de déclaration d'entrepreneur de spectacles et la personne concernée.

