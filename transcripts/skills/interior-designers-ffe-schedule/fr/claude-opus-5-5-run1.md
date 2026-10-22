# Transcript — skill interior-designers-ffe-schedule [fr] — claude-opus-5-5 — run 1

- model_id: `claude-opus-5-5` (provider `anthropic`)
- started_utc: 2026-10-21T06:01:00+00:00
- duration_s: 93.1
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

Intention

  - Pièce, dimensions, occupants, usages et type de projet : séjour de 4,2 m × 5,5 m, hauteur 2,60 m, une baie vitrée de 2,4 m de large ; occupants : un couple, un enfant de 3 ans et un chien qui perd ses poils ; usages détaillés [NON FOURNI] ; type de projet [NON FOURNI]. Hypothèse : logement, et non ERP.
  - Autres données du brief à conserver : famille Exemple (fictive), Bordeaux ; budget 22 000 € TTC, livraison et installation comprises ; installation le 15 avril 2027 ; délai de fabrication du canapé annoncé par les fournisseurs : 8 à 10 semaines ; goûts : bois clair, tons sable ; existant : bibliothèque en chêne à conserver.
  - Exclusions appliquées :
      Verre : aucun plateau en verre pour la table basse (TAB-01) ; aucun diffuseur, abat-jour ni élément en verre pour les lampadaires (LAM-01). Pour la bibliothèque existante (BIB-01), d'éventuelles portes ou tablettes vitrées sont à vérifier et à arbitrer, puisque la pièce est conservée.
      Cuir : aucun revêtement ni accoudoir en cuir pour le canapé (CAN-01) et les fauteuils (FAU-01) ; aucune finition cuir pour les autres lignes. L'extension de ce refus au simili-cuir est à confirmer.
  - Pseudonymisez les données client et utilisez uniquement un outil approuvé par l'agence.


Liste mobilier et équipements

  CAN-01
    Élément : canapé d'angle 5 places
    Quantité : 1
    Dimensions cibles et calculs : longueur de chaque branche, profondeur, hauteur d'assise et côté de l'angle [NON FOURNI]. Une formule est possible (longueur des branches = nombre de places × largeur d'assise par place + accoudoirs), mais la largeur par place et les accoudoirs ne sont pas fournis : aucune dimension n'est déduite des seules 5 places. Le passage dans les accès (porte, escalier, ascenseur) est à vérifier.
    Matériaux / exigences à vérifier : sans cuir ; tons sable ; housses déhoussables, tissu facile à débarrasser des poils de chien et résistant à l'usage (enfant, chien), exigences à vérifier ; pieds en bois clair si visibles.
    Enveloppe estimative à confirmer par devis : [NON FOURNI] € TTC
    Délai / commande au plus tard : fabrication 8 à 10 semaines ; voir Contrôle des délais (4 février 2027 au plus tard, hors préparation)
    Statut : Neuf

  TAP-01
    Élément : tapis
    Quantité : 1
    Dimensions cibles et calculs : 30 cm = 0,30 m de sol visible de chaque côté. Longueur : 5,5 − 2 × 0,30 = 4,90 m. Largeur : 4,2 − 2 × 0,30 = 3,60 m. Tapis cible : 4,90 m × 3,60 m. Hypothèse : le retrait de 30 cm se mesure depuis les murs de la pièce. Si la bibliothèque est posée au sol contre un mur avec une profondeur supérieure à 0,30 m, le tapis passe dessous : arbitrage nécessaire. Le débattement de la baie est à vérifier.
    Matériaux / exigences à vérifier : tons sable ; entretien facilité face aux poils (aspiration, nettoyage) et résistance au glissement (enfant de 3 ans), exigences à vérifier ; besoin d'une sous-couche [NON FOURNI].
    Enveloppe estimative à confirmer par devis : [NON FOURNI] € TTC
    Délai / commande au plus tard : délai fournisseur [NON FOURNI]
    Statut : Neuf

  TAB-01
    Élément : table basse
    Quantité : 1
    Dimensions cibles et calculs : longueur, largeur et hauteur [NON FOURNI] ; elles dépendent des dimensions du canapé et des dégagements de circulation, non fournis.
    Matériaux / exigences à vérifier : sans verre ; bois clair ; angles arrondis et stabilité (enfant de 3 ans), exigences à vérifier ; surface facile d'entretien.
    Enveloppe estimative à confirmer par devis : [NON FOURNI] € TTC
    Délai / commande au plus tard : délai fournisseur [NON FOURNI]
    Statut : Neuf

  FAU-01
    Élément : fauteuils
    Quantité : 2 (1 ligne)
    Dimensions cibles et calculs : largeur, profondeur et hauteur [NON FOURNI] ; l'implantation par rapport au canapé et aux circulations est à vérifier.
    Matériaux / exigences à vérifier : sans cuir ; tons sable ou bois clair ; tissu déhoussable, adapté aux poils et résistant à l'usage, exigences à vérifier ; stabilité.
    Enveloppe estimative à confirmer par devis : [NON FOURNI] € TTC
    Délai / commande au plus tard : délai fournisseur [NON FOURNI]
    Statut : Neuf

  LAM-01
    Élément : lampadaires
    Quantité : 2 (1 ligne)
    Dimensions cibles et calculs : hauteur [NON FOURNI], qui doit rester inférieure à la hauteur sous plafond de 2,60 m ; emprise du pied [NON FOURNI] ; positions des prises électriques [NON FOURNI].
    Matériaux / exigences à vérifier : sans verre (diffuseur et abat-jour compris) ; bois clair ou tons sable ; stabilité contre le basculement (enfant, chien) et gestion des câbles, exigences à vérifier.
    Enveloppe estimative à confirmer par devis : [NON FOURNI] € TTC
    Délai / commande au plus tard : délai fournisseur [NON FOURNI]
    Statut : Neuf

  RID-01
    Élément : rideaux pour la baie vitrée
    Quantité : nombre de panneaux [NON FOURNI] (1 ligne)
    Dimensions cibles et calculs : baie de 2,4 m de large. Largeur de tringle ou de rail = 2,4 m + débords de chaque côté [NON FOURNI]. Largeur de tissu = largeur de tringle × coefficient d'ampleur [NON FOURNI]. Hauteur = hauteur de fixation − garde au sol [NON FOURNI], avec une fixation au plus à 2,60 m sous plafond. Fixation au plafond ou au mur [NON FOURNI].
    Matériaux / exigences à vérifier : tons sable ; tissu lavable et adapté aux poils, exigence à vérifier ; absence de cordons accessibles (enfant), à vérifier ; fourniture de la tringle ou du rail [NON FOURNI] ; occultation souhaitée [NON FOURNI].
    Enveloppe estimative à confirmer par devis : [NON FOURNI] € TTC
    Délai / commande au plus tard : délai de confection [NON FOURNI]
    Statut : Neuf

  BIB-01
    Élément : bibliothèque en chêne
    Quantité : 1
    Dimensions cibles et calculs : [NON FOURNI] (largeur, profondeur, hauteur, emplacement)
    Matériaux / exigences à vérifier : chêne ; fixation murale anti-basculement (enfant de 3 ans), à vérifier ; présence d'éléments en verre à vérifier ; harmonie avec le bois clair à vérifier.
    Enveloppe estimative à confirmer par devis : interventions [NON FOURNI] ; coût nul non supposé (nettoyage, fixation, déplacement éventuel à confirmer)
    Délai / commande au plus tard : délai d'intervention [NON FOURNI]
    Statut : Existant – réemploi

  - Rapprochement : canapé d'angle → CAN-01 ; tapis → TAP-01 ; table basse → TAB-01 ; 2 fauteuils → FAU-01 ; 2 lampadaires → LAM-01 ; rideaux → RID-01 ; bibliothèque existante → BIB-01. Cela fait 7 lignes, pour au moins 9 objets plus les rideaux, dont le nombre de panneaux n'est pas fourni. Aucun retrait n'est mentionné dans le brief.


Contrôle du budget

  - Budget client et périmètre : 22 000 € TTC, livraison et installation comprises. La fourniture est supposée incluse (Hypothèse : … à confirmer).
  - Hypothèses de répartition : aucune enveloppe par ligne n'est fournie et aucune répartition chiffrée n'est proposée ici, faute de base de devis. La répartition reste à établir avec le client.
  - Total ou sous-total connu : 0 € TTC alloué sur 7 lignes, puisque toutes les enveloppes sont [NON FOURNI].
  - Écart ou solde provisoire : 22 000 € TTC − 0 € TTC = 22 000 € TTC non réparti. Ce solde n'est pas une marge disponible : il doit couvrir les 6 lignes neuves, la livraison, l'installation et les éventuelles interventions sur BIB-01, toutes à chiffrer.
  - Les enveloppes sont estimatives, à confirmer par devis.


Contrôle des délais

  - Date de pose et date de référence : installation le 15 avril 2027 (jeudi). Date de référence pour le contrôle [NON FOURNI].
  - CAN-01 : fabrication de 8 à 10 semaines ; préparation, livraison et transport [NON FOURNI]. Hypothèse : semaines calendaires, point de départ à la commande.
      Délai haut : 15 avril 2027 − 10 semaines (70 jours) = 4 février 2027.
      Délai bas : 15 avril 2027 − 8 semaines (56 jours) = 18 février 2027.
      Échéance retenue : le 4 février 2027, à avancer encore du temps de préparation et de livraison, non fourni.
  - TAP-01, TAB-01, FAU-01, LAM-01 : délais fournisseurs [NON FOURNI] ; date de commande non calculable. Formule : date de pose − délai fournisseur − préparation.
  - RID-01 : délai de confection et de pose de la tringle [NON FOURNI] ; date de commande non calculable. Le métré dépend de la fixation retenue.
  - BIB-01 : délai d'intervention (fixation, nettoyage) [NON FOURNI] ; à planifier avant l'installation du 15 avril 2027.
  - Risques :
      Date de référence absente : le retard éventuel ne peut pas être évalué.
      Hypothèse : si la date de référence est le 21 octobre 2026, le 4 février 2027 reste à 106 jours (15 semaines + 1 jour). L'échéance du canapé est donc à confirmer, pas en retard établi.
      Lignes sans délai fournisseur : évaluation impossible.


Caractéristiques à vérifier

  - CAN-01 : réaction au feu du revêtement et du garnissage ; abrasion du tissu, méthode et unité à relever (cycles Martindale ou doubles frottements, sans équivalence) ; codes d'entretien et déhoussabilité ; absence de cuir.
  - TAP-01 : résistance au glissement ou sous-couche ; consignes d'entretien ; tenue à l'usage ; réaction au feu selon pertinence.
  - TAB-01 : rayons des angles ; stabilité ; finition et consignes d'entretien ; absence de verre.
  - FAU-01 : réaction au feu ; abrasion, méthode et unité à relever ; codes d'entretien ; déhoussabilité ; stabilité ; absence de cuir.
  - LAM-01 : stabilité de l'embase ; matériaux du diffuseur (absence de verre) ; conformité électrique déclarée par le fabricant, à relever.
  - RID-01 : réaction au feu du tissu ; codes de lavage et retrait éventuel ; dispositifs sans cordon accessible ; capacité de charge de la tringle ou du rail et fixations.
  - BIB-01 : fixations murales selon la nature du support ; stabilité ; état et finition existante.
  - Toutes ces données sont à contrôler sur la documentation fabricant ; aucune valeur n'est présentée comme acquise.
  - Le professionnel responsable vérifie les règles applicables.


Questions pour le client

  - Le projet est-il bien un logement, et non un ERP ?
  - Quels sont les usages du séjour (repas, jeux de l'enfant, télévision, travail) ?
  - Quelles sont les dimensions du canapé (branches, profondeur, côté de l'angle), de la table basse, des fauteuils et des lampadaires, ou les dégagements de circulation souhaités ?
  - Les 30 cm de sol visible se mesurent-ils depuis les murs (tapis de 4,90 m × 3,60 m) ? Le tapis peut-il passer sous la bibliothèque, ou faut-il le réduire de ce côté ?
  - Quelles sont les dimensions et l'emplacement de la bibliothèque ? Est-elle fixée au mur ? Comporte-t-elle du verre ? Quelles interventions prévoir, et pour quel coût ?
  - Le refus du cuir inclut-il le simili-cuir ?
  - Pour les rideaux : combien de panneaux, quelle fixation (mur ou plafond), quelle tringle (fournie ou existante), quelle occultation, quelle garde au sol, quels débords ?
  - Quelles sont la nature et les dimensions des accès pour la livraison du canapé ?
  - Quelle répartition des 22 000 € TTC entre les lignes ? La fourniture est-elle bien incluse avec la livraison et l'installation ?
  - Quelle est la date de référence pour le contrôle des délais ?
  - Les 8 à 10 semaines du canapé sont-elles calendaires, comptées à partir de la commande, et livraison comprise ? Quel temps de préparation (validation, acompte) prévoir ?
  - Quels sont les délais fournisseurs des autres lignes ?

