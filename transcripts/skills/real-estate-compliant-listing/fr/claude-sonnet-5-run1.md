# Transcript — skill real-estate-compliant-listing [fr] — claude-sonnet-5 — run 1

- model_id: `claude-sonnet-5` (provider `anthropic`)
- started_utc: 2026-10-21T06:04:41+00:00
- duration_s: 80.9
- exit_code: 0
- attempts: 1
- completed: True
- rubric_sha256: e115806a7c26228bf311ae90494110ac918c84a4f2f53d61d90fb44083c90ba2
- skill_sha256: fcf6f6bd58100350217913780a449c429429893361c0bd7e020b5ec78fb5b992

## Query (verbatim, from query file)

````text
<skill_instructions>
---
name: real-estate-compliant-listing
description: "Utilisez-la quand vous collez les données d'un bien à vendre et les notes du vendeur pour obtenir une annonce, un texte pour réseaux sociaux et une liste des modifications."
---

# Annonce immobilière conforme et sans discrimination

## Ce qu'elle fait

Cet outil prépare une annonce de vente en France, un texte pour les réseaux sociaux et une liste vérifiable des modifications. Il décrit le bien, sans cibler un acquéreur, et écarte les promesses ainsi que les caractéristiques non établies. Les informations manquantes ou contradictoires sont signalées pour validation par le responsable de l'agence.

## Ce dont elle a besoin

- Le type de bien, la commune ou le quartier, la surface et les documents qui les établissent.
- Le prix, la partie supportant les honoraires et, à la charge de l'acquéreur, les prix honoraires inclus et hors honoraires ainsi que le pourcentage TTC.
- La classe du DPE et le document correspondant.
- Le statut de copropriété ; le cas échéant, le nombre de lots, les charges annuelles et l'existence éventuelle d'une procédure en cours.
- Les caractéristiques documentées : pièces, étage, extérieurs, revêtements, équipements, travaux et autorisations.
- Les notes du vendeur, les formulations à reprendre et les désaccords entre ces notes et les documents.
- Les éventuelles contraintes du portail et les mentions communiquées par l'agence.

Les éléments manquants sont marqués [NON FOURNI] et listés à la fin, sans question préalable.
Une « Hypothèse : … » peut préciser un choix de présentation, jamais remplacer une donnée du bien ou une information obligatoire.

## Procédure

1. Livrer toujours la réponse complète dès la première réponse, avec les cinq sections prévues.
   Ne jamais interrompre la rédaction pour poser une question ou attendre une confirmation.
   Ne retenir aucune section ni aucun calcul : si un calcul est impossible, donner sa formule et les données manquantes.
   Employer [NON FOURNI] pour les absences et ambiguïtés factuelles ; regrouper toutes les questions à la fin de « Avant publication ».
2. Vérifier le périmètre : vente en France uniquement.
   Si le dossier relève d'un autre marché ou d'une location, livrer les cinq sections en signalant le hors-périmètre, sans adapter ni inventer les règles locales.
3. Relever les données fournies, leur provenance et leurs éventuelles contradictions.
   Recopier exactement chaque chiffre, date, heure et quantité repris de l'entrée, sans arrondi ni conversion, en conservant le format des montants.
   Ne pas publier une donnée douteuse pour satisfaire cette règle : conserver ses valeurs exactes dans le signalement du conflit.
   Ne pas recopier dans les textes publics les coordonnées ou autres données personnelles inutiles.
4. Présenter l'arithmétique de chaque valeur calculée dans « Mentions obligatoires à vérifier ».
   Honoraires = prix honoraires inclus − prix hors honoraires.
   Pourcentage TTC = honoraires TTC ÷ prix hors honoraires × 100.
   Remplacer les termes par les valeurs fournies et afficher le résultat ; identifier toute valeur dérivée comme calculée.
   Si le caractère TTC, une donnée ou la base applicable est incertain, ne pas supposer le résultat : écrire [NON FOURNI] et demander confirmation à la fin.
   Si un résultat contredit un chiffre fourni, montrer les deux sans corriger silencieusement l'entrée.
5. Décrire le bien, jamais l'acquéreur ou l'occupant idéal.
   Repérer toute référence à la situation de famille, la religion, l'origine nationale, la nationalité, l'âge, le handicap, le sexe, la race ou la couleur de peau, la source de revenus ou tout autre critère personnel.
   Supprimer ces références ou les remplacer par des caractéristiques neutres déjà établies dans le dossier.
   « Idéal pour une jeune famille » ne devient « trois chambres » que si ces chambres sont effectivement documentées.
   Supprimer la proximité d'une église, d'un temple ou d'un autre lieu de culte utilisée comme argument de ciblage.
6. Retirer des deux textes publics les allégations invérifiables et les promesses.
   Cela comprend « quartier le plus sûr », « meilleures écoles du secteur » et « plus-value garantie ».
   Les signaler dans la liste des modifications ; ne conserver une affirmation factuelle que si les éléments fournis l'établissent.
7. Distinguer les faits établis des croyances du vendeur.
   Vérifier notamment le revêtement non identifié, les travaux sans autorisation établie, les équipements loués ou acquis et les écarts de surface.
   Omettre toute caractéristique incertaine des textes publics ; pour une mention obligatoire incertaine, utiliser [NON FOURNI].
   Ne choisir aucune valeur parmi des données contradictoires ; citer les valeurs exactes dans le signalement.
   Reporter chaque incertitude dans « Supprimé ou modifié » et dans les points à confirmer.
8. Contrôler les mentions de l'annonce, en indiquant pour chacune « présent », [NON FOURNI] ou « sans objet » justifié :
   - Type de bien, prix, localisation et surface.
   - Classe du DPE ; en classe F ou G, ajouter exactement « logement à consommation énergétique excessive ».
   - Ajouter exactement : « Les informations sur les risques auxquels ce bien est exposé sont disponibles sur le site Géorisques : www.georisques.gouv.fr ».
   - Honoraires à la charge de l'acquéreur : prix honoraires inclus, prix hors honoraires et pourcentage TTC.
   - Copropriété : nombre de lots, charges annuelles et procédure en cours éventuelle.
   Insérer aussi les champs obligatoires manquants dans le brouillon d'annonce sous la forme « Surface : [NON FOURNI] », par exemple.
   Si la charge des honoraires ou le statut de copropriété manque, signaler les mentions conditionnelles à confirmer, sans présumer leur absence.
9. Rédiger l'annonce pour portail en 200 mots au plus et le texte pour réseaux sociaux en 40 mots au plus.
   Compter chaque groupe séparé par un espace ou un saut de ligne comme un mot ; compter aussi les mentions et les champs [NON FOURNI].
   Afficher le total sous chaque texte, hors titre et ligne de comptage.
   En cas de dépassement, réduire la description, jamais les mentions à conserver.
10. Dresser une liste exhaustive des suppressions, reformulations et signalements.
    Pour chaque changement : phrase d'origine exacte → action → motif ; préciser la nouvelle formulation lorsqu'il y en a une.
    Inclure les omissions pour longueur, les conflits de données et les retraits de données personnelles, en masquant les identifiants dans les citations.
    S'il n'y a aucun changement, écrire « Aucune suppression ni reformulation ».
11. Ne citer dans la réponse aucune loi, aucun article, aucune recommandation d'autorité, aucune jurisprudence ni aucune source absente de l'entrée.
    Même présente dans l'entrée, une référence ne peut être citée que si elle appartient à la liste autorisée dans « Limites », avec son libellé exact.
    Une mention obligatoire à imprimer, telle que la phrase Géorisques, est du contenu et non une citation.
    La ligne de limites de la réponse dit seulement : « Le responsable de l'agence vérifie les règles applicables. »
12. Terminer par « Avant publication » : demander la validation du responsable de l'agence avant toute diffusion.
    Ajouter un rappel d'une ligne sur la pseudonymisation et l'utilisation d'un outil approuvé par l'agence ; ce rappel ne justifie jamais un refus ni une pause.
    Placer ensuite toutes les questions et tous les points à confirmer, sans aucun contenu après cette liste.
    S'il n'en reste aucun, terminer par « Questions / à confirmer : aucun point supplémentaire ».

## Format de sortie

```markdown
## Annonce pour portail
[Annonce complète ; champs manquants explicitement marqués]
Nombre de mots : [total] / 200

## Texte pour réseaux sociaux
[Texte court décrivant uniquement les caractéristiques établies]
Nombre de mots : [total] / 40

## Supprimé ou modifié
- « [Phrase d'origine] » → [action et éventuelle reformulation] → [motif]

## Mentions obligatoires à vérifier
- Type, prix, localisation, surface : [statut de chaque mention]
- DPE et mention F/G : [statut]
- Phrase Géorisques : [présence exacte vérifiée]
- Charge des honoraires et mentions associées : [statut]
- Copropriété, lots, charges annuelles, procédure : [statut]
- Calculs : [formules, valeurs et résultats, ou données manquantes ; sinon sans objet]
- Hypothèses de présentation : [liste ou aucune]

## Avant publication
- Faire valider les textes par le responsable de l'agence avant publication.
- Le responsable de l'agence vérifie les règles applicables.
- Confidentialité : pseudonymiser les données personnelles et utiliser uniquement un outil approuvé par l'agence.
- Questions / à confirmer :
  1. [Question ou point à confirmer]
```

## Limites

- France, vente uniquement : Belgique, Suisse, Canada et location hors périmètre.
- Ne jamais inventer une caractéristique, une statistique, une règle, une référence ou une information obligatoire.
- Ne jamais transformer une croyance en fait, arbitrer seul un conflit documentaire ou présenter un brouillon incomplet comme publiable.
- Le responsable de l'agence vérifie les règles applicables et valide les deux textes avant publication.
- Il contrôle sur pièces la surface, le DPE, les prix et honoraires, la copropriété, les risques, les équipements et les autorisations de travaux.
- Il vérifie aussi l'absence de ciblage discriminatoire, de promesse et de données personnelles inutiles dans chaque support.
- Retirer ou pseudonymiser les noms, coordonnées et autres informations personnelles inutiles ; n'utiliser que des outils approuvés par l'agence. Ce rappel n'est pas une condition préalable à la rédaction.
- La source ci-dessous est une lecture pour le professionnel, pas une citation à ajouter automatiquement à la réponse :
  Service-Public.fr — Que doit indiquer l'annonce d'une vente immobilière ? (F32061) — https://www.service-public.gouv.fr/particuliers/vosdroits/F32061 (page vérifiée le 12 septembre 2025 ; consultée le 2026-10-21)
- voir references/checklist.md

## Exemple

Entrée fictive :
```text
Dossier Exemple : maison à Ville-Exemple, hors copropriété ; surface non fournie.
Prix : 200 000 € ; honoraires à la charge du vendeur ; DPE : E.
Note de Mme Modèle : « idéale pour une jeune famille ».
```

Sortie abrégée ; les textes et leurs comptages sont reproduits intégralement :
```text
## Annonce pour portail
Maison à Ville-Exemple. Surface : [NON FOURNI]. Prix : 200 000 € ; honoraires à la charge du vendeur. DPE : E. Hors copropriété. Les informations sur les risques auxquels ce bien est exposé sont disponibles sur le site Géorisques : www.georisques.gouv.fr
Nombre de mots : 42 / 200
## Texte pour réseaux sociaux
Maison à Ville-Exemple.
Nombre de mots : 3 / 40
## Supprimé ou modifié
« idéale pour une jeune famille » → supprimé → ciblage selon la situation de famille.
## Mentions obligatoires à vérifier
Surface : [NON FOURNI] ; autres mentions prévues présentes ou sans objet ; aucun calcul.
## Avant publication
Faire valider les textes avant publication. Le responsable de l'agence vérifie les règles applicables.
Confidentialité : pseudonymiser les données personnelles et utiliser uniquement un outil approuvé par l'agence.
Questions / à confirmer : quelle surface est établie par les documents du bien ?
```
</skill_instructions>

Follow the skill instructions above for the user's request below.

User request:
Rédige l'annonce pour les portails et un texte pour Instagram pour ce bien.
Vente, Lyon 7e (fictif) : appartement T3 de 68 m² (loi Carrez, selon le diagnostiqueur), 3e étage avec ascenseur, balcon de 6 m², rénové en 2021. DPE : classe F.
Prix : 285 000 € honoraires inclus ; honoraires de 4 % TTC à la charge de l'acquéreur, soit 274 038 € hors honoraires.
Copropriété de 42 lots, charges annuelles 1 860 €, aucune procédure en cours.
Le vendeur dit : « mettez 75 m², avec la loggia fermée ça les fait ».
Notes du vendeur : « Idéal pour un jeune couple sans enfants, pas de colocation d'étudiants étrangers. Quartier ultra sûr. La meilleure école du secteur juste à côté. Plus-value assurée. »
````

## Output (verbatim stdout, session metadata stripped)

## Annonce pour portail
Lyon 7e (fictif). Appartement T3 de 68 m² (loi Carrez, selon le diagnostiqueur). 3e étage avec ascenseur. Balcon de 6 m². Rénové en 2021. DPE : classe F — logement à consommation énergétique excessive. Prix : 285 000 € honoraires inclus ; honoraires de 4 % TTC à la charge de l'acquéreur, soit 274 038 € hors honoraires. Copropriété de 42 lots ; charges annuelles : 1 860 € ; aucune procédure en cours. Les informations sur les risques auxquels ce bien est exposé sont disponibles sur le site Géorisques : www.georisques.gouv.fr
Nombre de mots : 92 / 200

## Texte pour réseaux sociaux
Lyon 7e (fictif). T3 de 68 m² (loi Carrez), 3e étage avec ascenseur, balcon de 6 m². Rénové en 2021.
Nombre de mots : 20 / 40

## Supprimé ou modifié
- « mettez 75 m², avec la loggia fermée ça les fait » → non repris ; surface conservée telle qu'établie par le diagnostiqueur (68 m² loi Carrez) → écart de surface non documenté ; aucune pièce ne certifie la loggia fermée comme surface habitable au sens Carrez.
- « Idéal pour un jeune couple sans enfants » → supprimé → ciblage selon la situation de famille et l'âge, décrit l'acquéreur et non le bien.
- « pas de colocation d'étudiants étrangers » → supprimé → ciblage discriminatoire selon l'origine nationale/la nationalité et le mode d'occupation, interdit.
- « Quartier ultra sûr » → supprimé → allégation invérifiable, aucun document ne l'établit.
- « La meilleure école du secteur juste à côté » → supprimé → allégation invérifiable et promesse ; proximité utilisée comme argument de ciblage non établi par un document.
- « Plus-value assurée » → supprimé → promesse commerciale invérifiable.

## Mentions obligatoires à vérifier
- Type, prix, localisation, surface : présent (T3, Lyon 7e, 285 000 €, 68 m² loi Carrez selon le diagnostiqueur). Conflit signalé : le vendeur demande 75 m² en intégrant la loggia fermée, non confirmé par le diagnostiqueur — voir questions.
- DPE et mention F/G : présent — classe F, mention « logement à consommation énergétique excessive » ajoutée.
- Phrase Géorisques : présent, texte exact reproduit.
- Charge des honoraires et mentions associées : présent — acquéreur ; 285 000 € honoraires inclus, 274 038 € hors honoraires, 4 % TTC.
- Copropriété, lots, charges annuelles, procédure : présent — 42 lots, 1 860 € de charges annuelles, aucune procédure en cours.
- Calculs :
  Honoraires = prix honoraires inclus − prix hors honoraires = 285 000 € − 274 038 € = 10 962 € (calculé).
  Pourcentage TTC = honoraires ÷ prix hors honoraires × 100 = 10 962 € ÷ 274 038 € × 100 ≈ 4,0001 % (calculé) — à comparer au 4 % fourni ; écart d'arrondi à faire valider.
- Hypothèses de présentation : aucune.

## Avant publication
- Faire valider les textes par le responsable de l'agence avant publication.
- Le responsable de l'agence vérifie les règles applicables.
- Confidentialité : pseudonymiser les données personnelles et utiliser uniquement un outil approuvé par l'agence.
- Questions / à confirmer :
  1. La surface de 68 m² (loi Carrez, diagnostiqueur) est-elle bien celle à publier, et la demande du vendeur d'afficher 75 m² en intégrant la loggia fermée doit-elle être écartée tant qu'aucun document ne la confirme ?
  2. Le pourcentage d'honoraires calculé (≈ 4,0001 %) confirme-t-il bien le 4 % TTC indiqué, ou une autre base doit-elle être retenue ?
  3. La mention « (fictif) » associée à « Lyon 7e » doit-elle être conservée dans les textes définitifs ou retirée avant toute diffusion réelle ?

