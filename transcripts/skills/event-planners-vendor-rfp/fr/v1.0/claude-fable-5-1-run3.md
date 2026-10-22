# Transcript — skill event-planners-vendor-rfp [fr] — claude-fable-5-1 — run 3

- model_id: `claude-fable-5-1` (provider `anthropic`)
- started_utc: 2026-10-21T06:52:19+00:00
- duration_s: 72.1
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

APPEL D'OFFRES — PRESTATION TRAITEUR — SÉMINAIRE ANNUEL EXEMPLE CONSEIL

1. En-tête de la consultation

Objet : Appel d'offres — prestation traiteur (accueil café, déjeuner assis, cocktail) — séminaire annuel de la société Exemple Conseil (fictive)
Émetteur : Exemple Conseil (fictive) — Contact : [NON FOURNI] (nom, fonction, téléphone, courriel professionnels)
Date d'envoi : [NON FOURNI] — Référence : [NON FOURNI]

2. Présentation de l'événement

Client : Exemple Conseil (société fictive)
Nature : séminaire annuel
Lieu : Domaine Modèle, près de Bordeaux (lieu fictif) — adresse exacte : [NON FOURNI]
Date : jeudi 10 juin 2027
Programme fourni : accueil café 8h30 ; déjeuner assis 12h30 ; cocktail 18h00–19h30
Participants : 120
Budget : [NON FOURNI] (montant et qualification HT ou TTC non communiqués)

3. Périmètre et besoins

Prestations à chiffrer (une ligne par prestation) :
  - Accueil café à 8h30 pour 120 participants — contenu attendu (boissons chaudes, viennoiseries, jus, etc.) : [NON FOURNI] ; heure de fin : [NON FOURNI]
  - Déjeuner assis à 12h30 pour 120 participants — nombre de services ou formule (entrée/plat/dessert, fromage, café) : [NON FOURNI] ; heure de fin : [NON FOURNI]
  - Cocktail de 18h00 à 19h30 pour 120 participants — nombre de pièces par personne, pièces salées/sucrées : [NON FOURNI]
  - Boissons : le client fournit lui-même les vins ; aucune boisson alcoolisée n'est incluse dans la prestation. Boissons sans alcool attendues (eaux, softs, boissons chaudes) : [NON FOURNI]. Service des vins fournis par le client (ouverture, service, verrerie, rafraîchissement, droit de bouchon éventuel) : à préciser par le prestataire, voir Format du devis.
  - Équipements et mobilier (tables, chaises, nappage, vaisselle, verrerie, buffets, mange-debout, matériel de maintien en température, groupe froid) : [NON FOURNI] — le prestataire indique ce qu'il fournit, ce qu'il attend du lieu et ce qu'il exclut.
  - Personnel de service (effectif, qualification, horaires) : à proposer et à chiffrer séparément.

Régimes et allergies (reprise exacte du brief) :
  - 9 végétariens
  - 3 végans
  - 2 sans gluten
  - 1 personne avec une allergie sévère à l'arachide
  - Autres allergies ou intolérances : [NON FOURNI]. L'absence d'information ne doit pas être interprétée comme une absence d'autres allergies.
  - Le prestataire propose, pour chacune des trois prestations, une offre adaptée à chaque régime et précise comment les plats concernés sont identifiés et servis aux bonnes personnes.

Programme, livraisons, montage et démontage :
  - Horaires de livraison : [NON FOURNI]
  - Horaires de montage : [NON FOURNI]
  - Horaires de démontage et d'enlèvement : [NON FOURNI]
  - Heure d'accès au lieu et heure limite de libération : [NON FOURNI]
  - Le prestataire propose un planning de livraison, montage, service et démontage compatible avec les trois temps du programme (8h30, 12h30, 18h00–19h30).

Calculs nécessaires :
  - Durée du cocktail : 19h30 − 18h00 = 1 h 30
  - Effectif sans régime particulier : [NON FOURNI]. Les catégories 9 végétariens, 3 végans, 2 sans gluten et 1 allergie arachide peuvent se recouper (ex. une personne végane et sans gluten) ; le chevauchement n'étant pas indiqué, aucune addition ni soustraction n'est faite. Répartition exacte demandée en Points à confirmer.
  - Durées de l'accueil café et du déjeuner : non calculables, heures de fin [NON FOURNI].

4. Contraintes du lieu

  - Pas de cuisine équipée : le prestataire doit expliquer comment son offre est réalisable sans cuisine sur place (préparation en laboratoire, transport en liaison froide ou chaude, maintien en température, remise en température, dressage sur place) pour un déjeuner assis de 120 couverts et un cocktail de 120 personnes.
  - Un office avec point d'eau : le prestataire doit indiquer si ce point d'eau unique suffit pour sa prestation (plonge, lavage des mains, préparation) et, à défaut, ce qu'il apporte en complément.
  - 2 prises 16 A : le prestataire doit lister tous ses équipements électriques avec leur puissance, démontrer que la somme des puissances est compatible avec 2 prises 16 A, et préciser s'il a besoin d'une alimentation complémentaire ou d'un groupe électrogène (à chiffrer séparément). Tension, circuits distincts ou non, protection : [NON FOURNI].
  - Accès véhicules, zone de livraison, hauteur et largeur de passage : [NON FOURNI] — le prestataire précise ses besoins.
  - Stationnement des véhicules du prestataire : [NON FOURNI]
  - Accroches ou fixations autorisées : [NON FOURNI] — aucune fixation n'est présumée autorisée.
  - Mobilier, vaisselle, verrerie et matériel mis à disposition par le lieu : [NON FOURNI] — aucun équipement du lieu n'est présumé disponible.
  - Surface, configuration et capacité des espaces (salle de déjeuner pour 120 assis, espace cocktail, espace accueil café, intérieur/extérieur, repli en cas de pluie) : [NON FOURNI]
  - Gestion des déchets et évacuation : [NON FOURNI]
  - Dispositif de froid sur place (chambre froide, réfrigérateurs) : [NON FOURNI] — le prestataire prévoit son propre froid sauf confirmation contraire.

5. Format du devis

Présenter chaque prestation et chaque équipement sur une ligne distincte : accueil café, déjeuner assis, cocktail, boissons sans alcool, menus adaptés par régime (végétarien, végan, sans gluten, sans arachide), mobilier, vaisselle, verrerie, nappage, matériel de maintien ou remise en température, matériel électrique, alimentation électrique complémentaire éventuelle.
Pour chaque ligne : désignation, quantité, unité, prix unitaire HT et montant HT.
Séparer également sur des lignes distinctes : main-d'œuvre (par poste, effectif, nombre d'heures, taux horaire, majorations éventuelles), livraison, enlèvement, frais de service.
Présenter les pourboires ou gratifications sur une ligne distincte.
Présenter sur une ligne distincte le service des vins fournis par le client (droit de bouchon ou frais de service) ou indiquer qu'il est sans objet.
Séparer le total HT, la TVA par taux avec le montant correspondant à chaque taux, les autres taxes éventuelles, et le total TTC.
Préciser la base de facturation (forfait ou par personne), le seuil et le délai de confirmation du nombre définitif de convives, et les conditions de facturation des variations d'effectif.
Indiquer explicitement les postes sans objet et les exclusions de l'offre (ce qui est attendu du lieu ou du client).
Durée de validité de l'offre : à indiquer.

6. Documents demandés au prestataire

  - Attestation d'assurance responsabilité civile professionnelle en cours de validité.
  - Procédure écrite de gestion des allergènes et de prévention des contaminations croisées, couvrant préparation, transport, stockage sur place et service, avec un volet spécifique à l'allergie sévère à l'arachide (séparation des préparations, matériel dédié, identification des plats, consigne au personnel de service, mesures en cas d'incident) et aux régimes végétarien, végan et sans gluten.
  - Description de l'organisation hygiène et chaîne du froid/chaud dans un lieu sans cuisine équipée (moyens de transport, enregistrement des températures).
  - Conditions d'acompte, de paiement, d'annulation et de report, avec les échéances et les pénalités éventuelles.
  - Conditions générales de vente.
  - Références de prestations comparables (séminaire, 100 à 150 personnes, lieu sans cuisine) : à fournir si disponibles.
  - Spectacle vivant : aucun n'est mentionné dans le brief ; aucun récépissé n'est demandé à ce stade.

7. Calendrier et critères de choix

Date limite de réponse : avant le 15 janvier 2027 (heure limite : [NON FOURNI])
Date de décision : 29 janvier 2027
Visite du lieu avant remise de l'offre : [NON FOURNI]
Critères : [NON FOURNI]
  Hypothèse : notation sur le prix total HT, l'adéquation de la proposition aux contraintes du lieu (absence de cuisine, 2 prises 16 A), la qualité et la variété des menus y compris régimes spéciaux, la robustesse de la procédure allergènes, les références et moyens humains — pondération à définir par le client.
Confidentialité : limiter les données au nécessaire, les pseudonymiser et utiliser uniquement un outil approuvé par la structure.
Le professionnel responsable vérifie les règles applicables.

8. Points à confirmer

Données absentes du brief :
  - Coordonnées de l'émetteur (nom, fonction, téléphone, courriel) ; date d'envoi ; référence de consultation.
  - Adresse exacte du Domaine Modèle et nom du contact sur place.
  - Budget : montant et qualification HT ou TTC ? Budget global ou par prestation ?
  - Heures de fin de l'accueil café et du déjeuner ; horaires de livraison, de montage, de démontage et d'enlèvement ; heure d'accès au lieu et heure limite de libération.
  - Contenu attendu pour l'accueil café, le déjeuner (nombre de services, café inclus ?) et le cocktail (nombre de pièces par personne) ; boissons sans alcool attendues.
  - Mobilier, vaisselle, verrerie et nappage : fournis par le lieu, par le prestataire ou par le client ?
  - Qui assure le service des vins fournis par le client (prestataire ou client) ? Verrerie fournie par qui ? Les vins sont-ils servis au déjeuner, au cocktail, ou aux deux ?
  - Critères de choix et pondération ; validation ou modification de l'hypothèse proposée.
  - Heure limite précise de remise des offres le 15 janvier 2027 et modalités d'envoi.
  - Visite du lieu possible pour les candidats ?

Chevauchement des régimes :
  - Les 9 végétariens, 3 végans, 2 sans gluten et 1 allergie arachide sont-ils des personnes distinctes ou certaines cumulent-elles plusieurs régimes ? Fournir la répartition exacte afin de déterminer le nombre de menus standard et de menus adaptés.
  - Existe-t-il d'autres allergies, intolérances ou régimes (religieux, sans lactose, etc.) non recensés ? La collecte des régimes est-elle terminée ?
  - La personne allergique à l'arachide est-elle présente aux trois temps (café, déjeuner, cocktail) ?

Contraintes du lieu à confirmer avec le Domaine Modèle :
  - Caractéristiques des 2 prises 16 A (circuits distincts, puissance totale disponible) ; possibilité d'alimentation complémentaire ou de groupe électrogène.
  - Accès véhicules, zone de livraison, stationnement, accroches autorisées, surfaces et configuration des espaces, solution de repli en cas d'intempéries, espace froid disponible, évacuation des déchets.
  - Règles du lieu en matière d'hygiène et de sécurité (plan d'évacuation, capacité maximale des salles, interdictions) et contraintes horaires éventuelles (voisinage, bruit).

Hygiène, allergènes, sécurité et boissons :
  - Confirmer avec le lieu et le prestataire l'organisation d'hygiène dans un espace sans cuisine équipée (chaîne du froid, remise en température, plonge).
  - Valider la procédure allergènes du prestataire retenu, en particulier pour l'allergie sévère à l'arachide, et définir la consigne au personnel de service.
  - Débit de boissons : le client fournit lui-même les vins ; vérifier avec le lieu et les interlocuteurs compétents les conditions de service d'alcool sur place (autorisation du lieu, responsabilité, licence éventuelle) et qui en est responsable.
  - Spectacle vivant : confirmer qu'aucune animation ou spectacle vivant n'est prévu ; dans le cas contraire, vérifier si un récépissé de déclaration d'entrepreneur de spectacles est exigible et qui doit le fournir.

