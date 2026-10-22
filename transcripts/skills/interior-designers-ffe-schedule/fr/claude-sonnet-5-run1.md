# Transcript — skill interior-designers-ffe-schedule [fr] — claude-sonnet-5 — run 1

- model_id: `claude-sonnet-5` (provider `anthropic`)
- started_utc: 2026-10-21T06:12:43+00:00
- duration_s: 113.6
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
- Pièce : séjour de 4,2 m × 5,5 m, hauteur 2,60 m, une baie vitrée de 2,4 m de large (logement, famille Exemple, Bordeaux — fictif).
- Occupants : un couple, un enfant de 3 ans, un chien qui perd ses poils.
- Goûts : bois clair, tons sable.
- Existant à conserver : bibliothèque en chêne (dimensions [NON FOURNI], aucune intervention annoncée).
- Budget : 22 000 € TTC, périmètre fourniture + livraison + installation comprises.
- Date de pose : 15 avril 2027. Délai de fabrication du canapé annoncé par le fournisseur : 8 à 10 semaines.
- Date de référence : non fournie par le client. La date du jour (21/10/2026) est utilisée ici à titre indicatif pour situer les échéances ; elle ne provient pas du brief.
- Exclusions appliquées :
  - Verre → aucun plateau ou élément en verre sur TAB-01.
  - Cuir → aucun revêtement cuir sur CAN-01 et FAU-01.
- Pseudonymisez les données client et utilisez uniquement un outil approuvé par l'agence.

## Liste mobilier et équipements

| Repère | Élément | Quantité | Dimensions cibles et calculs | Matériaux / exigences à vérifier | Enveloppe estimative à confirmer par devis (TTC) | Délai / commande au plus tard | Statut |
|---|---|---|---|---|---|---|---|
| CAN-01 | Canapé d'angle 5 places | 1 | [NON FOURNI] — dimensions non imposées par le client. Paramètres nécessaires avant calcul : largeur par place assise, profondeur d'assise, longueur du retour d'angle, encombrement total souhaité. Ne pas déduire une dimension du seul nombre de places sans ces hypothèses. | Pas de cuir (exclusion) ; tissu déhoussable/lavable souhaitable (chien, enfant) — exigence à vérifier ; tons sable, pas de bois sombre sur piètement ; stabilité de la structure d'angle à vérifier | Hypothèse de répartition : 8 800 € TTC (≈40 % du budget total) | Fabrication 8 à 10 semaines (annoncé fournisseur). Préparation (prise de mesure, validation) : [NON FOURNI]. Commande au plus tard = 15/04/2027 − délai fabrication − préparation. Cas 10 sem. (70 j) : 15/04/2027 − 70 j = 04/02/2027. Cas 8 sem. (56 j) : 15/04/2027 − 56 j = 18/02/2027. Retenir 04/02/2027 comme échéance la plus sûre, sans marge de préparation (à ajouter si préparation connue). | Neuf |
| TAP-01 | Tapis | 1 | Formule dégagement pièce : longueur = 5,5 m − 2×0,30 m = 4,9 m ; largeur = 4,2 m − 2×0,30 m = 3,6 m (dégagement de 30 cm par côté fourni par le client, appliqué aux dimensions de la pièce). À vérifier : adéquation de ce calcul avec l'implantation réelle du mobilier (voir Questions). | Entretien facile (poils de chien, enfant au sol) — exigence à vérifier ; résistance au glissement — exigence à vérifier ; tons sable | Hypothèse de répartition : 3 300 € TTC (≈15 %) | Délai fournisseur : [NON FOURNI] → commande au plus tard non calculable | Neuf |
| TAB-01 | Table basse | 1 | [NON FOURNI] — dimensions non imposées. Paramètres nécessaires : longueur, largeur ou diamètre, hauteur souhaitées, dégagement de circulation autour. | Pas de verre (exclusion) ; bois clair ; angles arrondis (enfant 3 ans) — exigence à vérifier ; stabilité et finition non toxique — exigence à vérifier | Hypothèse de répartition : 1 760 € TTC (≈8 %) | Délai fournisseur : [NON FOURNI] → commande au plus tard non calculable | Neuf |
| FAU-01 | Fauteuil | 2 | [NON FOURNI] — dimensions non imposées. Paramètres nécessaires : largeur, profondeur, hauteur d'assise souhaitées. | Pas de cuir (exclusion) ; tissu déhoussable/lavable souhaitable (chien) — exigence à vérifier ; tons sable ; stabilité | Hypothèse de répartition : 3 300 € TTC (≈15 %, pour les 2 unités) | Délai fournisseur : [NON FOURNI] → commande au plus tard non calculable | Neuf |
| LAMP-01 | Lampadaire | 2 | [NON FOURNI] — dimensions non imposées. Paramètres nécessaires : hauteur, diamètre de l'embase, type d'éclairage. | Stabilité / résistance au basculement (enfant, chien) — exigence à vérifier ; câblage sécurisé (enfant) — exigence à vérifier ; bois clair sur pied si applicable ; réaction au feu de l'abat-jour à vérifier | Hypothèse de répartition : 1 760 € TTC (≈8 %, pour les 2 unités) | Délai fournisseur : [NON FOURNI] → commande au plus tard non calculable | Neuf |
| RID-01 | Rideaux pour baie vitrée | 1 jeu (quantité de lés : [NON FOURNI]) | Baie de 2,4 m de large (donnée client). Largeur totale de tringle et de tissu non calculable sans hypothèse de débord de part et d'autre de la baie et de fullness souhaitée — paramètres nécessaires avant calcul. Hauteur : du point de fixation au sol ou à l'appui, non fournie. | Entretien facile (poils de chien) — exigence à vérifier ; tons sable ; réaction au feu à vérifier selon réglementation applicable | Hypothèse de répartition : 1 320 € TTC (≈6 %) | Délai fournisseur : [NON FOURNI] → commande au plus tard non calculable | Neuf |
| BIB-01 | Bibliothèque en chêne | 1 | [NON FOURNI] (dimensions de l'existant non transmises) | Stabilité / fixation murale à vérifier (enfant pouvant grimper) — exigence à vérifier ; aucune intervention annoncée | 0 € TTC d'achat ; frais éventuels de déplacement, nettoyage ou fixation non inclus et à confirmer [NON FOURNI] | Aucune intervention annoncée ; délai d'intervention éventuel : [NON FOURNI] | Existant – réemploi |

Rapprochement :
- Canapé d'angle 5 places demandé → CAN-01.
- Tapis demandé → TAP-01.
- Table basse demandée → TAB-01.
- 2 fauteuils demandés → FAU-01 (quantité 2 sur une ligne).
- 2 lampadaires demandés → LAMP-01 (quantité 2 sur une ligne).
- Rideaux pour la baie demandés → RID-01.
- Bibliothèque en chêne existante → BIB-01, conservée, aucun retrait identifié.
- Aucun élément hors achat (retrait) signalé dans le brief.

## Contrôle du budget
- Budget client : 22 000 € TTC, périmètre fourniture + livraison + installation comprises.
- Hypothèses de répartition (non un prix de marché, à confirmer par devis) : CAN-01 8 800 € + TAP-01 3 300 € + TAB-01 1 760 € + FAU-01 3 300 € + LAMP-01 1 760 € + RID-01 1 320 € = 20 240 € TTC.
- Calcul : 8 800 + 3 300 + 1 760 + 3 300 + 1 760 + 1 320 = 20 240 € TTC.
- Écart = budget client − total des enveloppes = 22 000 € TTC − 20 240 € TTC = 1 760 € TTC.
- Ce solde de 1 760 € TTC n'est pas une marge disponible : il couvre notamment les frais non chiffrés de la bibliothèque existante (BIB-01 : déplacement/nettoyage/fixation éventuels), ainsi que tout écart entre les hypothèses de répartition et les devis réels.
- Les enveloppes sont estimatives, à confirmer par devis.

## Contrôle des délais
- Date de pose : 15 avril 2027. Date de référence : non fournie par le client ; date du jour (21/10/2026) utilisée à titre indicatif seulement.
- CAN-01 : délai fabrication 8 à 10 semaines (annoncé fournisseur) ; préparation [NON FOURNI]. Commande au plus tard (cas 10 sem., sans marge de préparation) : 04/02/2027 (15/04/2027 − 70 jours). Commande au plus tard (cas 8 sem.) : 18/02/2027 (15/04/2027 − 56 jours). À la date de référence indicative (21/10/2026), ces échéances ne sont pas dépassées.
- TAP-01, TAB-01, FAU-01, LAMP-01, RID-01 : délai fournisseur [NON FOURNI] → date de commande au plus tard non calculable.
- BIB-01 : aucune intervention annoncée ; délai d'intervention éventuel [NON FOURNI].
- Risques : aucun retard établi à ce jour pour CAN-01 (échéance à confirmer en fonction de la préparation réelle) ; pour TAP-01, TAB-01, FAU-01, LAMP-01 et RID-01, l'évaluation du risque de retard est impossible en l'absence de délai fournisseur.

## Caractéristiques à vérifier
- CAN-01 : réaction au feu (mobilier rembourré, selon réglementation applicable au logement), abrasion (cycles Martindale, à vérifier sur documentation fabricant, sans équivalence supposée), consignes d'entretien du tissu, stabilité de la structure d'angle, absence de cuir.
- TAP-01 : entretien/lavabilité, résistance au glissement (coefficient à vérifier sur documentation fabricant), réaction au feu si pertinent, fixation ou sous-couche antidérapante à vérifier au regard de la grande dimension.
- TAB-01 : absence de verre, stabilité, angles arrondis, finition non toxique, fixations si plateau rapporté.
- FAU-01 : abrasion (méthode et unité à préciser sur documentation fabricant), consignes d'entretien, stabilité, absence de cuir.
- LAMP-01 : stabilité / résistance au basculement, fixations éventuelles au sol ou au mur, câblage et sécurité électrique, réaction au feu de l'abat-jour.
- RID-01 : réaction au feu selon réglementation applicable, entretien/lavabilité, résistance à la lumière (tenue de la couleur sable) à vérifier sur documentation fabricant.
- BIB-01 : stabilité, fixation murale ou au sol à vérifier compte tenu de la présence d'un enfant en bas âge.
- Le professionnel responsable vérifie les règles applicables.

## Questions pour le client
- Confirmez-vous que le dégagement de 30 cm sur le tapis se calcule par rapport aux dimensions de la pièce entière (4,9 m × 3,6 m résultant) et non par rapport à une zone de circulation ou d'implantation du mobilier plus restreinte ?
- Quelles sont les dimensions souhaitées pour le canapé d'angle (largeur par place, profondeur d'assise, longueur du retour d'angle) ?
- Quelles sont les dimensions souhaitées pour la table basse, les fauteuils et les lampadaires ?
- Quel débord de tringle et quelle hauteur de rideaux souhaitez-vous pour la baie de 2,4 m (pour calculer la largeur et la longueur du tissu) ?
- Quelles sont les dimensions de la bibliothèque en chêne existante, et des frais de nettoyage, déplacement ou fixation sont-ils à prévoir ?
- Confirmez-vous les enveloppes proposées par ligne (hypothèses de répartition du budget de 22 000 € TTC), ou souhaitez-vous une autre pondération ?
- Quels sont les délais fournisseurs pour le tapis, la table basse, les fauteuils, les lampadaires et les rideaux ?
- Quel temps de préparation (prise de mesure, validation, commande) faut-il prévoir avant la commande du canapé, en plus du délai de fabrication de 8 à 10 semaines ?
- Le budget de 22 000 € TTC inclut-il la totalité des frais de livraison et de pose pour chaque ligne, ou ces frais sont-ils à prévoir en plus des enveloppes par élément ?
- Quelle est la date de référence actuelle du projet pour l'évaluation des délais (si différente de la date de rédaction) ?

