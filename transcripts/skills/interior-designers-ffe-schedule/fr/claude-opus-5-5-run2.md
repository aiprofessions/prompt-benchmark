# Transcript — skill interior-designers-ffe-schedule [fr] — claude-opus-5-5 — run 2

- model_id: `claude-opus-5-5` (provider `anthropic`)
- started_utc: 2026-10-21T06:34:23+00:00
- duration_s: 80.6
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
- Pièce, dimensions, occupants, usages et type de projet : séjour de 4,2 m × 5,5 m, hauteur 2,60 m, une baie vitrée de 2,4 m de large. Occupants : un couple, un enfant de 3 ans et un chien qui perd ses poils. Usages détaillés : [NON FOURNI]. Type de projet : Hypothèse : logement, car il s'agit du séjour d'une famille ; [NON FOURNI] dans le brief.
- Autres données du brief à conserver : client famille Exemple (fictive), Bordeaux. Préférences : bois clair, tons sable. Budget : 22 000 € TTC, livraison et installation comprises. Installation : 15 avril 2027. Délai de fabrication du canapé annoncé par les fournisseurs : 8 à 10 semaines. Existant : bibliothèque en chêne, à conserver. Position de la baie, des portes, de la bibliothèque et des prises : [NON FOURNI].
- Exclusions appliquées :
  - Verre → aucun plateau, piètement ou étagère en verre pour TAB-01. Aucun abat-jour ni diffuseur en verre pour LAM-01. Aucun élément décoratif en verre sur les lignes neuves.
  - Cuir → aucun revêtement, accoudoir ni passepoil en cuir pour CAN-01 et FAU-01. L'inclusion du simili-cuir dans ce refus est à confirmer.
- Pseudonymisez les données client et utilisez uniquement un outil approuvé par l'agence.

## Liste mobilier et équipements
| Repère | Élément | Quantité | Dimensions cibles et calculs | Matériaux / exigences à vérifier | Enveloppe estimative à confirmer par devis (HT/TTC) | Délai / commande au plus tard | Statut |
|---|---|---|---|---|---|---|---|
| CAN-01 | Canapé d'angle 5 places | 1 | Non déductible du seul nombre de places. Longueur de chaque branche = nombre d'assises de la branche × largeur d'assise + accoudoirs. Répartition des assises, largeur d'assise, profondeur et sens de l'angle : [NON FOURNI]. Implantation à vérifier par rapport à la baie de 2,4 m, à la bibliothèque et à la circulation. Accès (porte, escalier, ascenseur) : [NON FOURNI]. | Sans cuir. Tons sable. Tissu déhoussable, facile à nettoyer et à tissage limitant l'accroche des poils du chien : exigences à vérifier. Résistance à l'usage avec un enfant de 3 ans et un chien : exigence à vérifier. | Hypothèse : 7 000 € TTC, livraison et installation comprises | 8 à 10 semaines de fabrication. Au plus tard le 4 février 2027 (cas 10 semaines), avant déduction de la préparation : voir Contrôle des délais | Neuf |
| TAP-01 | Tapis | 1 | Longueur : 5,5 − 2 × 0,30 = 4,9 m. Largeur : 4,2 − 2 × 0,30 = 3,6 m. Cible : 4,9 × 3,6 m. Calcul fondé sur toute la pièce : à vérifier, car le tapis passerait sous la bibliothèque et devant la baie (voir Questions). | Tons sable. Entretien facilité face aux poils : exigence à vérifier. Antidérapant ou sous-tapis pour l'enfant : exigence à vérifier. | Hypothèse : 2 500 € TTC | Délai fournisseur : [NON FOURNI] | Neuf |
| TAB-01 | Table basse | 1 | Longueur × largeur × hauteur : [NON FOURNI]. Paramètres nécessaires : hauteur d'assise du canapé, longueur de la branche concernée, passage entre canapé et table. Valeurs à fixer avec l'agence. | Sans verre. Bois clair. Angles arrondis et stabilité pour un enfant de 3 ans : exigences à vérifier. Finition résistante aux rayures : exigence à vérifier. | Hypothèse : 1 200 € TTC | Délai fournisseur : [NON FOURNI] | Neuf |
| FAU-01 | Fauteuil | 2 | Largeur × profondeur × hauteur : [NON FOURNI]. Paramètres nécessaires : implantation face au canapé et circulation vers la baie. | Sans cuir. Tons sable, bois clair. Tissu déhoussable et facile à nettoyer (poils du chien) : exigence à vérifier. Stabilité : exigence à vérifier. | Hypothèse : 2 × 1 500 = 3 000 € TTC | Délai fournisseur : [NON FOURNI] | Neuf |
| LAM-01 | Lampadaire | 2 | Hauteur et emprise du pied : [NON FOURNI]. Plafond de 2,60 m à respecter. Emplacement des prises : [NON FOURNI]. | Sans verre, ni abat-jour ni diffuseur. Base lourde, stabilité anti-basculement et câbles hors de portée (enfant, chien) : exigences à vérifier. | Hypothèse : 2 × 400 = 800 € TTC | Délai fournisseur : [NON FOURNI] | Neuf |
| RID-01 | Rideaux pour la baie | [NON FOURNI] ; Hypothèse : 2 panneaux | Largeur de tringle ou de rail = 2,4 + 2 × 0,15 (débord, Hypothèse) = 2,7 m. Largeur de tissu = 2,7 × 2 (ampleur, Hypothèse) = 5,4 m, soit 2 panneaux de 2,7 m. Hauteur = hauteur de fixation − garde au sol. Si fixation à 2,60 m et garde de 0,01 m (Hypothèse) : 2,60 − 0,01 = 2,59 m, moins la hauteur du système de fixation [NON FOURNI]. Hauteur de la baie : [NON FOURNI]. | Tons sable. Lavable ou entretien facilité (poils) : exigence à vérifier. Aucun cordon ni chaînette accessible à l'enfant : exigence à vérifier. Fixations de tringle adaptées au support : exigence à vérifier. Tringle ou rail inclus dans la ligne : à confirmer. | Hypothèse : 2 000 € TTC, confection et pose comprises | Délai fournisseur ou confection : [NON FOURNI] | Neuf |
| BIB-01 | Bibliothèque en chêne | 1 | Dimensions : [NON FOURNI]. Emplacement : [NON FOURNI]. | Fixation murale anti-basculement (enfant de 3 ans) : exigence à vérifier. État et interventions (nettoyage, reprise de finition, démontage, déplacement) : [NON FOURNI]. Cohérence de la teinte du chêne avec le bois clair : à vérifier. | Pas d'achat. Hypothèse : 500 € TTC pour interventions éventuelles (fixation, protection, déplacement), à confirmer | Délais d'intervention : [NON FOURNI] | Existant – réemploi |

- Rapprochement :
  - canapé d'angle 5 places → CAN-01 ;
  - tapis → TAP-01 ;
  - table basse → TAB-01 ;
  - 2 fauteuils → FAU-01 (1 ligne, 2 objets) ;
  - 2 lampadaires → LAM-01 (1 ligne, 2 objets) ;
  - rideaux pour la baie → RID-01 ;
  - bibliothèque en chêne à conserver → BIB-01.
  - Total : 7 lignes et 8 objets dénombrés, plus les panneaux de rideaux dont la quantité reste à confirmer. Aucun élément à retirer n'est signalé.

## Contrôle du budget
- Budget client et périmètre : 22 000 € TTC, livraison et installation comprises.
- Hypothèses de répartition : les enveloppes sont une répartition de travail, pas des prix de marché. Chaque enveloppe est supposée inclure la livraison et l'installation de sa ligne. L'enveloppe BIB-01 couvre des interventions non encore définies, pas un achat.
- Total ou sous-total connu : 7 000 + 2 500 + 1 200 + 3 000 + 800 + 2 000 + 500 = 17 000 € TTC. Toutes les enveloppes sont des hypothèses, aucun coût n'est confirmé.
- Écart ou solde provisoire : 22 000 € TTC − 17 000 € TTC = 5 000 € TTC. Ce solde n'est pas une marge disponible. Restent à confirmer : devis de chaque ligne, tringle ou rail, sous-tapis, interventions sur la bibliothèque, frais de livraison et d'installation réels, accès difficiles éventuels.
- Les enveloppes sont estimatives, à confirmer par devis.

## Contrôle des délais
- Date de pose et date de référence : installation le 15 avril 2027. Date de référence pour le contrôle des délais : [NON FOURNI].
- Par repère :
  - CAN-01, en supposant des semaines calendaires (Hypothèse ; jours ouvrés ou fermetures fournisseurs à confirmer) :
    - cas 10 semaines : 15 avril 2027 − 70 jours = 4 février 2027 ;
    - cas 8 semaines : 15 avril 2027 − 56 jours = 18 février 2027.
    - Il faut encore déduire la préparation prévue (validation du tissu, livraison, transport) : [NON FOURNI]. Commande au plus tard = 4 février 2027 − préparation. Si le délai de 8 à 10 semaines ne comprend pas la livraison, celle-ci est aussi à déduire.
  - TAP-01, TAB-01, FAU-01, LAM-01, RID-01 : délais fournisseurs [NON FOURNI]. Commande = 15 avril 2027 − délai − préparation. Aucune date ne peut être calculée.
  - BIB-01 : délais d'intervention [NON FOURNI]. La fixation et le déplacement éventuel sont à coordonner avec la pose du 15 avril 2027 et avec celle du tapis.
- Risques : sans date de référence, aucun retard ne peut être établi. CAN-01 a l'échéance la plus contrainte connue (4 février 2027 au plus tard, avant préparation). Pour les autres lignes, l'évaluation est impossible.

## Caractéristiques à vérifier
- CAN-01 : réaction au feu selon le type de projet ; abrasion, avec méthode et unité (cycles Martindale ou doubles frottements, sans équivalence entre les deux) ; codes d'entretien et déhoussabilité ; composition du revêtement (absence de cuir) ; stabilité de l'assemblage d'angle.
- TAP-01 : résistance au glissement ou sous-tapis antidérapant ; codes et consignes d'entretien ; résistance à l'usage ; réaction au feu selon le type de projet.
- TAB-01 : absence de verre ; rayon des angles ; stabilité ; consignes d'entretien de la finition.
- FAU-01 : réaction au feu selon le type de projet ; abrasion avec méthode et unité ; codes d'entretien et déhoussabilité ; absence de cuir ; stabilité.
- LAM-01 : stabilité et lestage du pied ; absence de verre ; câbles et fixations ; données électriques du fabricant.
- RID-01 : réaction au feu selon le type de projet ; consignes d'entretien et stabilité dimensionnelle au lavage ; système de manœuvre sans cordon accessible ; fixations adaptées au support.
- BIB-01 : stabilité ; fixation murale adaptée au support ; état de la structure et de la finition.
- Le professionnel responsable vérifie les règles applicables.

## Questions pour le client
- Type de projet : confirmez-vous qu'il s'agit d'un logement ?
- Plan : où se trouvent la baie, les portes, la bibliothèque et les prises ? Quelle est la hauteur de la baie ? Quels sont les accès pour la livraison (largeur des portes, escalier, ascenseur) ?
- Tapis : les 30 cm de sol visible se comptent-ils par rapport aux murs (cible 4,9 × 3,6 m, tapis sous la bibliothèque et devant la baie) ou par rapport à la zone salon ?
- Canapé : quelle répartition des 5 places entre les branches, quel sens d'angle, quelle profondeur d'assise ?
- Table basse, fauteuils, lampadaires : avez-vous des dimensions souhaitées ?
- Exclusions : le refus du cuir inclut-il le simili-cuir ? Le refus du verre vaut-il aussi pour les luminaires et les petits éléments ?
- Rideaux : combien de panneaux ? Occultants ou voilages ? Tringle ou rail à inclure ? Quel type de fixation (plafond ou mur) ?
- Bibliothèque : dimensions, état, emplacement ? Faut-il la fixer, la déplacer, la nettoyer ou la reprendre ? Avec quel budget ?
- Budget : validez-vous la répartition hypothétique (total 17 000 € TTC, solde provisoire 5 000 € TTC) ? La livraison et l'installation sont-elles bien à intégrer ligne par ligne ?
- Délais : les 8 à 10 semaines du canapé sont-elles en semaines calendaires ou ouvrées, livraison comprise ou non ? Quel temps de préparation prévoir ?
- Délais fournisseurs : quels sont ceux des autres lignes ?
- Date de référence : quelle date utiliser pour contrôler les délais ?
- Usages : télévision, coin jeu de l'enfant, couchage du chien ou autre usage à intégrer ?

