# Transcript — skill interior-designers-ffe-schedule [fr] — claude-fable-5-1 — run 1

- model_id: `claude-fable-5-1` (provider `anthropic`)
- started_utc: 2026-10-21T05:49:51+00:00
- duration_s: 112.4
- exit_code: 0
- attempts: 1
- completed: True
- rubric_sha256: ea7c361bc780b7b113a5f39623e158f7a87c25e44e9a3912575f3a40925b201a
- skill_sha256: d8d0799b051c268d42c5fb63acd6f1044427b10cb11abed7a63aef253fb18f6a

## Query (verbatim, from query file)

````text
<skill_instructions>
---
name: interior-designers-ffe-schedule
description: "Utilisez-la quand vous collez le brief d'une pièce pour obtenir une liste de mobilier et d'équipements avec dimensions, enveloppes budgétaires et délais à vérifier."
---

# Du brief client à la liste de mobilier et d'équipements

## Ce qu'elle fait

Elle transforme un brief en liste de mobilier et d'équipements pour un projet en France. Elle couvre les éléments demandés et l'existant à réemployer, avec dimensions, exigences d'usage, enveloppes budgétaires et délais à vérifier. Elle prépare un document de travail à valider par l'architecte d'intérieur ou le décorateur, sans inventer de produits ni de prix.

## Ce dont elle a besoin

- Dimensions de la pièce, ouvertures, accès et contraintes de circulation.
- Éléments souhaités, quantités et dimensions imposées.
- Occupants, usages et présence d'animaux, sans données personnelles inutiles.
- Goûts et refus : couleurs, matières, formes et styles.
- Budget total, mention HT ou TTC et périmètre : fourniture, livraison, pose.
- Date de pose, date de référence pour le contrôle des délais, délais fournisseurs et temps de préparation connus.
- Existant à conserver, réemployer ou retirer, avec dimensions et interventions prévues.
- Type de projet : logement ou établissement recevant du public (ERP).

Les données manquantes sont signalées par [NON FOURNI] et les propositions par « Hypothèse : … ». Ne jamais deviner une donnée client ; poursuivre la rédaction et regrouper les questions à la fin.

## Procédure

1. Livrer toutes les rubriques dès la première réponse, sans poser de question préalable ni attendre de confirmation. Ne retenir aucune section ni aucun calcul : si un calcul est impossible, en donner la formule et les données manquantes. Employer [NON FOURNI] ou une hypothèse raisonnable explicitement étiquetée « Hypothèse : … ». Regrouper toutes les questions dans la dernière rubrique.
2. Recopier exactement chaque chiffre, date, heure, quantité et montant du brief, avec son unité et sa présentation. Conserver les valeurs contradictoires en signalant le conflit. Montrer l'arithmétique de chaque valeur dérivée ; toute conversion conserve aussi la valeur d'origine.
3. Insérer une seule ligne de rappel : « Pseudonymisez les données client et utilisez uniquement un outil approuvé par l'agence. » Ne jamais refuser ni suspendre la rédaction pour ce motif.
4. Établir un inventaire de chaque élément demandé et de chaque pièce existante. Attribuer un repère unique à chaque ligne ; distinguer quantité d'objets et nombre de lignes. Vérifier la correspondance entre chaque demande et son repère, sans omission. Un élément à retirer reste identifié comme hors achat.
5. Marquer les éléments à acquérir « Neuf » et les pièces conservées « Existant – réemploi ». Pour le réemploi, reprendre dimensions et interventions connues ; sinon écrire [NON FOURNI]. Ne pas supposer un coût nul : distinguer absence d'achat et frais de nettoyage, adaptation, transport ou pose à confirmer.
6. Recopier tous les refus sous « Exclusions appliquées » dans « Intention », avec leur application concrète. Reporter chaque exclusion dans les lignes concernées. En cas de demande incompatible avec un refus, conserver la ligne mais signaler l'arbitrage nécessaire, sans proposer l'option refusée.
7. Donner une dimension cible par ligne, fournie ou calculée. Pour un tapis, calculer séparément longueur et largeur : dimension de la pièce − dégagement de chaque côté. Étiqueter tout dégagement proposé comme hypothèse. Pour les autres éléments, expliciter les paramètres nécessaires ; ne pas déduire une table du seul nombre de places sans hypothèses dimensionnelles. Faire vérifier circulation, ouvertures et accès.
8. Relier les occupants et animaux aux exigences des lignes concernées : entretien facilité, tissu déhoussable, angles arrondis, stabilité ou résistance à l'usage. Écrire « exigence à vérifier », jamais une promesse de performance ou une propriété acquise d'un produit.
9. Reprendre le budget total du client et son périmètre. Chaque montant porte HT ou TTC ; si cette information manque, conserver le montant et ajouter [HT/TTC NON PRÉCISÉ], sans choisir ni convertir la base. Ne jamais additionner des bases incompatibles.
10. Nommer chaque allocation « enveloppe estimative à confirmer par devis ». Si une répartition est proposée, l'étiqueter comme hypothèse, sans la présenter comme un prix de marché. Montrer la somme, puis l'écart = budget client − total des enveloppes. Si des coûts manquent, calculer le sous-total connu et préciser que le solde n'est pas une marge disponible. Ne jamais inventer prix de produit, marque, nom de modèle ou référence.
11. Pour chaque ligne neuve, contrôler la commande au plus tard : date de pose − délai fournisseur − préparation prévue, en montrant le calcul. Préciser les unités et le traitement des jours ouvrés si nécessaire ; ne pas les supposer. Si un délai manque, écrire [NON FOURNI], sans inventer de date de commande. Pour le réemploi, contrôler les délais d'intervention. Comparer aux dates de référence fournies ; sinon signaler que le retard éventuel ne peut pas être évalué.
12. Lister par repère les caractéristiques pertinentes à vérifier dans les données du fabricant : réaction au feu, abrasion avec méthode et unité (cycles Martindale ou doubles frottements, sans équivalence supposée), codes ou consignes d'entretien, résistance au glissement. Ajouter stabilité et fixations si pertinentes. Ne présenter aucun classement ni aucune valeur comme acquis ; un résultat fourni reste à valider sur sa documentation.
13. Ne citer dans la sortie aucune loi, aucun article, aucune recommandation d'autorité, aucune jurisprudence ni aucune source absente du brief. Une mention imposée à reproduire est du contenu, pas une citation. Ne compléter aucune référence de mémoire. La ligne de limites de la sortie dit seulement : « Le professionnel responsable vérifie les règles applicables. »
14. Contrôler la présence de toutes les colonnes et des six rubriques ci-dessous. Terminer par « Questions pour le client », en y regroupant tous les manques, hypothèses et arbitrages, y compris ceux concernant budget et délais. Ne rien ajouter après cette rubrique.

## Format de sortie

```
## Intention
- Pièce, dimensions, occupants, usages et type de projet : [...]
- Autres données du brief à conserver : [...]
- Exclusions appliquées : [chaque refus → application concrète]
- Pseudonymisez les données client et utilisez uniquement un outil approuvé par l'agence.

## Liste mobilier et équipements
| Repère | Élément | Quantité | Dimensions cibles et calculs | Matériaux / exigences à vérifier | Enveloppe estimative à confirmer par devis (HT/TTC) | Délai / commande au plus tard | Statut |
|---|---|---|---|---|---|---|---|
| [...] | [...] | [...] | [...] | [...] | [...] | [...] | Neuf / Existant – réemploi |
- Rapprochement : [chaque élément demandé ou existant → repère ; retraits hors achat identifiés]

## Contrôle du budget
- Budget client et périmètre : [...]
- Hypothèses de répartition : [...]
- Total ou sous-total connu : [calcul avec base HT/TTC]
- Écart ou solde provisoire : [calcul ; coûts restant à confirmer]
- Les enveloppes sont estimatives, à confirmer par devis.

## Contrôle des délais
- Date de pose et date de référence : [...]
- Par repère : [délais, calcul de commande ou d'intervention, données manquantes]
- Risques : [retard établi / échéance à confirmer / évaluation impossible]

## Caractéristiques à vérifier
- Par repère : [caractéristiques pertinentes et données fabricant à contrôler]
- Le professionnel responsable vérifie les règles applicables.

## Questions pour le client
- [Tous les manques, hypothèses et arbitrages à confirmer]
```

## Limites

- Périmètre : France uniquement ; ne pas transposer cette liste à la Belgique, à la Suisse ou au Canada.
- Ne jamais inventer de produit, prix, disponibilité, résultat d'essai, statistique ou référence réglementaire. Une enveloppe proposée n'est pas un devis.
- Le professionnel responsable vérifie les relevés, les accès, la circulation, les fixations, les dimensions finales, les devis et les engagements de livraison avant commande.
- Les exigences de réaction au feu et de sécurité dépendent du type de projet, notamment logement ou ERP : l'architecte d'intérieur les confirme, avec les justificatifs fabricant pertinents.
- Chaque montant doit porter HT ou TTC ; une base inconnue reste explicitement signalée et doit être confirmée avant validation.
- Aucune source officielle propre à l'usage de l'IA n'a été vérifiée pour les architectes d'intérieur. Le professionnel se renseigne auprès de son organisation professionnelle ou de l'autorité compétente ; cette indication lui est destinée, pas à ajouter comme citation dans la sortie.
- Confidentialité : pseudonymiser le brief, retirer les données identifiantes inutiles et utiliser uniquement un outil approuvé par l'agence. Ce rappel ne bloque pas la rédaction.
- voir references/checklist.md

## Exemple

Entrée fictive :
```
Projet Exemple, logement : tapis pour une pièce de 4 × 3 m, dégagement de 0,50 m sur chaque côté.
Demandes : 1 tapis ; conserver 1 chaise Modèle de 40 × 40 cm, sans intervention ni frais.
Un chat ; exclure le velours. Enveloppes client : tapis 600 € TTC ; chaise 0 € TTC.
Budget total 600 € TTC, fourniture seule ; date de pose et délais non fournis.
```

Sortie abrégée :
```
## Intention
Logement Exemple, pièce de 4 × 3 m, un chat ; velours exclu des deux lignes. Pseudonymisez les données client et utilisez uniquement un outil approuvé par l'agence.
## Liste mobilier et équipements
| Repère | Élément | Quantité | Dimensions cibles et calculs | Exigences à vérifier | Enveloppe estimative à confirmer par devis | Délai / commande | Statut |
|---|---|---|---|---|---|---|---|
| TAP-01 | Tapis | 1 | 4 − 2 × 0,50 = 3 m ; 3 − 2 × 0,50 = 2 m | Sans velours ; entretien adapté au chat à vérifier | 600 € TTC | [NON FOURNI] | Neuf |
| MOB-01 | Chaise Modèle | 1 | 40 × 40 cm | Absence de velours à vérifier ; sans intervention ni frais | 0 € TTC | Sans intervention | Existant – réemploi |
## Contrôle du budget
Budget : 600 € TTC, fourniture seule ; enveloppes : 600 € TTC + 0 € TTC = 600 € TTC ; écart : 600 € TTC − 600 € TTC = 0 € TTC.
## Contrôle des délais
Pose, délai fournisseur et date de référence : [NON FOURNI] ; commande = pose − délai − préparation éventuelle, calcul impossible.
## Caractéristiques à vérifier
TAP-01 : entretien, abrasion, glissement, réaction au feu selon pertinence ; MOB-01 : matériau et stabilité, sur documentation fabricant. Le professionnel responsable vérifie les règles applicables.
## Questions pour le client
Quelles sont la date de pose, la date de référence, le délai fournisseur et la préparation éventuelle ? Confirmez-vous les enveloppes et l'absence de velours sur la chaise ?
```
</skill_instructions>

Follow the skill instructions above for the user's request below.

User request:
Prépare la liste mobilier et équipements de cette pièce.
Client : famille Exemple (fictive), Bordeaux. Pièce : séjour de 4,2 m × 5,5 m, hauteur 2,60 m, une baie vitrée de 2,4 m de large.
Éléments souhaités : canapé d'angle 5 places ; tapis laissant 30 cm de sol visible de chaque côté ; table basse ; 2 fauteuils ; 2 lampadaires ; rideaux pour la baie.
Existant : bibliothèque en chêne — à conserver.
Occupants : un couple, un enfant de 3 ans et un chien qui perd ses poils.
Aime : bois clair, tons sable. N'aime pas : le verre, le cuir.
Budget : 22 000 € TTC, livraison et installation comprises. Installation : 15 avril 2027. Délai de fabrication du canapé annoncé par nos fournisseurs : 8 à 10 semaines.
````

## Output (verbatim stdout, session metadata stripped)

## Intention
- Pièce, dimensions, occupants, usages et type de projet : séjour de 4,2 m × 5,5 m, hauteur 2,60 m, une baie vitrée de 2,4 m de large ; un couple, un enfant de 3 ans, un chien qui perd ses poils ; usage séjour (détail des usages [NON FOURNI]) ; type de projet : Hypothèse : logement (famille), à confirmer.
- Autres données du brief à conserver : client famille Exemple (fictive), Bordeaux ; budget 22 000 € TTC, livraison et installation comprises ; installation le 15 avril 2027 ; délai de fabrication du canapé annoncé par nos fournisseurs : 8 à 10 semaines ; goûts : bois clair, tons sable ; existant : bibliothèque en chêne à conserver ; date de référence pour le contrôle des délais [NON FOURNI].
- Exclusions appliquées :
  - Verre refusé → TAB-01 sans plateau ni pieds en verre ; LAM-01 sans diffuseur, abat-jour ou socle en verre apparent (ampoules : arbitrage à confirmer) ; aucune étagère ou porte en verre ajoutée sur BIB-01. La baie vitrée existante n'est pas concernée (hors achat).
  - Cuir refusé → CAN-01 et FAU-01 en tissu, sans cuir ni simili cuir ; aucune poignée ou détail cuir sur les autres lignes.
- Pseudonymisez les données client et utilisez uniquement un outil approuvé par l'agence.

## Liste mobilier et équipements

Colonnes : Repère | Élément | Quantité | Dimensions cibles et calculs | Matériaux / exigences à vérifier | Enveloppe estimative à confirmer par devis (HT/TTC) | Délai / commande au plus tard | Statut

CAN-01 | Canapé d'angle 5 places | 1
  Dimensions : [NON FOURNI]. Ne peut pas être déduit des seules 5 places. Paramètres à fixer : largeur d'assise par place, profondeur totale, sens de l'angle (gauche/droite), implantation face à la baie ou au mur, dégagement de passage conservé devant la baie de 2,4 m. Hypothèse pour la circulation : passage libre ≥ 0,80 m entre canapé et autres éléments, à vérifier.
  Exigences : tissu sans cuir ; déhoussable et lavable (chien, enfant) → exigence à vérifier ; bois clair / tons sable souhaités ; résistance à l'abrasion → exigence à vérifier ; accès (escalier, ascenseur, portes) pour un canapé d'angle → à vérifier.
  Enveloppe : Hypothèse : 7 000 € TTC, enveloppe estimative à confirmer par devis.
  Délai : fabrication 8 à 10 semaines (fournisseurs). Commande au plus tard = 15 avril 2027 − 10 semaines − préparation. Voir Contrôle des délais.
  Statut : Neuf

TAP-01 | Tapis | 1
  Dimensions : 30 cm (0,30 m) de sol visible de chaque côté. Longueur : 5,5 − 2 × 0,30 = 4,9 m. Largeur : 4,2 − 2 × 0,30 = 3,6 m. Cible : 4,9 m × 3,6 m. Format non standard, fabrication sur mesure ou assemblage probable → à vérifier. Arbitrage : le brief parle de la pièce entière ; si le dégagement s'entend autour de la zone canapé, ou si le tapis doit s'arrêter devant la bibliothèque BIB-01 (position [NON FOURNI]), les dimensions changent.
  Exigences : poils de chien → aspiration facile, fibres non piégeantes, entretien → exigence à vérifier ; enfant → antidérapant / sous-tapis → exigence à vérifier ; tons sable ; sans velours imposé par le brief ? [NON FOURNI] ; poids et accès pour un tapis de 4,9 × 3,6 m → à vérifier.
  Enveloppe : Hypothèse : 3 000 € TTC, enveloppe estimative à confirmer par devis.
  Délai : délai fournisseur [NON FOURNI] ; commande au plus tard = 15 avril 2027 − délai − préparation, calcul impossible.
  Statut : Neuf

TAB-01 | Table basse | 1
  Dimensions : [NON FOURNI]. Paramètres : profondeur d'assise du canapé CAN-01, dégagement souhaité canapé–table (Hypothèse : 0,40 à 0,45 m, à confirmer), hauteur compatible avec l'assise du canapé.
  Exigences : sans verre ; angles arrondis (enfant de 3 ans) → exigence à vérifier ; stabilité → exigence à vérifier ; bois clair souhaité ; surface résistante aux taches et nettoyable → exigence à vérifier.
  Enveloppe : Hypothèse : 1 500 € TTC, enveloppe estimative à confirmer par devis.
  Délai : [NON FOURNI] ; calcul impossible.
  Statut : Neuf

FAU-01 | Fauteuil | 2
  Dimensions : [NON FOURNI]. Paramètres : encombrement unitaire, implantation par rapport à CAN-01 et TAB-01, passage conservé vers la baie et vers BIB-01.
  Exigences : tissu sans cuir ; déhoussable / nettoyable (chien) → exigence à vérifier ; stabilité (enfant) → exigence à vérifier ; bois clair / tons sable.
  Enveloppe : Hypothèse : 2 × 1 500 = 3 000 € TTC, enveloppe estimative à confirmer par devis.
  Délai : [NON FOURNI] ; calcul impossible.
  Statut : Neuf

LAM-01 | Lampadaire | 2
  Dimensions : [NON FOURNI]. Paramètres : hauteur sous plafond 2,60 m (hauteur maximale du lampadaire à rester nettement en dessous), emplacement des prises [NON FOURNI], position près de CAN-01 / FAU-01.
  Exigences : sans verre apparent (arbitrage ampoules) ; socle lesté et stabilité au basculement (enfant, chien) → exigence à vérifier ; câble sans passage dans la circulation → à vérifier ; bois clair / tons sable.
  Enveloppe : Hypothèse : 2 × 600 = 1 200 € TTC, enveloppe estimative à confirmer par devis.
  Délai : [NON FOURNI] ; calcul impossible.
  Statut : Neuf

RID-01 | Rideaux pour la baie | 1 ensemble (nombre de panneaux : Hypothèse : 2)
  Dimensions : baie 2,4 m de large ; hauteur de la baie, hauteur de fixation et type de pose (tringle, rail, plafond) [NON FOURNI]. Largeur de tissu = (2,4 + 2 × débord) × coefficient d'ampleur. Hypothèse : débord 0,20 m de chaque côté et ampleur 2 → (2,4 + 0,4) × 2 = 5,6 m de tissu fini. Hauteur = hauteur de fixation − garde au sol, non calculable (données manquantes ; plafond à 2,60 m comme borne haute).
  Exigences : tissu lavable (poils de chien) → exigence à vérifier ; cordons ou chaînettes hors de portée de l'enfant → exigence à vérifier ; occultation ou tamisage souhaité [NON FOURNI] ; tons sable ; fixation de la tringle/rail sur le support existant → à vérifier.
  Enveloppe : Hypothèse : 2 500 € TTC (confection, tringlerie et pose), enveloppe estimative à confirmer par devis.
  Délai : confection et pose [NON FOURNI] ; calcul impossible.
  Statut : Neuf

BIB-01 | Bibliothèque en chêne | 1
  Dimensions : [NON FOURNI] (L × P × H). Position dans la pièce [NON FOURNI]. Influe sur TAP-01 et sur la circulation.
  Exigences : interventions prévues [NON FOURNI] (nettoyage, déplacement, rénovation, adaptation) ; fixation murale anti-basculement (enfant de 3 ans) → exigence à vérifier ; aucune adaptation en verre ou en cuir.
  Enveloppe : hors achat. Frais de nettoyage, déplacement, adaptation ou fixation : [NON FOURNI] (coût nul non supposé).
  Délai : délai d'intervention [NON FOURNI] ; à caler avant le 15 avril 2027 si la bibliothèque doit être déplacée ou fixée.
  Statut : Existant – réemploi

LIV-01 | Provision livraison et installation (toutes lignes neuves) | 1
  Dimensions : sans objet ; accès (étage, ascenseur, largeur de porte) [NON FOURNI].
  Exigences : à répartir par fournisseur selon les devis.
  Enveloppe : Hypothèse : 2 000 € TTC, enveloppe estimative à confirmer par devis.
  Délai : 15 avril 2027 (date de pose).
  Statut : Neuf (prestation)

- Rapprochement : canapé d'angle 5 places → CAN-01 ; tapis → TAP-01 ; table basse → TAB-01 ; 2 fauteuils → FAU-01 (2 objets, 1 ligne) ; 2 lampadaires → LAM-01 (2 objets, 1 ligne) ; rideaux pour la baie → RID-01 ; bibliothèque en chêne → BIB-01 (réemploi) ; livraison/installation → LIV-01. Aucun retrait demandé. 7 lignes d'éléments + 1 ligne de prestation ; 10 objets (1 + 1 + 1 + 2 + 2 + 1 ensemble + 1 + prestation).

## Contrôle du budget
- Budget client et périmètre : 22 000 € TTC, livraison et installation comprises (fourniture + livraison + pose).
- Hypothèses de répartition (toutes « Hypothèse », aucune n'est un prix de marché) : CAN-01 7 000 € TTC ; TAP-01 3 000 € TTC ; TAB-01 1 500 € TTC ; FAU-01 3 000 € TTC ; LAM-01 1 200 € TTC ; RID-01 2 500 € TTC ; LIV-01 2 000 € TTC ; BIB-01 [NON FOURNI].
- Total ou sous-total connu : 7 000 + 3 000 + 1 500 + 3 000 + 1 200 + 2 500 + 2 000 = 20 200 € TTC (sous-total, base TTC homogène).
- Écart ou solde provisoire : 22 000 € TTC − 20 200 € TTC = 1 800 € TTC. Ce solde n'est pas une marge disponible : frais BIB-01 non chiffrés, tapis 4,9 × 3,6 m potentiellement sur mesure, accès et livraison d'un canapé d'angle non évalués.
- Les enveloppes sont estimatives, à confirmer par devis.

## Contrôle des délais
- Date de pose et date de référence : pose le 15 avril 2027 ; date de référence [NON FOURNI] ; temps de préparation (réception, contrôle, stockage) [NON FOURNI].
- Par repère :
  - CAN-01 : délai 8 à 10 semaines, lues comme semaines calendaires (7 jours) — à confirmer si semaines ouvrées. Sans préparation : 15 avril 2027 − 10 semaines (70 jours) = 4 février 2027 ; 15 avril 2027 − 8 semaines (56 jours) = 18 février 2027. Commande au plus tard = 4 février 2027 − préparation [NON FOURNI], donc avant le 4 février 2027 sur l'hypothèse haute.
  - TAP-01, TAB-01, FAU-01, LAM-01, RID-01 : délai fournisseur [NON FOURNI] ; commande au plus tard = 15 avril 2027 − délai − préparation, calcul impossible.
  - BIB-01 : interventions et délais [NON FOURNI] ; à planifier avant le 15 avril 2027.
  - LIV-01 : planning de livraison et pose à caler sur le 15 avril 2027, séquence (tapis avant mobilier, rideaux après) à confirmer.
- Risques : CAN-01 échéance à confirmer (le 4 février 2027 n'est comparable à aucune date de référence fournie, le retard éventuel ne peut pas être évalué) ; autres lignes : évaluation impossible, délais manquants.

## Caractéristiques à vérifier
- CAN-01 / FAU-01 : composition du tissu (absence de cuir), abrasion avec méthode et unité (cycles Martindale ou doubles frottements, sans équivalence supposée), codes d'entretien et déhoussage, réaction au feu selon le type de projet, stabilité de la structure, sur documentation fabricant.
- TAP-01 : composition, entretien et aspiration, résistance au glissement / sous-tapis, réaction au feu selon pertinence, poids et conditionnement pour l'accès.
- TAB-01 : matériau du plateau (hors verre), rayon des angles, stabilité au renversement, résistance aux taches et à l'eau, sur documentation fabricant.
- LAM-01 : matériaux hors verre apparent, poids et surface du socle, stabilité au basculement, compatibilité électrique, sur documentation fabricant.
- RID-01 : composition, codes d'entretien et lavage, réaction au feu selon pertinence, charge et fixation de la tringle/rail, sécurité des cordons.
- BIB-01 : état, dispositif de fixation murale et nature du mur support, charge des étagères.
- Le professionnel responsable vérifie les règles applicables.

## Questions pour le client
- Confirmez-vous que le projet est un logement (famille) et non un ERP ?
- Tapis : le dégagement de 30 cm s'entend-il autour de la pièce entière (soit 4,9 m × 3,6 m) ou autour de la zone canapé ? Le tapis doit-il passer sous la bibliothèque ou s'arrêter devant ?
- Bibliothèque : dimensions (L × P × H), position actuelle et future dans la pièce, interventions prévues (déplacement, nettoyage, fixation murale) et frais associés ?
- Canapé : sens de l'angle, profondeur et largeur d'assise souhaitées, implantation par rapport à la baie ? Accès au logement (étage, ascenseur, largeur de porte) ?
- Rideaux : hauteur de la baie, type de pose (tringle, rail, plafond), hauteur de fixation, débord et ampleur souhaités, tamisant ou occultant ? Nombre de panneaux (hypothèse : 2) ?
- Lampadaires : emplacement des prises électriques ? Les ampoules en verre sont-elles acceptées malgré le refus du verre ?
- Table basse : dimensions ou hauteur imposées ? Dégagement canapé–table de 0,40 à 0,45 m acceptable ?
- Budget : validez-vous la répartition hypothétique (20 200 € TTC) et le solde provisoire de 1 800 € TTC, sachant que les frais de la bibliothèque ne sont pas chiffrés ?
- Délais : date de référence pour le contrôle ? Les 8 à 10 semaines du canapé sont-elles calendaires ou ouvrées ? Temps de préparation prévu après réception ? Délais fournisseurs pour tapis, table basse, fauteuils, lampadaires et rideaux ?
- Exclusions : le refus du velours ou d'autres matières s'ajoute-t-il au verre et au cuir ? Le simili cuir est-il également exclu ?

