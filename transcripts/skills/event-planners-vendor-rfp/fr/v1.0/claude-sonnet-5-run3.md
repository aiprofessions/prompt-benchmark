# Transcript — skill event-planners-vendor-rfp [fr] — claude-sonnet-5 — run 3

- model_id: `claude-sonnet-5` (provider `anthropic`)
- started_utc: 2026-10-21T07:13:11+00:00
- duration_s: 54.0
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

EN-TÊTE DE LA CONSULTATION
Objet : Appel d'offres — Prestation traiteur — Séminaire annuel Exemple Conseil
Émetteur : [NON FOURNI] — Contact : [NON FOURNI]
Date d'envoi : [NON FOURNI] — Référence : [NON FOURNI]

PRÉSENTATION DE L'ÉVÉNEMENT
Client : Exemple Conseil (fictive)
Nature : Séminaire annuel
Lieu : Domaine Modèle, près de Bordeaux (fictif)
Date : jeudi 10 juin 2027
Participants : 120
Budget : [NON FOURNI]

PÉRIMÈTRE ET BESOINS
- Prestations à consulter :
  - Accueil café : 8h30
  - Déjeuner assis : 12h30
  - Cocktail : 18h00–19h30
- Boissons alcoolisées : exclues de la prestation traiteur. Le client fournit lui-même les vins.
- Régimes et allergies (chiffres exacts du brief, non sommés) :
  - Végétariens : 9
  - Végans : 3
  - Sans gluten : 2
  - Allergie sévère à l'arachide : 1
- Calculs nécessaires :
  - Somme des catégories alimentaires (9 + 3 + 2 + 1) : [NON FOURNI] — chevauchement entre catégories inconnu, l'addition n'est pas effectuée.
  - Nombre de participants sans régime spécifique (120 − somme ci-dessus) : [NON FOURNI], pour la même raison.
- Programme, livraisons, montage et démontage :
  - Programme : accueil café 8h30, déjeuner assis 12h30, cocktail 18h00–19h30 (repris exactement du brief)
  - Horaires de livraison : [NON FOURNI]
  - Horaires de montage : [NON FOURNI]
  - Horaires de démontage : [NON FOURNI]

CONTRAINTES DU LIEU
- Pas de cuisine équipée : un office avec point d'eau et 2 prises 16 A. Le prestataire doit expliquer comment il organise la préparation, le maintien en température et le service de l'accueil café (8h30), du déjeuner (12h30) et du cocktail (18h00–19h30) dans ces conditions, y compris le bilan de puissance électrique compatible avec 2 prises 16 A.
- Accès, stationnement et zones de livraison au Domaine Modèle : [NON FOURNI]. Le prestataire doit indiquer les besoins d'accès qu'il anticipe et attendre confirmation du lieu.
- Accroches autorisées (structures, décor suspendu) : [NON FOURNI].
- Capacités ou équipements nécessaires non précisés par le brief : réfrigération, chambre froide, four, groupe électrogène d'appoint, point d'eau chaude — [NON FOURNI]. Le prestataire précise ses besoins propres et les soumet à validation du lieu.

FORMAT DU DEVIS
Présenter chaque prestation et chaque équipement sur une ligne distincte :
- Accueil café (8h30) — quantité/unité, prix unitaire HT, montant HT
- Déjeuner assis (12h30) — quantité/unité, prix unitaire HT, montant HT
- Cocktail (18h00–19h30) — quantité/unité, prix unitaire HT, montant HT
- Prestations spécifiques régimes/allergie (végétarien, végan, sans gluten, allergie arachide) — lignes séparées si surcoût
- Équipement (vaisselle, mobilier, matériel de maintien en température, etc.) — lignes séparées
- Main-d'œuvre (service, cuisine) — ligne séparée
- Livraison — ligne séparée
- Enlèvement — ligne séparée
- Frais de service — ligne séparée
- Pourboires ou gratifications — ligne séparée
- Boissons alcoolisées : sans objet / exclusion explicite de l'offre (fournies par le client)
- Boissons non alcoolisées (café, eau, softs pour accueil et cocktail) : [NON FOURNI si non demandées explicitement — le prestataire précise ce qui est inclus]

Total HT, TVA par taux avec montant, autres taxes éventuelles, Total TTC — lignes séparées.
Le prestataire indique explicitement tout poste sans objet et toute exclusion de son offre.

DOCUMENTS DEMANDÉS AU PRESTATAIRE
- Attestation d'assurance responsabilité civile professionnelle en cours de validité.
- Procédure écrite de gestion des allergènes et de prévention des contaminations croisées, couvrant la préparation, le transport et le service — à détailler notamment pour l'allergie sévère à l'arachide (1 personne) et les régimes végétarien (9), végan (3) et sans gluten (2).
- Conditions d'acompte, de paiement, d'annulation et de report.
- Spectacle vivant : non mentionné dans ce brief — sans objet, sauf indication contraire de l'organisateur.

CALENDRIER ET CRITÈRES DE CHOIX
Date limite de réponse : 15 janvier 2027
Date de décision : 29 janvier 2027
Critères : [NON FOURNI]
Hypothèse : critères possibles — qualité et faisabilité technique de la prestation sans cuisine équipée, expérience de gestion d'allergies sévères, prix, références événementielles comparables — à valider par l'organisateur avant diffusion.
Confidentialité : limiter les données de participants au nécessaire (effectifs par régime, sans identité), les pseudonymiser et utiliser uniquement un outil approuvé par la structure.
Le professionnel responsable vérifie les règles applicables.

POINTS À CONFIRMER
- Émetteur, contact professionnel, date d'envoi et référence de consultation : à fournir avant diffusion.
- Budget (montant HT ou TTC) : non fourni, à préciser si disponible.
- Horaires de livraison, de montage et de démontage : non fournis, nécessaires pour le chiffrage logistique.
- Accès, stationnement et accroches autorisées au Domaine Modèle : à confirmer avec le lieu.
- Répartition exacte des régimes (chevauchements possibles entre végétariens, végans, sans gluten et l'allergie arachide) : à fournir pour permettre un calcul fiable du nombre de personnes concernées et du nombre sans régime spécifique.
- Boissons non alcoolisées (café, eau, softs) : à confirmer si elles sont incluses dans la prestation traiteur ou gérées séparément.
- Service des vins fournis par le client : à clarifier si le personnel du traiteur assure le service de ces boissons alcoolisées fournies par le client, et si une habilitation ou une autorisation de débit de boissons est nécessaire pour cette tâche — l'organisateur vérifie ce point avec le lieu et les autorités compétentes.
- Critères de choix : non fournis — valider ou amender la proposition formulée en « Hypothèse ».
- Hygiène, sécurité du lieu (Domaine Modèle) et conditions d'intervention de l'office (point d'eau, 2 prises 16 A) : à confirmer avec le lieu avant envoi de l'appel d'offres.
- Capacités et équipements disponibles sur place (réfrigération, four, groupe électrogène) : non précisés, à vérifier avec le Domaine Modèle.
- Spectacle vivant : aucun élément du brief ne l'indique ; si un spectacle vivant devait être ajouté au programme, l'organisateur vérifie la nécessité d'un récépissé de déclaration d'entrepreneur de spectacles et identifie la personne concernée.

