# Transcript — skill interior-designers-ffe-schedule [fr] — claude-fable-5-1 — run 3

- model_id: `claude-fable-5-1` (provider `anthropic`)
- started_utc: 2026-10-21T06:57:16+00:00
- duration_s: 114.7
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

Pseudonymisez les données client et utilisez uniquement un outil approuvé par l'agence.

INTENTION

- Pièce : séjour, 4,2 m × 5,5 m, hauteur 2,60 m, une baie vitrée de 2,4 m de large. Lieu : Bordeaux.
- Occupants : un couple, un enfant de 3 ans, un chien qui perd ses poils.
- Type de projet : [NON FOURNI] — Hypothèse : logement (séjour familial), à confirmer.
- Autres données du brief à conserver : budget 22 000 € TTC, livraison et installation comprises ; installation le 15 avril 2027 ; délai de fabrication du canapé annoncé par les fournisseurs : 8 à 10 semaines ; goûts : bois clair, tons sable.
- Exclusions appliquées :
  - Verre → aucun plateau de table basse en verre, aucun diffuseur ou pied de lampadaire en verre, aucune étagère ou porte vitrée ajoutée à la bibliothèque, aucun accessoire en verre. Note : la baie vitrée est un élément du bâti, hors exclusion.
  - Cuir → aucun revêtement cuir ni similicuir sur canapé et fauteuils ; aucune garniture cuir sur table basse, lampadaires ou embrasses.
- Préférences appliquées (à vérifier, non promises) : bois clair pour structures et piétements ; tons sable pour textiles.

LISTE MOBILIER ET ÉQUIPEMENTS

| Repère | Élément | Quantité | Dimensions cibles et calculs | Matériaux / exigences à vérifier | Enveloppe estimative à confirmer par devis (HT/TTC) | Délai / commande au plus tard | Statut |
|---|---|---|---|---|---|---|---|
| CAN-01 | Canapé d'angle 5 places | 1 | Dimensions fournies : [NON FOURNI]. Hypothèse : 55 à 60 cm par place → 5 places ≈ 2,75 à 3,00 m de longueur d'assise développée, à répartir sur les deux branches de l'angle. Contrainte : mur long 5,5 m, mur court 4,2 m, baie de 2,4 m à ne pas obstruer. Profondeur, hauteur de dossier, sens de l'angle : [NON FOURNI]. | Sans cuir. Tissu déhoussable et lavable, exigence à vérifier (chien, enfant 3 ans). Résistance à l'abrasion à vérifier (voir rubrique caractéristiques). Structure bois clair souhaitée. Passage de porte et accès pour livraison à vérifier. | Hypothèse : 8 000 € TTC | 8 à 10 semaines de fabrication. Au plus tard : 15 avril 2027 − 10 semaines = 4 février 2027 ; avec 8 semaines : 18 février 2027. Préparation et transport : [NON FOURNI], à déduire en plus. | Neuf |
| TAP-01 | Tapis | 1 | Longueur : 5,5 m − 2 × 0,30 m (30 cm) = 4,9 m. Largeur : 4,2 m − 2 × 0,30 m (30 cm) = 3,6 m. Hypothèse : le dégagement de 30 cm est pris sur les murs nus ; si la bibliothèque BIB-01 est au sol sur une longueur, le tapis s'arrête devant elle et la dimension est à recalculer. Format 4,9 × 3,6 m probablement hors standard : fabrication sur mesure ou raccord à vérifier. | Entretien facilité face aux poils de chien, exigence à vérifier. Résistance au glissement et sous-tapis à vérifier. Tons sable. | Hypothèse : 2 200 € TTC | Délai fournisseur : [NON FOURNI]. Commande = 15 avril 2027 − délai − préparation ; calcul impossible. | Neuf |
| TAB-01 | Table basse | 1 | [NON FOURNI]. Paramètres nécessaires : dimensions du canapé CAN-01, dégagement souhaité entre assise et table, hauteur d'assise. Hypothèse : dégagement de 40 à 45 cm entre canapé et table, hauteur de plateau proche de l'assise. | Sans verre. Angles arrondis ou bords adoucis, exigence à vérifier (enfant 3 ans). Stabilité à vérifier. Bois clair souhaité ; finition résistante aux taches à vérifier. | Hypothèse : 1 500 € TTC | Délai fournisseur : [NON FOURNI]. Calcul impossible. | Neuf |
| FAU-01 | Fauteuil | 2 | [NON FOURNI]. À coordonner avec CAN-01 et le passage vers la baie (2,4 m). Hypothèse : largeur hors tout 70 à 85 cm par fauteuil, à confirmer sur plan. | Sans cuir. Tissu déhoussable ou facile à nettoyer, exigence à vérifier (chien). Abrasion à vérifier. Piétement bois clair souhaité. | Hypothèse : 2 × 1 400 € TTC = 2 800 € TTC | Délai fournisseur : [NON FOURNI]. Calcul impossible. | Neuf |
| LUM-01 | Lampadaire | 2 | [NON FOURNI]. Hauteur sous plafond 2,60 m : hauteur du lampadaire et débord de l'abat-jour à vérifier par rapport aux fauteuils et au canapé. | Sans verre (diffuseur, pied). Stabilité et poids de la base à vérifier (enfant 3 ans, chien). Câble et interrupteur hors de portée à vérifier. Bois clair souhaité. | Hypothèse : 2 × 450 € TTC = 900 € TTC | Délai fournisseur : [NON FOURNI]. Calcul impossible. | Neuf |
| RID-01 | Rideaux pour la baie | 1 lot (nombre de panneaux à définir) | Largeur de baie : 2,4 m. Longueur de tringle ou rail : Hypothèse : 2,4 m + débord de 0,20 à 0,30 m de chaque côté = 2,8 à 3,0 m. Hauteur de tombée : à prendre depuis la fixation (plafond 2,60 m ou linteau), hauteur de la baie [NON FOURNI]. Largeur de tissu : Hypothèse : coefficient d'ampleur 2 → 5,6 à 6,0 m de tissu développé. | Tissu lavable, exigence à vérifier (poils de chien). Tons sable. Mode d'ouverture, occultation ou voilage : [NON FOURNI]. Fixation de la tringle au mur ou au plafond à vérifier. | Hypothèse : 2 500 € TTC (tissu, confection, tringle, pose) | Délais tissu, confection et pose : [NON FOURNI]. Calcul impossible. | Neuf |
| BIB-01 | Bibliothèque en chêne | 1 | [NON FOURNI] (longueur, hauteur, profondeur, emplacement). Impact sur TAP-01 et sur l'implantation de CAN-01 à vérifier. | Chêne existant, couleur à rapprocher du souhait « bois clair » (contrôle visuel). Fixation murale et stabilité à vérifier (enfant 3 ans). Interventions prévues : [NON FOURNI] (nettoyage, déplacement, fixation, remise en état). | Pas d'achat. Frais éventuels de déplacement, nettoyage, fixation ou adaptation : [NON FOURNI], à ne pas supposer nuls. | Interventions : [NON FOURNI]. Si déplacement ou fixation, à planifier avant la pose du tapis TAP-01 et avant le 15 avril 2027. | Existant – réemploi |
| LIV-01 | Livraison et installation (toutes lignes neuves) | 1 lot | — | Accès à la pièce, ascenseur, escalier, largeur de portes : [NON FOURNI]. | Hypothèse : 1 500 € TTC (si non inclus dans les devis de chaque ligne) | Date cible : 15 avril 2027. | Prestation (hors mobilier) |

Rapprochement :
- Canapé d'angle 5 places → CAN-01 (1 objet, 1 ligne)
- Tapis avec 30 cm de sol visible → TAP-01 (1 objet, 1 ligne)
- Table basse → TAB-01 (1 objet, 1 ligne)
- 2 fauteuils → FAU-01 (2 objets, 1 ligne)
- 2 lampadaires → LUM-01 (2 objets, 1 ligne)
- Rideaux pour la baie → RID-01 (1 lot, 1 ligne)
- Bibliothèque en chêne, à conserver → BIB-01 (1 objet, 1 ligne, hors achat)
- Aucun élément à retirer n'est mentionné dans le brief.
- Total : 8 objets ou lots sur 7 lignes mobilier et équipements, plus 1 ligne de prestation LIV-01.

CONTRÔLE DU BUDGET

- Budget client et périmètre : 22 000 € TTC, livraison et installation comprises (fourniture + livraison + installation).
- Hypothèses de répartition (toutes en TTC, non des prix de marché) :
  CAN-01 8 000 + TAP-01 2 200 + TAB-01 1 500 + FAU-01 2 800 + LUM-01 900 + RID-01 2 500 + LIV-01 1 500
- Sous-total connu des enveloppes : 8 000 + 2 200 + 1 500 + 2 800 + 900 + 2 500 + 1 500 = 19 400 € TTC.
- Écart ou solde provisoire : 22 000 € TTC − 19 400 € TTC = 2 600 € TTC.
- Coûts restant à confirmer, non chiffrés dans le sous-total : interventions sur BIB-01 ; sous-tapis TAP-01 ; sur-mesure éventuel du tapis ; nombre de panneaux et type de confection RID-01 ; accès et manutention LIV-01. Le solde de 2 600 € TTC n'est donc pas une marge disponible.
- Les enveloppes sont estimatives, à confirmer par devis.

CONTRÔLE DES DÉLAIS

- Date de pose : 15 avril 2027. Date de référence pour le contrôle : [NON FOURNI].
- Unité du délai canapé : « 8 à 10 semaines » ; semaines calendaires ou ouvrées non précisé, hypothèse de calcul : semaines calendaires, à confirmer avec le fournisseur.
- Par repère :
  - CAN-01 : commande au plus tard = 15 avril 2027 − 10 semaines (70 jours) = 4 février 2027 ; à 8 semaines (56 jours) = 18 février 2027. Préparation (validation du tissu, transport, stockage) : [NON FOURNI], à retrancher en plus de ces dates. Retenir la borne prudente du 4 février 2027.
  - TAP-01, TAB-01, FAU-01, LUM-01 : délai fournisseur [NON FOURNI] ; formule : commande = 15 avril 2027 − délai − préparation ; calcul impossible.
  - RID-01 : délais tissu, confection et pose [NON FOURNI] ; calcul impossible. La pose de la tringle doit précéder la pose des rideaux.
  - BIB-01 : interventions [NON FOURNI] ; si déplacement ou fixation, à réaliser avant TAP-01 et avant le 15 avril 2027.
  - LIV-01 : séquence conseillée à confirmer : BIB-01 → TAP-01 → CAN-01, FAU-01, TAB-01 → LUM-01 → RID-01.
- Risques : échéance à confirmer pour CAN-01 (le 4 février 2027 n'est comparable à aucune date de référence fournie) ; évaluation impossible pour les autres lignes faute de délais ; aucun retard établi à ce stade.

CARACTÉRISTIQUES À VÉRIFIER

- CAN-01, FAU-01 : réaction au feu de la mousse et du tissu selon le type de projet ; résistance à l'abrasion du tissu avec méthode et unité indiquées par le fabricant (cycles Martindale ou doubles frottements, sans équivalence supposée) ; codes ou consignes d'entretien et lavabilité des housses ; stabilité ; absence de cuir dans toutes les parties.
- TAP-01 : réaction au feu selon pertinence ; résistance au glissement (tapis et sous-tapis) ; consignes d'entretien et comportement aux poils ; faisabilité du format 4,9 × 3,6 m.
- TAB-01 : absence de verre ; traitement des angles ; stabilité et résistance du plateau aux taches et chocs ; finition du bois.
- LUM-01 : absence de verre ; poids et stabilité de la base ; conformité électrique indiquée par le fabricant ; puissance et type d'ampoule.
- RID-01 : réaction au feu selon pertinence ; consignes d'entretien et lavabilité ; charge admissible de la tringle ou du rail et fixations ; rétrécissement au lavage.
- BIB-01 : fixation murale et stabilité ; état du chêne et compatibilité visuelle avec le bois clair souhaité.
- Le professionnel responsable vérifie les règles applicables.

QUESTIONS POUR LE CLIENT

1. Type de projet : s'agit-il bien d'un logement privé (hypothèse retenue) ?
2. Date de référence pour le contrôle des délais (date de validation du brief ou de la commande) ?
3. Canapé CAN-01 : dimensions imposées, sens de l'angle, profondeur d'assise ? Les 8 à 10 semaines sont-elles des semaines calendaires ou ouvrées ? Quels sont les délais de transport et de préparation à ajouter ?
4. Délais fournisseurs pour TAP-01, TAB-01, FAU-01, LUM-01 et RID-01 (tissu, confection, pose) ?
5. Bibliothèque BIB-01 : dimensions, emplacement, interventions prévues (déplacement, nettoyage, fixation) et budget associé ?
6. Tapis TAP-01 : le dégagement de 30 cm s'applique-t-il aussi devant la bibliothèque, ou le tapis s'arrête-t-il devant elle ? Acceptez-vous un sur-mesure ou un raccord si le format 4,9 × 3,6 m n'existe pas en standard ?
7. Rideaux RID-01 : hauteur de la baie, fixation au plafond ou au mur, occultant ou voilage, nombre de panneaux souhaité ? Validez-vous l'hypothèse de débord 0,20 à 0,30 m et d'ampleur 2 ?
8. Table basse TAB-01 et fauteuils FAU-01 : dimensions souhaitées ou à proposer sur plan ? Confirmez-vous les angles arrondis pour la table basse ?
9. Lampadaires LUM-01 : lampadaires d'ambiance ou de lecture, hauteur souhaitée ?
10. Accès pour la livraison LIV-01 : étage, ascenseur, largeur de porte et de couloir ?
11. Budget : validez-vous la répartition proposée en hypothèse (19 400 € TTC de sous-total, solde 2 600 € TTC non disponible tant que les coûts manquants ne sont pas chiffrés) ? Les devis fournisseurs seront-ils reçus en HT ou en TTC ?
12. Exclusions : le refus du verre vise-t-il aussi les petits éléments (lampadaires, accessoires) ? Le refus du cuir inclut-il le similicuir ?
13. Préférences : le chêne existant de la bibliothèque est-il considéré comme « bois clair » à vos yeux, ou faut-il s'en écarter pour le mobilier neuf ?

