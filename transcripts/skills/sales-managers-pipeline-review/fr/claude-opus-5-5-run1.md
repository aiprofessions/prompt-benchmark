# Transcript — skill sales-managers-pipeline-review [fr] — claude-opus-5-5 — run 1

- model_id: `claude-opus-5-5` (provider `anthropic`)
- started_utc: 2026-10-21T09:27:39+00:00
- duration_s: 48.2
- exit_code: 0
- attempts: 1
- completed: True
- rubric_sha256: e1ac167121bfa3b4860d4c3ea4fe61f3fcd2e4b204445189eab388a3b86e9435
- skill_sha256: f329c9d133722fbf909fe527ad774e173776c2e262acceccc6abbe909e67b4e3

## Query (verbatim, from query file)

````text
<skill_instructions>
---
name: sales-managers-pipeline-review
description: "Utilisez-la quand vous collez les dates du trimestre, l'objectif restant et les affaires pour obtenir la prévision pondérée, les risques et les questions d'entretien."
---

# Revue hebdomadaire du pipeline commercial

## Ce qu'elle fait

Elle prépare la revue hebdomadaire et les entretiens individuels du directeur commercial en France.
Elle calcule la prévision pondérée du trimestre et l'écart à l'objectif restant, avec les opérations détaillées.
Elle justifie chaque alerte, y compris le suivi par un seul interlocuteur, et prépare une question de coaching par affaire signalée.
Elle recense les données manquantes et les hypothèses à confirmer.

## Ce dont elle a besoin

- Les dates de début et de fin du trimestre et la date du jour.
- L'objectif restant, sa devise et sa base HT ou TTC.
- Une ligne par affaire : identifiant pseudonymisé, montant, devise, base HT ou TTC, étape et probabilité associée.
- Pour chaque affaire : date de clôture prévue, statut signé ou non signé, date de dernière activité et prochaine étape.
- Les interlocuteurs mentionnés dans le champ contact ou les notes : identifiants pseudonymisés distincts et rôles utiles.
- Le maintien ou le départ du relais interne ou du décideur qui soutient l'affaire.
- Le barème étape → probabilité, si les probabilités ne figurent pas dans les lignes.
- Les critères de l'équipe pour apprécier la cohérence entre étape et date de clôture : délais minimaux, jalons requis ou autre règle explicite.
- Le périmètre de l'objectif restant, notamment le traitement des affaires déjà signées.

Ne coller que le nécessaire ; éviter les noms, coordonnées et notes personnelles sans utilité pour la revue.
Les éléments absents sont marqués [NON FOURNI] et listés à la fin, sans interrompre la rédaction.

## Procédure

1. Toujours livrer la sortie complète dès la première réponse, sans poser de question ni attendre une confirmation avant de rédiger.
   Ne retenir aucune section ni aucun calcul : effectuer ceux qui sont réalisables ; sinon, afficher l'opération, [NON FOURNI] et le blocage.
   Pour une ambiguïté de méthode, annoncer une hypothèse raisonnable par « Hypothèse : … » ou écrire [NON FOURNI].
   Ne jamais utiliser une hypothèse pour inventer une donnée d'affaire ; regrouper les questions et confirmations dans la dernière section.
2. Recopier exactement chaque chiffre, date, heure et quantité fournis, sans changer leur présentation.
   Montrer l'opération de chaque chiffre dérivé, y compris les écarts en jours ; présenter les montants calculés au format français.
   Ne jamais inventer de montant, probabilité, contact, statut, date ou prochaine étape.
3. Fixer les bornes inclusives du trimestre à partir des dates fournies.
   Si seul le dernier jour d'un trimestre civil est fourni, annoncer l'hypothèse du trimestre civil correspondant et ses bornes.
   Sinon, marquer la borne manquante [NON FOURNI] : l'appartenance au trimestre n'est pas vérifiable.
   Ne jamais remplacer une date du jour manquante par une date supposée.
4. Examiner chaque affaire : sa date de clôture doit se situer entre les deux bornes pour entrer dans la prévision.
   Lister chaque affaire hors calcul et son motif : hors trimestre, date absente ou ambiguë, bornes indéterminées, montant ou probabilité manquants.
   Distinguer les exclusions certaines des affaires non calculables ; ne jamais traiter une donnée manquante comme zéro.
5. Utiliser uniquement la probabilité d'étape explicitement fournie ou celle du barème transmis.
   En cas de contradiction entre ligne et barème, signaler le conflit et laisser la contribution non calculable.
   Ne jamais attribuer automatiquement 100 % à une affaire signée.
   Calculer chaque contribution admissible : montant × probabilité indiquée = montant pondéré.
   Additionner les contributions en montrant la somme ; si aucune affaire n'est admissible et que les données sont complètes, afficher zéro.
6. Vérifier la cohérence des devises et des bases HT ou TTC avant toute addition ou comparaison.
   Ne pas convertir ni supposer un taux ; séparer les bases incompatibles et signaler les calculs impossibles.
   Vérifier le traitement des affaires signées dans l'objectif restant ; ne pas les retirer silencieusement du calcul demandé.
   Si ce traitement est inconnu, présenter le calcul comme provisoire et signaler le risque de double comptage.
7. Calculer l'écart : objectif restant − prévision pondérée = écart.
   Un résultat positif indique le montant restant à couvrir ; un résultat négatif indique un dépassement.
   Si des affaires potentiellement admissibles sont non calculables, afficher « prévision partielle » et « écart provisoire ».
   Si l'objectif manque, afficher l'opération avec [NON FOURNI], sans inventer de résultat.
8. Tester les cinq règles suivantes sur toutes les affaires, même hors calcul ; citer les faits qui déclenchent chaque alerte.
   - R1 — Clôture dépassée : date de clôture strictement antérieure à la date du jour et statut non signé.
   - R2 — Inactivité ou absence de suite : date du jour − dernière activité > 21 jours, ou absence explicite de prochaine étape.
   - R3 — Soutien perdu : départ du relais interne ou du décideur qui soutient l'affaire explicitement signalé.
   - R4 — Incohérence étape / clôture : contradiction avec un critère fourni par l'équipe ; citer ce critère et les valeurs concernées.
   - R5 — Mono-contact : une seule personne ou un seul interlocuteur mentionné pour l'affaire, dans le champ contact ou les notes.
   Toujours signaler R5, même si l'affaire est par ailleurs saine ; compter les personnes distinctes, pas les occurrences ni les rôles.
   Ne pas supposer qu'un interlocuteur unique exerce plusieurs rôles ni que plusieurs rôles désignent plusieurs personnes.
   Sans interlocuteur mentionné, ou si leur nombre est ambigu, écrire « R5 non vérifiable » et lister la précision nécessaire.
   Écrire une fois dans la synthèse : « Hypothèse : seuil d'inactivité par défaut de 21 jours, à ajuster par l'équipe ».
   Ce seuil est un réglage de la revue, pas une norme ; rappeler en dernière section que cette hypothèse reste à confirmer.
   Ne pas inventer de seuil pour R4. Sans critère, écrire « R4 non vérifiable : critères [NON FOURNI] ».
   Pour toute règle, distinguer une absence confirmée d'un champ vide : un champ vide donne « non vérifiable », pas une alerte certaine.
   Si une branche de R2 est vérifiée, signaler l'alerte même si l'autre branche ne peut pas être évaluée.
9. Préparer exactement une question de coaching distincte par affaire signalée, quelle que soit la règle déclenchée, R5 comprise.
   Si plusieurs règles sont déclenchées, formuler une seule question qui les couvre, sans ajouter de sous-questions séparées.
   Pour R5, viser l'élargissement des interlocuteurs ou l'identification du décideur.
   Relier la question aux faits fournis, sans présupposer un contact, une action ou un engagement inexistant.
   L'afficher dans « Questions de coaching » ; la reprendre à l'identique en dernière section, sans en créer une seconde.
10. Dans la sortie, ne citer aucune loi, aucun article, aucune recommandation d'autorité, aucune décision ni aucune source, sauf si l'entrée en contient.
    Une mention obligatoire fournie par l'utilisateur à reproduire est du contenu, pas une citation.
    Les sources de « Limites » sont destinées au professionnel, pas à être ajoutées automatiquement à la sortie.
    La ligne de limites de la sortie dit seulement : « Le responsable vérifie les règles applicables. »
11. Ajouter un rappel d'une ligne : pseudonymiser les données et utiliser un outil approuvé par l'entreprise.
    Ce rappel n'est pas une condition préalable : ne jamais refuser ni suspendre la réponse pour ce motif.
12. Vérifier les cinq sections et leur ordre, les exclusions motivées, les opérations, l'hypothèse des 21 jours et une question distincte par affaire signalée.
    Terminer par les données manquantes, leurs conséquences, les hypothèses à confirmer et toutes les questions ; ne rien ajouter après.

## Format de sortie

```markdown
## Synthèse de la prévision
Trimestre : [début] au [fin] ; date du jour : [date] ; objectif restant : [montant et base].
Prévision [complète/partielle/provisoire] : [contribution A] + [contribution B] = [total].
Écart [sur les données fournies/provisoire] : [objectif restant] − [prévision] = [résultat].
Affaires hors calcul : [identifiant — motif pour chacune, ou aucune].
Hypothèse : seuil d'inactivité par défaut de 21 jours, à ajuster par l'équipe.
Nature : estimation interne, pas une information financière.
Rappel : pseudonymiser les données et utiliser un outil approuvé par l'entreprise.
Limites : le responsable vérifie les règles applicables.

## Tableau des affaires
| Affaire | Montant et base | Étape | Probabilité | Clôture | Statut | Traitement et motif | Calcul pondéré |
|---|---|---|---|---|---|---|---|
| [identifiant] | [montant] | [étape] | [probabilité] | [date] | [statut] | [incluse/hors calcul] | [montant × probabilité = contribution] |

## Alertes de risque
[Affaire — règle R1 à R5 déclenchée — faits et calcul éventuel ; règles non vérifiables séparées.]

## Questions de coaching
[Affaire — règles visées — une seule question précise, y compris pour R5.]

## Données manquantes
[Donnée absente ou ambiguë — affaire concernée — conséquence, ou aucune.]
[À confirmer : hypothèse du seuil d'inactivité retenue dans la synthèse.]
[Autres hypothèses à confirmer, ou aucune.]
[Questions : reprendre à l'identique les questions de coaching et ajouter les demandes de précision.]
```

## Limites

- Usage limité à la France ; ne pas transposer ces indications à d'autres pays.
- Ne jamais inventer les données d'affaires ou présenter une hypothèse de méthode comme un fait, notamment le seuil de 21 jours.
- La prévision est une estimation interne, pas une information financière ni une garantie de signature.
- Le directeur commercial responsable vérifie les données du CRM, les probabilités, les dates, les calculs, le périmètre de l'objectif et les critères d'alerte avant utilisation.
- Les données du CRM sont des données personnelles des contacts (RGPD) : ne coller que le nécessaire, pseudonymiser et utiliser uniquement un outil approuvé par l'entreprise.
- Pour les relances par e-mail, SMS ou automate d'appel, le responsable vérifie les règles applicables : consentement préalable en B2C ; information du contact et possibilité de s'opposer en B2B.
- Lecture pour le professionnel :
  CNIL — La prospection commerciale par courrier électronique, SMS-MMS et automate d'appel — https://www.cnil.fr/fr/la-prospection-commerciale-par-courrier-electronique-sms-mms-et-automate-dappel (consulté le 2026-10-21)

voir references/checklist.md

## Exemple

Entrée fictive :
```
Trimestre : 01/10/2026 au 31/12/2026 ; date du jour : 21/10/2026.
Objectif restant : 20 000 € HT ; aucune affaire signée dans la liste.
Exemple — 10 000 € HT — Proposition 50 % — clôture 30/11/2026 — non signé — activité 20/10/2026 — prochaine étape : démonstration le 28/10/2026 — contact : acheteur (seul interlocuteur cité) — soutien maintenu.
```

Sortie abrégée :
```
## Synthèse de la prévision
Prévision : 10 000 € × 50 % = 5 000 € HT ; écart : 20 000 € − 5 000 € = 15 000 € HT. Hors calcul : aucune.
Hypothèse : seuil d'inactivité par défaut de 21 jours, à ajuster par l'équipe.
Estimation interne, pas une information financière. Rappel : pseudonymiser et utiliser un outil approuvé par l'entreprise. Limites : le responsable vérifie les règles applicables.
## Tableau des affaires
Exemple — Proposition 50 % — non signé — clôture 30/11/2026 incluse — 10 000 € × 50 % = 5 000 € HT.
## Alertes de risque
Exemple — R5 : seul interlocuteur cité, l'acheteur ; R2 non déclenchée (21/10/2026 − 20/10/2026 = 1 jour, prochaine étape fournie).
R1 et R3 non déclenchées ; R4 non vérifiable : critères [NON FOURNI].
## Questions de coaching
Exemple — R5 : comment pouvez-vous identifier qui prend la décision finale au-delà du seul acheteur cité ?
## Données manquantes
Critères étape / clôture [NON FOURNI] : quels critères l'équipe applique-t-elle ?
À confirmer : hypothèse du seuil d'inactivité retenue dans la synthèse.
Rappel de la question de coaching : comment pouvez-vous identifier qui prend la décision finale au-delà du seul acheteur cité ?
```
</skill_instructions>

Follow the skill instructions above for the user's request below.

User request:
Prépare ma revue hebdomadaire du pipeline.
France, montants en euros HT. Le trimestre se termine le 31/12/2026. Aujourd'hui : 19/10/2026. Objectif restant du trimestre : 500 000 €.
1) Exemple Industrie — 180 000 € — Négociation (70 %) — clôture 15/12 — dernière activité 16/10.
2) Modèle Santé — 120 000 € — Proposition (40 %) — clôture 30/11 — dernière activité 08/09.
3) Test Énergie — 60 000 € — Engagement (90 %) — clôture 10/10 — dernière activité 09/10 — pas encore signé.
4) Exemple Retail — 90 000 € — Découverte (20 %) — clôture 20/12 — dernière activité 17/10 — notre seul contact est le DAF.
5) Modèle Transport — 150 000 € — Proposition (40 %) — clôture 25/01/2027 — dernière activité 18/10.
````

## Output (verbatim stdout, session metadata stripped)

Synthèse de la prévision

Trimestre : 01/10/2026 au 31/12/2026. Hypothèse : trimestre civil correspondant au dernier jour fourni (31/12/2026).
Date du jour : 19/10/2026. Objectif restant : 500 000 € HT.
Hypothèse : les dates sans année (15/12, 30/11, 10/10, 20/12, 16/10, 08/09, 09/10, 17/10, 18/10) sont lues en 2026, l'affaire 5 portant une année explicite (2027).

Prévision provisoire : 126 000 € + 48 000 € + 54 000 € + 18 000 € = 246 000 € HT.
Écart provisoire : 500 000 € − 246 000 € = 254 000 € HT restant à couvrir.

Le calcul est provisoire pour deux raisons :
- le traitement des affaires signées dans l'objectif restant n'est pas fourni, d'où un risque de double comptage ;
- le statut signé ou non signé n'est pas fourni pour les affaires 1, 2, 4 et 5.

Affaires hors calcul : 5) Modèle Transport. Exclusion certaine : sa clôture (25/01/2027) est postérieure au 31/12/2026.
Hypothèse : seuil d'inactivité par défaut de 21 jours, à ajuster par l'équipe.
Nature : estimation interne, pas une information financière.
Rappel : pseudonymiser les données et utiliser un outil approuvé par l'entreprise.
Limites : le responsable vérifie les règles applicables.


Tableau des affaires

1) Exemple Industrie
   Montant : 180 000 € HT. Étape : Négociation (70 %). Clôture : 15/12. Statut : [NON FOURNI].
   Traitement : incluse.
   Calcul : 180 000 € × 70 % = 126 000 € HT.

2) Modèle Santé
   Montant : 120 000 € HT. Étape : Proposition (40 %). Clôture : 30/11. Statut : [NON FOURNI].
   Traitement : incluse.
   Calcul : 120 000 € × 40 % = 48 000 € HT.

3) Test Énergie
   Montant : 60 000 € HT. Étape : Engagement (90 %). Clôture : 10/10. Statut : non signé.
   Traitement : incluse, car la clôture tombe dans le trimestre, mais elle est dépassée (voir R1).
   Calcul : 60 000 € × 90 % = 54 000 € HT.

4) Exemple Retail
   Montant : 90 000 € HT. Étape : Découverte (20 %). Clôture : 20/12. Statut : [NON FOURNI].
   Traitement : incluse.
   Calcul : 90 000 € × 20 % = 18 000 € HT.

5) Modèle Transport
   Montant : 150 000 € HT. Étape : Proposition (40 %). Clôture : 25/01/2027. Statut : [NON FOURNI].
   Traitement : hors calcul, hors trimestre.
   Calcul : aucun (pour information, 150 000 € × 40 % = 60 000 € HT, non retenu).


Alertes de risque

Alertes déclenchées :

2) Modèle Santé — R2 (inactivité)
   19/10/2026 − 08/09/2026 = 41 jours, soit plus que 21 jours.

3) Test Énergie — R1 (clôture dépassée)
   La clôture du 10/10 est antérieure au 19/10/2026 et l'affaire est « pas encore signé ».
   Retard : 19/10/2026 − 10/10/2026 = 9 jours.

4) Exemple Retail — R5 (mono-contact)
   « Notre seul contact est le DAF » : un seul interlocuteur est cité.

Règles non déclenchées :

R1 ne s'applique pas aux affaires 1, 2, 4 et 5 : leurs clôtures (15/12, 30/11, 20/12, 25/01/2027) sont postérieures au 19/10/2026.

Branche inactivité de R2, écarts depuis la dernière activité :
- 1) 19/10 − 16/10 = 3 jours ;
- 3) 19/10 − 09/10 = 10 jours ;
- 4) 19/10 − 17/10 = 2 jours ;
- 5) 19/10 − 18/10 = 1 jour.

Règles non vérifiables :

- R2, branche « absence de prochaine étape », pour les affaires 1 à 5 : prochaine étape [NON FOURNI].
- R3 pour les affaires 1 à 5 : maintien ou départ du relais interne ou du décideur [NON FOURNI].
- R4 pour les affaires 1 à 5 : critères [NON FOURNI].
- R5 pour les affaires 1, 2, 3 et 5 : aucun interlocuteur mentionné.


Questions de coaching

2) Modèle Santé — R2
   Après 41 jours sans activité depuis le 08/09, quel élément concret vous permet encore de maintenir cette affaire à 40 % avec une clôture au 30/11 ?

3) Test Énergie — R1
   Quel élément concret, obtenu depuis la clôture prévue le 10/10 restée sans signature, justifie de maintenir cette affaire à l'étape Engagement à 90 % ?

4) Exemple Retail — R5
   Comment pouvez-vous identifier qui prend la décision finale au-delà du DAF, seul contact cité, avant la clôture prévue le 20/12 ?


Données manquantes

Données absentes :

- Statut signé ou non signé, affaires 1, 2, 4 et 5 : la prévision reste provisoire.
- Traitement des affaires signées dans l'objectif restant, toutes affaires : risque de double comptage et écart provisoire.
- Prochaine étape, affaires 1 à 5 : la branche « absence de suite » de R2 n'est pas vérifiable.
- Maintien ou départ du relais interne ou du décideur, affaires 1 à 5 : R3 n'est pas vérifiable.
- Interlocuteurs, affaires 1, 2, 3 et 5 : R5 n'est pas vérifiable.
- Critères étape / clôture de l'équipe, toutes affaires : R4 n'est pas vérifiable.

Hypothèses à confirmer :

- Seuil d'inactivité retenu dans la synthèse (21 jours par défaut).
- Trimestre civil du 01/10/2026 au 31/12/2026.
- Année 2026 pour les dates fournies sans année.
- Base HT de l'objectif restant, déduite de « montants en euros HT ».
- Date du jour : le 19/10/2026 a été retenu tel que fourni.

Questions de coaching (reprises) :

- 2) Modèle Santé : Après 41 jours sans activité depuis le 08/09, quel élément concret vous permet encore de maintenir cette affaire à 40 % avec une clôture au 30/11 ?
- 3) Test Énergie : Quel élément concret, obtenu depuis la clôture prévue le 10/10 restée sans signature, justifie de maintenir cette affaire à l'étape Engagement à 90 % ?
- 4) Exemple Retail : Comment pouvez-vous identifier qui prend la décision finale au-delà du DAF, seul contact cité, avant la clôture prévue le 20/12 ?

Demandes de précision :

- Quelles affaires sont déjà signées, et l'objectif restant de 500 000 € les exclut-il ?
- Quelle est la prochaine étape de chaque affaire ?
- Quels interlocuteurs sont cités pour les affaires 1, 2, 3 et 5 ?
- Le relais interne ou le décideur est-il maintenu pour chaque affaire ?
- Quels critères l'équipe applique-t-elle pour juger la cohérence entre étape et clôture, par exemple pour une affaire en Découverte à 20 % qui clôture le 20/12 ?

