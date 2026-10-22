# Transcript — skill interior-designers-ffe-schedule [fr] — claude-fable-5-1 — run 2

- model_id: `claude-fable-5-1` (provider `anthropic`)
- started_utc: 2026-10-21T06:25:04+00:00
- duration_s: 101.8
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
- Pièce, dimensions, occupants, usages et type de projet : séjour, 4,2 m × 5,5 m, hauteur 2,60 m, une baie vitrée de 2,4 m de large ; occupants : un couple, un enfant de 3 ans, un chien qui perd ses poils ; usage : séjour familial ; type de projet : Hypothèse : logement (déduit de « famille » et « séjour », non écrit dans le brief).
- Autres données du brief à conserver : client famille Exemple (fictive), Bordeaux ; goûts : bois clair, tons sable ; budget 22 000 € TTC, livraison et installation comprises ; installation : 15 avril 2027 ; délai de fabrication du canapé annoncé par les fournisseurs de l'agence : 8 à 10 semaines ; existant : bibliothèque en chêne à conserver.
- Exclusions appliquées :
  - Verre → aucun plateau, étagère, pied ou diffuseur en verre : table basse (TAB-01), lampadaires (LUM-01), accessoires de rideaux (RID-01) ; vérifier l'absence de verre sur la bibliothèque existante (BIB-01).
  - Cuir → aucun revêtement ni détail en cuir (y compris cuir recyclé ou croûte) : canapé (CAN-01), fauteuils (FAU-01) ; vérifier également table basse et lampadaires (poignées, sangles, finitions).
- Pseudonymisez les données client et utilisez uniquement un outil approuvé par l'agence.

## Liste mobilier et équipements
| Repère | Élément | Quantité | Dimensions cibles et calculs | Matériaux / exigences à vérifier | Enveloppe estimative à confirmer par devis (HT/TTC) | Délai / commande au plus tard | Statut |
|---|---|---|---|---|---|---|---|
| CAN-01 | Canapé d'angle 5 places | 1 | Dimensions [NON FOURNI]. Non déductible du seul nombre de places : paramètres à fixer avec le client — largeur d'assise par place, profondeur, longueur des deux branches de l'angle, sens de l'angle, dégagement devant la baie de 2,4 m et devant la bibliothèque (BIB-01). Vérifier accès, passage de portes et circulation. | Sans cuir. Tons sable, piètement bois clair souhaités. Exigence à vérifier : tissu déhoussable ou housses lavables (chien, enfant) ; entretien facilité et résistance aux poils ; angles non agressifs (enfant de 3 ans) ; stabilité. | Hypothèse : 8 000 € TTC (fourniture) | Délai fournisseur 8 à 10 semaines (hypothèse : semaines calendaires). Au plus tard = 15 avril 2027 − 10 semaines (70 jours) − préparation [NON FOURNI] = 4 février 2027 − préparation [NON FOURNI]. Avec 8 semaines : 18 février 2027 − préparation [NON FOURNI]. | Neuf |
| TAP-01 | Tapis | 1 | Dégagement fourni : 30 cm = 0,30 m par côté. Largeur : 4,2 − 2 × 0,30 = 3,6 m. Longueur : 5,5 − 2 × 0,30 = 4,9 m. Cible 3,6 m × 4,9 m ; vérifier compatibilité avec la position du canapé, de la bibliothèque et de l'ouverture de la baie. | Tons sable. Exigence à vérifier : entretien facilité, poils retirables, lavabilité ou traitement anti-taches (enfant, chien) ; antidérapant ou sous-couche à vérifier. Non verre / non cuir : sans objet. | Hypothèse : 2 500 € TTC (fourniture) | Délai fournisseur [NON FOURNI] ; calcul = 15 avril 2027 − délai − préparation, impossible. | Neuf |
| TAB-01 | Table basse | 1 | Dimensions [NON FOURNI]. Paramètres à fixer : hauteur par rapport à l'assise du canapé, dégagement entre canapé et table, encombrement sur le tapis 3,6 m × 4,9 m. | Sans verre (plateau, tablette, pieds). Bois clair souhaité. Exigence à vérifier : angles arrondis (enfant de 3 ans), stabilité, surface résistante aux taches et à l'entretien fréquent. | Hypothèse : 1 500 € TTC (fourniture) | Délai fournisseur [NON FOURNI] ; calcul impossible. | Neuf |
| FAU-01 | Fauteuil | 2 (1 ligne, 2 objets) | Dimensions [NON FOURNI]. Paramètres : largeur, profondeur, implantation face au canapé ou près de la baie, dégagement de circulation. | Sans cuir. Tissu tons sable, piètement bois clair souhaités. Exigence à vérifier : déhoussable ou entretien facilité (chien), stabilité. | Hypothèse : 2 × 1 500 € TTC = 3 000 € TTC (fourniture) | Délai fournisseur [NON FOURNI] ; calcul impossible. | Neuf |
| LUM-01 | Lampadaire | 2 (1 ligne, 2 objets) | Hauteur [NON FOURNI] ; plafond 2,60 m à respecter. Emplacement et prises électriques à vérifier. | Sans verre (diffuseur, globe, pied). Sans cuir. Exigence à vérifier : stabilité / base lestée et anti-basculement (enfant de 3 ans, chien), câble sécurisé, matériaux de l'abat-jour. | Hypothèse : 2 × 600 € TTC = 1 200 € TTC (fourniture) | Délai fournisseur [NON FOURNI] ; calcul impossible. | Neuf |
| RID-01 | Rideaux pour la baie | 1 ensemble (nombre de panneaux [NON FOURNI] ; Hypothèse : 2 panneaux) | Baie 2,4 m de large. Largeur de tringle = 2,4 m + débord de chaque côté [NON FOURNI] (Hypothèse : 0,20 m par côté → 2,4 + 2 × 0,20 = 2,8 m). Hauteur de confection : hauteur de fixation [NON FOURNI] ; plafond 2,60 m. Largeur d'étoffe = largeur de tringle × coefficient de plis [NON FOURNI]. | Tons sable. Sans verre ni cuir sur embouts, tringle, embrasses. Exigence à vérifier : tissu lavable (poils), fixation de tringle au mur ou plafond, type de support (béton, placo) et fixations adaptées. | Hypothèse : 2 500 € TTC (fourniture, confection et pose) | Délai confection et pose [NON FOURNI] ; calcul impossible. | Neuf |
| BIB-01 | Bibliothèque en chêne | 1 | Dimensions [NON FOURNI]. Position actuelle / future [NON FOURNI]. | Existant, chêne. Vérifier absence de verre (étagères, portes). Exigence à vérifier : fixation anti-basculement au mur (enfant de 3 ans), stabilité, état des surfaces. | Hors achat. Frais éventuels de déplacement, nettoyage, adaptation ou fixation : [NON FOURNI] — ne pas supposer un coût nul. | Intervention prévue [NON FOURNI] ; à planifier avant le 15 avril 2027 si fixation ou déplacement. | Existant – réemploi |
| LIV-01 | Livraison et installation (hors pose rideaux incluse dans RID-01) | — | Accès, ascenseur, étage, stationnement [NON FOURNI]. | Coordination des livraisons avec la date du 15 avril 2027. | Hypothèse : 1 800 € TTC | Date d'installation 15 avril 2027 ; créneaux fournisseurs [NON FOURNI]. | Prestation |

- Rapprochement : canapé d'angle 5 places → CAN-01 ; tapis → TAP-01 ; table basse → TAB-01 ; 2 fauteuils → FAU-01 (2 objets) ; 2 lampadaires → LUM-01 (2 objets) ; rideaux pour la baie → RID-01 ; bibliothèque en chêne à conserver → BIB-01 (réemploi, hors achat). Aucun retrait demandé. Total : 7 lignes mobilier/équipements (8 objets neufs + 1 existant) + 1 ligne de prestation LIV-01.

## Contrôle du budget
- Budget client et périmètre : 22 000 € TTC, livraison et installation comprises (fourniture + livraison + installation).
- Hypothèses de répartition (enveloppes estimatives à confirmer par devis, pas des prix de marché) : CAN-01 8 000 € TTC ; TAP-01 2 500 € TTC ; TAB-01 1 500 € TTC ; FAU-01 3 000 € TTC ; LUM-01 1 200 € TTC ; RID-01 2 500 € TTC ; LIV-01 1 800 € TTC ; BIB-01 [NON FOURNI].
- Sous-total connu : 8 000 + 2 500 + 1 500 + 3 000 + 1 200 + 2 500 + 1 800 = 20 500 € TTC.
- Solde provisoire : 22 000 € TTC − 20 500 € TTC = 1 500 € TTC. Ce solde n'est pas une marge disponible : les frais BIB-01 (déplacement, nettoyage, fixation) et les éventuels suppléments de livraison (étage, accès) restent à confirmer.
- Les enveloppes sont estimatives, à confirmer par devis.

## Contrôle des délais
- Date de pose et date de référence : installation 15 avril 2027 ; date de référence pour le contrôle [NON FOURNI] ; temps de préparation (validation, acompte, mise en production) [NON FOURNI] ; traitement en jours ouvrés ou calendaires [NON FOURNI] (hypothèse : semaines calendaires).
- Par repère :
  - CAN-01 : 8 à 10 semaines. Cas défavorable 10 semaines = 70 jours : 15 avril 2027 − 70 jours = 4 février 2027, puis − préparation [NON FOURNI]. Cas 8 semaines = 56 jours : 15 avril 2027 − 56 jours = 18 février 2027, puis − préparation [NON FOURNI]. Retenir la date du cas défavorable. La livraison doit arriver avant ou le 15 avril 2027 : le délai annoncé couvre-t-il la livraison à Bordeaux ? [NON FOURNI].
  - TAP-01, TAB-01, FAU-01, LUM-01, RID-01 : délais fournisseurs [NON FOURNI] ; commande au plus tard non calculable.
  - BIB-01 : interventions [NON FOURNI] ; à planifier avant le 15 avril 2027 si déplacement ou fixation.
  - LIV-01 : créneaux de livraison [NON FOURNI].
- Risques : évaluation impossible sans date de référence ; CAN-01 : échéance à confirmer (4 février 2027 hors préparation) ; autres lignes : échéances à confirmer dès réception des délais.

## Caractéristiques à vérifier
- CAN-01, FAU-01 : composition du tissu (sans cuir) ; abrasion avec méthode et unité indiquées par le fabricant (cycles Martindale ou doubles frottements, sans équivalence supposée) ; déhoussabilité et consignes d'entretien (codes du fabricant) ; réaction au feu des mousses et tissus selon la documentation fabricant ; stabilité et finition des angles.
- TAP-01 : composition, consignes d'entretien et lavabilité, résistance au glissement (sous-couche), réaction au feu si documentée.
- TAB-01 : matériau du plateau (sans verre), rayon des angles, stabilité, résistance de la finition aux taches, consignes d'entretien.
- LUM-01 : matériaux (sans verre), stabilité / masse de la base, conformité électrique sur documentation fabricant, type de source lumineuse.
- RID-01 : composition, consignes d'entretien et lavabilité, coefficient de plis, réaction au feu si documentée, résistance de la tringle et fixations selon support.
- BIB-01 : état, fixations anti-basculement adaptées au mur, charge admissible des étagères, absence de verre.
- Le professionnel responsable vérifie les règles applicables.

## Questions pour le client
1. Confirmez-vous qu'il s'agit d'un logement (hypothèse retenue) ?
2. Canapé d'angle : dimensions souhaitées ou maximales, sens de l'angle, largeur d'assise par place, profondeur, position par rapport à la baie et à la bibliothèque ?
3. Dimensions, position actuelle et future de la bibliothèque en chêne ; comporte-t-elle du verre ? Interventions prévues (déplacement, nettoyage, fixation au mur) et frais associés ?
4. Validez-vous le tapis à 3,6 m × 4,9 m (30 cm de sol visible par côté) ? Préférence de matière (laine, synthétique, lavable) ?
5. Table basse : hauteur, dimensions, forme ; accord sur angles arrondis ?
6. Fauteuils et lampadaires : dimensions, hauteur maximale, emplacement des prises ?
7. Rideaux : fixation mur ou plafond, hauteur de fixation, débord par côté (hypothèse 0,20 m), nombre de panneaux (hypothèse 2), doublure ou occultation, coefficient de plis ?
8. Validez-vous la répartition hypothétique des enveloppes (CAN-01 8 000, TAP-01 2 500, TAB-01 1 500, FAU-01 3 000, LUM-01 1 200, RID-01 2 500, LIV-01 1 800 € TTC) et le solde provisoire de 1 500 € TTC non affecté ?
9. Quelle date de référence retenir pour le contrôle des délais ? Quel temps de préparation (validation, acompte, mise en production) prévoir avant chaque commande ?
10. Le délai de 8 à 10 semaines du canapé est-il en semaines calendaires ou ouvrées, et inclut-il la livraison à Bordeaux ?
11. Délais fournisseurs pour tapis, table basse, fauteuils, lampadaires, rideaux (confection et pose) ?
12. Conditions d'accès pour la livraison (étage, ascenseur, largeur des portes, stationnement) ?
13. Confirmez-vous l'exclusion du verre et du cuir sur tous les éléments, y compris détails et accessoires ?

