# Transcript — skill lawyers-nda-review [fr] — claude-opus-5-5 — run 3

- model_id: `claude-opus-5-5` (provider `anthropic`)
- started_utc: 2026-10-21T06:59:45+00:00
- duration_s: 58.7
- exit_code: 0
- attempts: 1
- completed: True
- rubric_sha256: fedca4f8577f197bd01ad603962a443ad542a8ef958d899feb9c939765c6c33a
- skill_sha256: e60e5b35d88c9d6f92cdb588668ceee4e5519cf62381364b6f01795d180f57a7

## Query (verbatim, from query file)

````text
<skill_instructions>
---
name: lawyers-nda-review
description: "Utilisez-la quand vous collez un accord de confidentialité et la politique du client pour obtenir les écarts, les clauses manquantes ou conformes et des propositions de rédaction."
---

# Revue d'un accord de confidentialité selon votre politique

## Ce qu'elle fait

Elle compare chaque clause du projet d'accord de confidentialité à la politique de négociation du client, seule référence de la revue. Elle relève les écarts et les clauses exigées mais absentes, propose des rédactions et distingue les clauses déjà conformes, sans les renégocier. Elle prépare un document de travail pour l'avocat responsable en France, et non une consultation juridique.

## Ce dont elle a besoin

- Le projet d'accord, avec ses numéros de clauses, ses intitulés et les annexes utiles ; préciser si seuls des extraits sont fournis.
- La politique du client : positions attendues, replis autorisés, points non négociables et éventuelle échelle de risque.
- Le contexte disponible : partie représentée, objet de l'opération, caractère unilatéral ou réciproque de la confidentialité.
- Les consignes du cabinet concernant les données, avec des noms de parties pseudonymisés et sans données identifiantes inutiles.

Ne pas attendre de complément : marquer les éléments manquants [NON FOURNI] et les lister dans les questions finales. Une hypothèse raisonnable doit commencer par « Hypothèse : … » ; ne jamais supposer une position du client, le contenu d'une clause absente ou un fait juridique. Sans politique, livrer toutes les sections en indiquant que la conformité et les écarts ne sont pas évaluables.

## Procédure

1. Toujours livrer la sortie complète dès la première réponse, en une seule passe. Ne jamais interrompre la rédaction pour poser des questions ou attendre une confirmation ; ne retenir aucune section ni aucun calcul. Signaler les données manquantes ou ambiguës par [NON FOURNI] ou « Hypothèse : … ». Regrouper toutes les questions dans la dernière section, « Questions pour l'avocat responsable ».
2. Insérer dans la synthèse ce rappel d'une ligne : « Pseudonymisez les parties, retirez les données identifiantes inutiles et utilisez uniquement un outil approuvé par le cabinet. » Ce rappel n'est pas une condition préalable : ne jamais refuser ni suspendre la revue pour ce motif. Éviter de reproduire les identifiants personnels inutiles.
3. Inventorier les clauses du projet en conservant leurs numéros et intitulés, puis les exigences distinctes de la politique. Identifier les extraits, annexes absentes et passages illisibles ; ne pas traiter un document partiel comme un accord complet.
4. Rapprocher chaque clause des exigences correspondantes. Comparer uniquement à la politique fournie, sans imposer de pratique de marché, de préférence personnelle ou de position juridique extérieure. Si elle est muette ou contradictoire, inscrire « Non évaluable — politique muette ou contradictoire » dans le tableau, sans conclure à un écart ni à une conformité ; réserver l'arbitrage aux questions finales.
5. Reproduire exactement les chiffres, dates, heures, durées, délais, montants et quantités de l'entrée dans les passages qui les rapportent. Ne pas normaliser leur présentation. Distinguer clairement les valeurs du projet, celles de la politique et celles proposées en remplacement ; montrer l'opération de tout calcul dérivé, y compris les totaux.
6. Inscrire chaque écart constaté dans le tableau avec les six colonnes prévues. Utiliser d'abord l'échelle de risque de la politique ; à défaut, appliquer les critères suivants, uniquement à partir de son contenu :
   - Élevé : point non négociable méconnu ou limite explicite dépassée, y compris au-delà du repli autorisé.
   - Moyen : position attendue non respectée, mais rédaction située dans un repli expressément autorisé.
   - Faible : exigence rédactionnelle explicite non respectée, sans effet sur la position de fond.
   - Si ces critères ne permettent pas de classer l'écart, inscrire « À confirmer » et soumettre le niveau de risque à l'avocat responsable ; ne pas inventer de gravité.
   Ajouter dans la cellule de risque un motif bref fondé sur la politique.
7. Proposer pour chaque écart une rédaction alignée sur la position attendue, ou une suppression si la politique l'exige. Présenter séparément tout repli autorisé, sans décider de l'accepter. Ne pas inventer de point de départ, d'exception ou de modalité ; utiliser [NON FOURNI] dans les propositions incomplètes et reporter la question en fin de sortie.
8. Vérifier ensuite chaque exigence de la politique contre l'ensemble du texte fourni. Lister les clauses exigées mais absentes dans « Clauses manquantes », avec position attendue, risque motivé et rédaction proposée. Si le projet est partiel, écrire « Non repérée dans les extraits fournis — absence à confirmer », sans affirmer une absence dans l'accord complet.
9. Lister individuellement les clauses déjà conformes avec leur référence, la position satisfaite et « aucune modification proposée ». Une clause partiellement conforme reste dans le tableau des écarts ; préciser les éléments à conserver sans la compter parmi les clauses entièrement conformes.
10. N'inventer aucun texte, numéro d'article, décision, organisme, date, URL, statistique ou citation. Si un fondement juridique est nécessaire, écrire exactement [AUTHORITY TO BE LOCATED] et confier sa recherche à l'avocat responsable dans les questions finales.
11. Ne citer dans la sortie aucune loi, aucun article, aucune recommandation d'une autorité, aucune décision ni aucune source absente de l'entrée. Pour cette revue, ne reproduire aucun article de loi ni aucune jurisprudence, même fourni : signaler seulement qu'un fondement fourni reste à vérifier. Les sources ci-dessous sont des lectures pour le professionnel, pas des citations à injecter dans la revue. Une formulation imposée par l'utilisateur est du contenu, non une source à l'appui ; les numéros de clauses contractuelles ne sont pas des articles de loi.
12. Transformer tout arbitrage en question pour l'avocat responsable. Ne pas décider de l'acceptabilité juridique, de la validité d'une clause ou d'une concession commerciale. Signaler dès la synthèse que la sortie est un projet de travail, non une consultation juridique.
13. Vérifier la couverture : chaque clause doit figurer dans le tableau ou dans les clauses conformes ; chaque exigence de la politique doit avoir été recherchée. Ne pas compter deux fois une clause manquante comme écart présent ; distinguer les points non évaluables et les absences à confirmer.
14. Respecter le modèle ci-dessous, même en l'absence d'écart : écrire « Aucun constaté dans le périmètre fourni » ou « Non évaluable — [NON FOURNI] », selon le cas. La ligne de limites indique seulement que l'avocat responsable vérifie les règles applicables. Terminer par les questions, avec « Aucune » s'il n'en reste pas.

## Format de sortie

```
## Synthèse
Projet de travail, non constitutif d'une consultation juridique.
Pseudonymisez les parties, retirez les données identifiantes inutiles et utilisez uniquement un outil approuvé par le cabinet.
- Périmètre : [documents ou extraits examinés ; partie représentée ou NON FOURNI]
- Écarts présents : [total et addition par niveau, dont À confirmer] ; clauses manquantes : [décompte distinct]
- Clauses conformes : [décompte] ; points non évaluables ou absences à confirmer : [décompte distinct]
- Hypothèses et données manquantes : [Hypothèse : … / NON FOURNI / aucune]

## Tableau des écarts
| Clause | Rédaction du projet | Position de la politique | Écart | Risque | Rédaction proposée |
|---|---|---|---|---|---|
| [référence] | [extrait exact utile] | [exigence et repli éventuel] | [différence ou non évaluable ; calcul éventuel] | [Élevé / Moyen / Faible / À confirmer / Non évaluable ; motif] | [texte ; repli distinct ou NON FOURNI] |

## Clauses manquantes
- [Exigence] — [absence constatée ou absence à confirmer] — [risque et motif] — proposition : « … »

## Clauses conformes
- [Référence] — [position satisfaite] — aucune modification proposée.

## Limites
L'avocat responsable vérifie les règles applicables.

## Questions pour l'avocat responsable
- [Arbitrages, éléments NON FOURNI, hypothèses et absences à confirmer, fondements à rechercher ; ou Aucune]
```

## Limites

- Périmètre : pratique française uniquement ; ne pas transposer cette revue à la Belgique, à la Suisse ou au Canada.
- Ne jamais remplacer la politique du client par une norme extérieure ni présenter une incertitude comme une conformité acquise.
- Ne jamais inventer de référence juridique ; employer [AUTHORITY TO BE LOCATED] si une recherche est nécessaire.
- Ne jamais présenter la sortie comme une consultation juridique, une validation de l'accord ou une autorisation de signature.
- L'avocat responsable vérifie le droit applicable, les règles de la profession, la validité des clauses, les qualifications de risque et la cohérence des propositions avec l'accord complet. Il tranche les arbitrages et valide toute rédaction avant envoi ou signature.
- Le secret professionnel de l'avocat est la référence. Pseudonymiser les parties, retirer les données identifiantes inutiles et utiliser uniquement un outil approuvé selon la politique du cabinet ; la pseudonymisation ne remplace pas cette approbation.
- Le professionnel vérifie notamment les conditions d'hébergement et de réutilisation des données. Dans la revue, rappeler la confidentialité sans en faire un motif de refus ou de pause.
- Lecture pour le professionnel : Conseil national des barreaux — Grille de lecture IA, 1re édition (juin 2025) — https://www.cnb.avocat.fr/medias/cnb-grille-lecture-intelligence-aartificielle-2025-68f775b81ba5b2.65545272.pdf (juin 2025 ; consulté le 2026-10-21)
- Cette grille compare des outils d'IA juridique sur l'hébergement et la réutilisation des données.

voir references/checklist.md

## Exemple

Entrée fictive :

```
Partie représentée : société Modèle ; autre partie : société Exemple. Projet complet fourni.
Politique : confidentialité réciproque ; non-sollicitation interdite, point non négociable.
Clause A : « Chaque partie protège les informations confidentielles reçues de l'autre. »
Clause B : « Chaque partie s'interdit de solliciter le personnel de l'autre. »
```

Sortie abrégée :

```
## Synthèse
Projet de travail, non constitutif d'une consultation juridique ; périmètre : projet complet, société Modèle représentée.
Pseudonymisez les parties, retirez les données identifiantes inutiles et utilisez uniquement un outil approuvé par le cabinet.
## Tableau des écarts
| Clause | Rédaction du projet | Position de la politique | Écart | Risque | Rédaction proposée |
|---|---|---|---|---|---|
| B | « Chaque partie s'interdit de solliciter le personnel de l'autre. » | Non-sollicitation interdite | Interdiction non respectée | Élevé : point non négociable | Supprimer la clause B. |
## Clauses manquantes
Aucune constatée dans le périmètre fourni.
## Clauses conformes
Clause A — confidentialité réciproque — aucune modification proposée.
## Limites
L'avocat responsable vérifie les règles applicables.
## Questions pour l'avocat responsable
Aucune.
```
</skill_instructions>

Follow the skill instructions above for the user's request below.

User request:
Revois cet accord de confidentialité au regard de notre politique et donne-moi le tableau des écarts et les propositions de rédaction.
Client : Exemple Robotique SAS (fictive), France, partie DIVULGATRICE (accord unilatéral). Objet : évaluer un partenariat industriel.
Projet de l'autre partie :
Art. 1 Informations confidentielles : toute information, quelle qu'en soit la forme, marquée ou non comme confidentielle.
Art. 3 Le Destinataire peut communiquer les informations aux sociétés de son groupe, à ses sous-traitants et à ses conseils.
Art. 5 Durée : 2 ans à compter de la signature.
Art. 7 Droit français ; compétence exclusive des tribunaux de Paris.
Art. 9 Chaque partie s'interdit de solliciter les salariés de l'autre pendant 12 mois.
Politique du client : informations couvertes quelle qu'en soit la forme, marquées ou non ; communication uniquement aux personnes ayant besoin d'en connaître et liées par une obligation écrite de confidentialité au moins équivalente ; durée 5 ans ; aucune clause de non-sollicitation dans un accord de confidentialité ; droit français, tribunaux de Paris ou de Lyon acceptables ; restitution ou destruction sur demande avec attestation écrite ; clause précisant qu'aucune licence n'est concédée.
````

## Output (verbatim stdout, session metadata stripped)

SYNTHÈSE
Projet de travail, non constitutif d'une consultation juridique.
Pseudonymisez les parties, retirez les données identifiantes inutiles et utilisez uniquement un outil approuvé par le cabinet.

  - Périmètre : extraits du projet de l'autre partie (Art. 1, 3, 5, 7, 9) et politique du client. La numérotation est discontinue (Art. 2, 4, 6, 8 et suivants absents) : le projet est traité comme partiel. Partie représentée : le client, partie divulgatrice, dans un accord unilatéral. Objet : évaluer un partenariat industriel.
  - Écarts présents : 3 au total, soit 2 Élevé (Art. 3, Art. 9) + 0 Moyen + 0 Faible + 1 À confirmer (Art. 5) = 3.
  - Clauses manquantes : 2 (restitution ou destruction ; absence de licence), toutes deux en absence à confirmer.
  - Clauses conformes : 2 (Art. 1, Art. 7).
  - Points non évaluables ou absences à confirmer : 0 clause entièrement non évaluable ; 1 sous-point non évaluable (point de départ de la durée, Art. 5) ; 2 absences à confirmer (voir Clauses manquantes).
  - Hypothèses et données manquantes :
      Hypothèse : la numérotation discontinue indique des articles non fournis, et non une erreur de numérotation.
      [NON FOURNI] Texte des Art. 2, 4, 6, 8 et suivants ; annexes éventuelles.
      [NON FOURNI] Échelle de risque, points non négociables et replis autorisés de la politique.
      [NON FOURNI] Point de départ de la durée selon la politique.


TABLEAU DES ÉCARTS
(Tableau présenté en blocs pour la lecture en terminal. Chaque bloc reprend les six colonnes.)

  Écart 1
  Clause : Art. 3 (communication des informations)
  Rédaction du projet : « Le Destinataire peut communiquer les informations aux sociétés de son groupe, à ses sous-traitants et à ses conseils. »
  Position de la politique : « communication uniquement aux personnes ayant besoin d'en connaître et liées par une obligation écrite de confidentialité au moins équivalente ». Aucun repli fourni.
  Écart : le projet autorise la communication à trois catégories entières de destinataires. Il ne pose ni condition de besoin d'en connaître, ni exigence d'une obligation écrite de confidentialité au moins équivalente.
  Risque : Élevé. La politique fixe une limite explicite (« uniquement »), que le projet dépasse.
  Rédaction proposée : « Le Destinataire ne peut communiquer les Informations Confidentielles qu'aux seules personnes ayant besoin d'en connaître et liées par une obligation écrite de confidentialité au moins équivalente à celle prévue au présent accord. »
  Variante si le client souhaite conserver les catégories du projet : « Le Destinataire ne peut communiquer les Informations Confidentielles qu'aux sociétés de son groupe, à ses sous-traitants et à ses conseils, et uniquement à ceux d'entre eux ayant besoin d'en connaître et liés par une obligation écrite de confidentialité au moins équivalente à celle prévue au présent accord. »
  Repli : [NON FOURNI], la politique n'en prévoit aucun.

  Écart 2
  Clause : Art. 5 (durée)
  Rédaction du projet : « Durée : 2 ans à compter de la signature. »
  Position de la politique : « durée 5 ans ». Ni point de départ ni repli fournis.
  Écart : 5 ans − 2 ans = 3 ans de moins que la position attendue.
  Point de départ : le projet retient « la signature » et la politique est muette. Non évaluable — politique muette ou contradictoire.
  Autre point : le projet ne précise pas si « Durée » vise l'accord ou les obligations de confidentialité, et la politique ne le précise pas davantage.
  Risque : À confirmer. La politique ne qualifie pas la durée de point non négociable ni de limite minimale explicite, et ne prévoit aucun repli. Les critères ne permettent donc pas de classer l'écart.
  Rédaction proposée : « Durée : 5 ans à compter de [NON FOURNI]. »
  Le point de départ « la signature » figure au projet mais n'est pas validé par la politique. Il est soumis à l'avocat responsable.
  Repli : [NON FOURNI].

  Écart 3
  Clause : Art. 9 (non-sollicitation)
  Rédaction du projet : « Chaque partie s'interdit de solliciter les salariés de l'autre pendant 12 mois. »
  Position de la politique : « aucune clause de non-sollicitation dans un accord de confidentialité ». Aucun repli fourni.
  Écart : le projet contient une clause de non-sollicitation, d'une durée de 12 mois, alors que la politique l'exclut. La clause est réciproque (« chaque partie ») et engagerait donc aussi le client, dans un accord présenté comme unilatéral.
  Risque : Élevé. La politique pose une exclusion explicite (« aucune clause »), que le projet méconnaît. La politique ne la qualifie toutefois pas expressément de « non négociable » (voir Questions).
  Rédaction proposée : supprimer l'article 9.
  Repli : [NON FOURNI], la politique n'en prévoit aucun.


CLAUSES MANQUANTES

  - Restitution ou destruction sur demande, avec attestation écrite.
    Constat : non repérée dans les extraits fournis — absence à confirmer.
    Risque : À confirmer. La politique exige la clause sans la qualifier de non négociable ni prévoir de repli.
    Proposition : « Sur demande de la partie divulgatrice, le Destinataire restitue ou détruit les Informations Confidentielles, [au choix de : NON FOURNI], dans un délai de [NON FOURNI], et lui en remet une attestation écrite. »

  - Clause précisant qu'aucune licence n'est concédée.
    Constat : non repérée dans les extraits fournis — absence à confirmer.
    Risque : À confirmer. Même motif.
    Proposition : « Aucune disposition du présent accord ne peut être interprétée comme concédant au Destinataire une quelconque licence sur les Informations Confidentielles. »


CLAUSES CONFORMES

  - Art. 1 — informations couvertes « quelle qu'en soit la forme, marquée[s] ou non comme confidentielle[s] », conformément à la politique — aucune modification proposée.
  - Art. 7 — droit français et compétence des tribunaux de Paris, l'une des deux juridictions acceptables selon la politique (Paris ou Lyon) — aucune modification proposée.


LIMITES
L'avocat responsable vérifie les règles applicables.


QUESTIONS POUR L'AVOCAT RESPONSABLE

  1. Merci de transmettre les Art. 2, 4, 6, 8 et suivants, ainsi que les annexes éventuelles. Ils permettront de confirmer ou d'écarter l'absence des clauses de restitution ou destruction et d'absence de licence, et de contrôler les autres clauses au regard de la politique.
  2. La politique comporte-t-elle une échelle de risque, des points non négociables ou des replis autorisés ? Selon la réponse, les qualifications Élevé (Art. 3, Art. 9) et À confirmer (Art. 5, clauses manquantes) seront à revoir.
  3. Art. 3 : faut-il retenir la rédaction générale (personnes ayant besoin d'en connaître) ou conserver les trois catégories du projet (groupe, sous-traitants, conseils) en leur appliquant les conditions de la politique ?
  4. Art. 5 : quel point de départ retenir (signature ou autre) ? Les 5 ans de la politique visent-ils la durée de l'accord ou celle des obligations de confidentialité ?
  5. Art. 9 : l'exclusion de la non-sollicitation est-elle un point non négociable ? Le caractère réciproque de la clause, dans un accord unilatéral, appelle-t-il une observation particulière ?
  6. Clause de restitution ou destruction : qui choisit entre restitution et destruction ? Quel délai fixer ? Faut-il prévoir des exceptions, par exemple pour des copies conservées ? La politique n'en dit rien.
  7. Clause d'absence de licence : son périmètre doit-il viser uniquement les Informations Confidentielles ou aussi d'autres droits ? La politique se limite à « aucune licence ».
  8. Arbitrage et validation de l'ensemble des rédactions proposées avant envoi à l'autre partie.

