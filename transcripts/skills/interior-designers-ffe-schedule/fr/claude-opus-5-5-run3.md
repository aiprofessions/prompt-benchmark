# Transcript — skill interior-designers-ffe-schedule [fr] — claude-opus-5-5 — run 3

- model_id: `claude-opus-5-5` (provider `anthropic`)
- started_utc: 2026-10-21T07:06:41+00:00
- duration_s: 82.2
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
- Pièce, dimensions, occupants, usages et type de projet : séjour de 4,2 m × 5,5 m, hauteur 2,60 m, une baie vitrée de 2,4 m de large. Occupants : un couple, un enfant de 3 ans et un chien qui perd ses poils. Usages détaillés : [NON FOURNI]. Type de projet : Hypothèse : logement, car il s'agit d'un séjour familial. À confirmer, notamment pour écarter un ERP.
- Autres données du brief à conserver :
  - Client : famille Exemple (fictive), Bordeaux.
  - Goûts : bois clair, tons sable.
  - Existant : bibliothèque en chêne, à conserver.
  - Budget : 22 000 € TTC, livraison et installation comprises.
  - Installation : 15 avril 2027.
  - Délai de fabrication du canapé : 8 à 10 semaines.
- Exclusions appliquées :
  - Verre :
    - TBL-01 : aucun plateau, aucun élément en verre.
    - LUM-01 : aucun diffuseur, abat-jour ni pièce en verre.
    - BIB-01 : vérifier l'absence de portes ou d'étagères vitrées. Si elles existent, un arbitrage est nécessaire, car le meuble est à conserver.
    - RID-01 : aucune finition ni accessoire en verre.
  - Cuir :
    - CAN-01 et FAU-01 : aucun revêtement, aucune finition ni aucun accoudoir en cuir.
    - TAP-01 : aucune bordure en cuir.
    - Le cas du simili-cuir est à confirmer.
- Pseudonymisez les données client et utilisez uniquement un outil approuvé par l'agence.

## Liste mobilier et équipements
| Repère | Élément | Quantité | Dimensions cibles et calculs | Matériaux / exigences à vérifier | Enveloppe estimative à confirmer par devis (HT/TTC) | Délai / commande au plus tard | Statut |
|---|---|---|---|---|---|---|---|
| CAN-01 | Canapé d'angle 5 places | 1 | Dimensions [NON FOURNI]. Paramètres nécessaires : largeur d'assise par place, nombre et largeur des modules, accoudoirs, profondeur, sens de l'angle (gauche/droite), retour d'angle. Longueur totale = somme des modules + accoudoirs. Vérifier passages de portes, escalier, ascenseur et circulation | Sans cuir. Tons sable. Tissu déhoussable, entretien facilité, tissu résistant à l'usage et aux poils du chien : exigences à vérifier. Lavabilité adaptée à un enfant de 3 ans : exigence à vérifier | Hypothèse : 8 000 € TTC, livraison et installation incluses | Délai 8 à 10 semaines. Commande au plus tard entre le 4 février 2027 et le 18 février 2027, avant préparation [NON FOURNI] (calcul ci-dessous) | Neuf |
| TAP-01 | Tapis | 1 | 30 cm = 0,30 m. Longueur : 5,5 − 2 × 0,30 = 4,9 m. Largeur : 4,2 − 2 × 0,30 = 3,6 m. Cible : 4,9 m × 3,6 m. Vérifier l'emprise sous la bibliothèque, le débattement des portes et l'accès à la baie | Tons sable. Sans cuir. Poils ras ou tissage plat, entretien facilité face aux poils du chien, nettoyabilité : exigences à vérifier. Antidérapant, enfant de 3 ans : exigence à vérifier | Hypothèse : 2 500 € TTC | Délai [NON FOURNI] | Neuf |
| TBL-01 | Table basse | 1 | Dimensions [NON FOURNI]. Paramètres nécessaires : longueur et profondeur du canapé, hauteur d'assise, distance de circulation canapé-table. Dimension non déduite sans ces données | Sans verre. Bois clair. Angles arrondis et stabilité, enfant de 3 ans : exigences à vérifier. Finition résistante à l'usage : exigence à vérifier | Hypothèse : 1 500 € TTC | Délai [NON FOURNI] | Neuf |
| FAU-01 | Fauteuils | 2 | Dimensions [NON FOURNI]. Paramètres nécessaires : emprise au sol, hauteur d'assise, dégagements autour de CAN-01 et TBL-01 | Sans cuir. Bois clair et tons sable. Tissu déhoussable, entretien facilité face aux poils du chien, stabilité : exigences à vérifier | Hypothèse : 3 000 € TTC pour les 2, soit 2 × 1 500 € TTC | Délai [NON FOURNI] | Neuf |
| LUM-01 | Lampadaires | 2 | Hauteur ≤ 2,60 m (hauteur sous plafond). Autres dimensions [NON FOURNI] : diamètre du pied, emprise de l'abat-jour | Sans verre. Bois clair et tons sable. Stabilité, base lestée et câbles hors de portée de l'enfant et du chien : exigences à vérifier | Hypothèse : 1 200 € TTC pour les 2, soit 2 × 600 € TTC | Délai [NON FOURNI] | Neuf |
| RID-01 | Rideaux pour la baie | 1 jeu (nombre de panneaux [NON FOURNI]) | Largeur de la tringle = 2,4 m + 2 × débord latéral [NON FOURNI]. Largeur de tissu = largeur de la tringle × coefficient d'ampleur [NON FOURNI]. Hauteur : Hypothèse : fixation au plafond et garde au sol de 1 cm, soit 2,60 − 0,01 = 2,59 m. Hauteur de la baie [NON FOURNI] | Tons sable. Tissu lavable et entretien facilité face aux poils du chien : exigences à vérifier. Absence de cordons accessibles à l'enfant : exigence à vérifier. Tringle ou rail non demandé, à confirmer | Hypothèse : 2 000 € TTC, confection et pose incluses, tringlerie à confirmer | Délai [NON FOURNI] | Neuf |
| BIB-01 | Bibliothèque en chêne | 1 | Dimensions [NON FOURNI] | Présence de verre à vérifier (arbitrage si oui). Teinte du chêne face au goût pour le bois clair à vérifier. Fixation murale et stabilité, enfant de 3 ans : exigences à vérifier. Interventions [NON FOURNI] | Pas d'achat. Frais de nettoyage, déplacement, adaptation ou fixation [NON FOURNI], coût non supposé nul | Délai d'intervention [NON FOURNI] | Existant – réemploi |

- Rapprochement :
  - canapé d'angle 5 places → CAN-01
  - tapis → TAP-01
  - table basse → TBL-01
  - 2 fauteuils → FAU-01 (2 objets, 1 ligne)
  - 2 lampadaires → LUM-01 (2 objets, 1 ligne)
  - rideaux pour la baie → RID-01
  - bibliothèque en chêne → BIB-01
  - Total : 7 lignes, 9 objets hors panneaux de rideaux. Aucun élément à retirer n'est mentionné dans le brief.

## Contrôle du budget
- Budget client et périmètre : 22 000 € TTC, livraison et installation comprises.
- Hypothèses de répartition : enveloppes proposées pour cadrage, à confirmer par devis, livraison et installation incluses.
  - CAN-01 : 8 000 € TTC
  - FAU-01 : 3 000 € TTC
  - TAP-01 : 2 500 € TTC
  - RID-01 : 2 000 € TTC
  - TBL-01 : 1 500 € TTC
  - LUM-01 : 1 200 € TTC
  - BIB-01 : [NON FOURNI]
  - Ces montants ne sont pas des prix de marché.
- Total ou sous-total connu : 8 000 + 3 000 + 2 500 + 2 000 + 1 500 + 1 200 = 18 200 € TTC.
- Écart ou solde provisoire : 22 000 € TTC − 18 200 € TTC = 3 800 € TTC. Ce solde n'est pas une marge disponible. Il doit couvrir les coûts encore inconnus :
  - interventions éventuelles sur BIB-01 ;
  - tringlerie et fixations de RID-01 ;
  - fixations murales ;
  - surcoûts de livraison ou d'accès.
- Les enveloppes sont estimatives, à confirmer par devis.

## Contrôle des délais
- Date de pose : installation le 15 avril 2027. Date de référence pour le contrôle : [NON FOURNI].
- CAN-01 :
  - Délai annoncé : 8 à 10 semaines, en semaines calendaires telles qu'indiquées.
  - Le brief ne dit pas si ce délai inclut la livraison. Les fermetures fournisseurs ne sont pas connues.
  - 10 semaines = 70 jours : 15 avril 2027 − 70 jours = 4 février 2027.
  - 8 semaines = 56 jours : 15 avril 2027 − 56 jours = 18 février 2027.
  - Commande au plus tard = date obtenue − préparation prévue [NON FOURNI] : validation du tissu, échantillons, acompte, transport.
  - Hypothèse prudente : retenir le délai haut (10 semaines), soit le 4 février 2027 avant déduction de la préparation.
- TAP-01, TBL-01, FAU-01, LUM-01 et RID-01 : délais fournisseurs et préparation [NON FOURNI]. Pour chacun, commande au plus tard = 15 avril 2027 − délai − préparation. Calcul impossible.
- BIB-01 : délais d'intervention (nettoyage, déplacement, fixation) [NON FOURNI].
- Risques : aucune date de référence n'est fournie, donc un retard éventuel ne peut pas être évalué. CAN-01 a une échéance à confirmer, entre le 4 et le 18 février 2027 moins la préparation.

## Caractéristiques à vérifier
- CAN-01 et FAU-01 :
  - réaction au feu du revêtement et du rembourrage ;
  - abrasion, avec la méthode et l'unité indiquées (cycles Martindale ou doubles frottements, sans équivalence supposée) ;
  - codes d'entretien et caractère déhoussable ;
  - absence de cuir dans la composition ;
  - stabilité.
- TAP-01 : réaction au feu, résistance à l'usage, consignes d'entretien, résistance au glissement ou sous-couche antidérapante, composition.
- TBL-01 : stabilité, rayons des angles, finition et entretien du bois, absence de verre.
- LUM-01 : stabilité et lestage, absence de verre, notice de montage, gestion des câbles.
- RID-01 : réaction au feu, codes d'entretien et lavabilité, fixations de la tringlerie selon le support, dispositif de manœuvre sans cordon accessible.
- BIB-01 : état, stabilité, fixation murale selon le support, présence de verre, finition.
- Le professionnel responsable vérifie les règles applicables.

## Questions pour le client
- Le projet est-il bien un logement (Hypothèse retenue) ?
- Quels sont vos usages du séjour : télévision, repas, jeux de l'enfant, couchage d'appoint ?
- Canapé :
  - Quelles dimensions maximales et quel sens d'angle (gauche ou droite) souhaitez-vous ?
  - Quelle est son implantation, et la baie ou la bibliothèque impose-t-elle des contraintes ?
- Accès : quelles sont les dimensions des portes, des couloirs, de l'escalier ou de l'ascenseur pour livrer le canapé et un tapis de 4,9 m × 3,6 m ?
- Tapis : confirmez-vous 4,9 m × 3,6 m, même s'il passe sous la bibliothèque et les pieds des meubles ?
- Table basse, fauteuils et lampadaires : avez-vous des dimensions, des formes ou des hauteurs souhaitées ?
- Rideaux :
  - Quelle est la hauteur de la baie, et la fixation se fait-elle au plafond ou au mur ?
  - Quels débords latéraux et quelle ampleur souhaitez-vous ?
  - Faut-il prévoir la tringlerie ? Les rideaux sont-ils occultants ou voilages ?
- Bibliothèque en chêne :
  - Quelles sont ses dimensions, et comporte-t-elle du verre ?
  - Sa teinte vous convient-elle avec le bois clair ?
  - Faut-il prévoir un nettoyage, un déplacement ou une fixation murale, et à quel coût ?
- Exclusions : l'exclusion du cuir vaut-elle aussi pour le simili-cuir ?
- Budget :
  - Validez-vous la répartition proposée en Hypothèse (total de 18 200 € TTC, solde provisoire de 3 800 € TTC) ?
  - La livraison et l'installation sont-elles bien incluses dans chaque enveloppe ?
- Délais :
  - Quelle est la date de référence pour le contrôle des délais ?
  - Pour le canapé, quel délai retenir entre 8 et 10 semaines ? Inclut-il la livraison ?
  - Quel temps de préparation faut-il prévoir avant commande ?
  - Quels sont les délais fournisseurs des autres éléments ?

