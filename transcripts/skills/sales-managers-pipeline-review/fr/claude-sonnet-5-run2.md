# Transcript — skill sales-managers-pipeline-review [fr] — claude-sonnet-5 — run 2

- model_id: `claude-sonnet-5` (provider `anthropic`)
- started_utc: 2026-10-21T09:37:26+00:00
- duration_s: 100.3
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

REVUE HEBDOMADAIRE DU PIPELINE — SYNTHÈSE

SYNTHÈSE DE LA PRÉVISION

Trimestre : Hypothèse — seule la date de fin (31/12/2026) a été fournie ; trimestre civil Q4 2026 retenu, bornes du 01/10/2026 au 31/12/2026 (inclusives).
Date du jour : 19/10/2026.
Objectif restant : 500 000 € HT.

Prévision provisoire (voir note ci-dessous) :
180 000 € × 70 % = 126 000 €
120 000 € × 40 % = 48 000 €
60 000 € × 90 % = 54 000 €
90 000 € × 20 % = 18 000 €
Somme : 126 000 + 48 000 + 54 000 + 18 000 = 246 000 € HT

Écart provisoire : 500 000 € − 246 000 € = 254 000 € HT restant à couvrir.

Note sur le caractère provisoire : le statut signé/non signé n'est explicite que pour Test Énergie (« pas encore signé »). Pour les quatre autres affaires, ce statut n'est pas fourni, et le périmètre de l'objectif restant (inclusion ou non des affaires déjà signées) n'est pas précisé. Risque de double comptage non écarté — chiffres à valider par vous.

Affaires hors calcul : Modèle Transport — clôture 25/01/2027, hors des bornes du trimestre (après le 31/12/2026).

Hypothèse : seuil d'inactivité par défaut de 21 jours, à ajuster par l'équipe.
Nature : estimation interne, pas une information financière.
Rappel : pseudonymiser les données et utiliser un outil approuvé par l'entreprise.
Limites : le responsable vérifie les règles applicables.

TABLEAU DES AFFAIRES

1. Exemple Industrie — 180 000 € HT — Négociation — 70 % — clôture 15/12/2026 — statut [NON FOURNI] — incluse (clôture dans le trimestre) — 180 000 × 70 % = 126 000 €

2. Modèle Santé — 120 000 € HT — Proposition — 40 % — clôture 30/11/2026 — statut [NON FOURNI] — incluse — 120 000 × 40 % = 48 000 €

3. Test Énergie — 60 000 € HT — Engagement — 90 % — clôture 10/10/2026 — statut non signé — incluse (clôture dans le trimestre, bien que déjà dépassée) — 60 000 × 90 % = 54 000 €

4. Exemple Retail — 90 000 € HT — Découverte — 20 % — clôture 20/12/2026 — statut [NON FOURNI] — incluse — 90 000 × 20 % = 18 000 €

5. Modèle Transport — 150 000 € HT — Proposition — 40 % — clôture 25/01/2027 — statut [NON FOURNI] — hors calcul : clôture postérieure au 31/12/2026 — non calculée

ALERTES DE RISQUE

Exemple Industrie
R1 non déclenchée (clôture 15/12/2026 postérieure à la date du jour 19/10/2026).
R2 : branche inactivité non déclenchée (19/10/2026 − 16/10/2026 = 3 jours ≤ 21 jours) ; branche « absence de prochaine étape » non vérifiable, champ non fourni.
R3 non vérifiable : maintien/départ du relais ou décideur [NON FOURNI].
R4 non vérifiable : critères [NON FOURNI].
R5 non vérifiable : aucun interlocuteur mentionné.

Modèle Santé
R1 non déclenchée (clôture 30/11/2026 postérieure à la date du jour).
R2 DÉCLENCHÉE : 19/10/2026 − 08/09/2026 = 41 jours > 21 jours. Branche « prochaine étape » non vérifiable, champ non fourni.
R3 non vérifiable.
R4 non vérifiable : critères [NON FOURNI].
R5 non vérifiable : aucun interlocuteur mentionné.

Test Énergie
R1 DÉCLENCHÉE : clôture 10/10/2026 strictement antérieure à la date du jour 19/10/2026 (écart : 19/10/2026 − 10/10/2026 = 9 jours de retard), statut explicitement non signé.
R2 : branche inactivité non déclenchée (19/10/2026 − 09/10/2026 = 10 jours ≤ 21) ; branche « prochaine étape » non vérifiable.
R3 non vérifiable.
R4 non vérifiable : critères [NON FOURNI].
R5 non vérifiable : aucun interlocuteur mentionné.

Exemple Retail
R1 non déclenchée (clôture 20/12/2026 postérieure à la date du jour).
R2 : branche inactivité non déclenchée (19/10/2026 − 17/10/2026 = 2 jours) ; branche « prochaine étape » non vérifiable.
R3 non vérifiable.
R4 non vérifiable : critères [NON FOURNI].
R5 DÉCLENCHÉE : un seul interlocuteur cité — le DAF.

Modèle Transport (hors calcul, mais testée comme requis)
R1 non déclenchée (clôture 25/01/2027 postérieure à la date du jour).
R2 : branche inactivité non déclenchée (19/10/2026 − 18/10/2026 = 1 jour) ; branche « prochaine étape » non vérifiable.
R3 non vérifiable.
R4 non vérifiable : critères [NON FOURNI].
R5 non vérifiable : aucun interlocuteur mentionné.

QUESTIONS DE COACHING

Modèle Santé — R2 : Qu'est-ce qui explique l'absence d'activité enregistrée depuis le 08/09/2026, et quelle action concrète pouvez-vous engager cette semaine pour réactiver l'affaire ?

Test Énergie — R1 : La clôture prévue du 10/10/2026 est dépassée sans signature ; quelle nouvelle date de clôture réaliste pouvez-vous fixer avec le client, et sur quelle base ?

Exemple Retail — R5 : Le DAF est le seul interlocuteur cité pour cette affaire ; comment pouvez-vous identifier et engager d'autres parties prenantes, notamment le décideur final ?

DONNÉES MANQUANTES

Statut signé/non signé pour Exemple Industrie, Modèle Santé, Exemple Retail, Modèle Transport [NON FOURNI] — conséquence : traitement dans l'objectif restant non vérifiable, risque de double comptage, prévision et écart présentés comme provisoires.

Prochaine étape pour les cinq affaires [NON FOURNI] — conséquence : branche R2 « absence de prochaine étape » non vérifiable pour toutes les affaires.

Maintien ou départ du relais interne ou du décideur pour les cinq affaires [NON FOURNI] — conséquence : R3 non vérifiable pour toutes les affaires.

Critères équipe étape/clôture [NON FOURNI] — conséquence : R4 non vérifiable pour toutes les affaires.

Interlocuteurs pour Exemple Industrie, Modèle Santé, Test Énergie, Modèle Transport [NON FOURNI] — conséquence : R5 non vérifiable pour ces quatre affaires ; précision nécessaire : nombre et identité (pseudonymisée) des interlocuteurs.

Date de début du trimestre non fournie explicitement — hypothèse retenue : trimestre civil Q4 2026 (01/10/2026-31/12/2026), à confirmer.

Périmètre de l'objectif restant (traitement des affaires signées) [NON FOURNI] — conséquence : prévision et écart provisoires.

À confirmer : hypothèse du seuil d'inactivité retenue dans la synthèse (21 jours par défaut).

Autres hypothèses à confirmer : bornes du trimestre civil Q4 2026 ; périmètre exact de l'objectif restant.

Questions :
— Modèle Santé — R2 : Qu'est-ce qui explique l'absence d'activité enregistrée depuis le 08/09/2026, et quelle action concrète pouvez-vous engager cette semaine pour réactiver l'affaire ?
— Test Énergie — R1 : La clôture prévue du 10/10/2026 est dépassée sans signature ; quelle nouvelle date de clôture réaliste pouvez-vous fixer avec le client, et sur quelle base ?
— Exemple Retail — R5 : Le DAF est le seul interlocuteur cité pour cette affaire ; comment pouvez-vous identifier et engager d'autres parties prenantes, notamment le décideur final ?
— Précision demandée : le statut signé/non signé des quatre affaires concernées.
— Précision demandée : la prochaine étape prévue pour chaque affaire.
— Précision demandée : le maintien ou le départ du relais interne/décideur pour chaque affaire.
— Précision demandée : les critères de cohérence étape/clôture retenus par l'équipe.
— Précision demandée : les interlocuteurs identifiés sur chaque affaire sans contact mentionné.
— Précision demandée : le périmètre exact de l'objectif restant (affaires signées incluses ou non).
— Confirmation demandée : les bornes exactes du trimestre (début 01/10/2026 confirmé ou non).

