# Transcript — skill sales-managers-pipeline-review [fr] — claude-sonnet-5 — run 2

- model_id: `claude-sonnet-5` (provider `anthropic`)
- started_utc: 2026-10-21T06:43:48+00:00
- duration_s: 111.2
- exit_code: 0
- attempts: 1
- completed: True
- rubric_sha256: e1ac167121bfa3b4860d4c3ea4fe61f3fcd2e4b204445189eab388a3b86e9435
- skill_sha256: 485aee00b73d8fd60b5ab27e2f4ee73d2f52b6f0868370cdfac57e4d4e25424f

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
Elle justifie les alertes, prépare une question de coaching par affaire signalée et recense les données manquantes.

## Ce dont elle a besoin

- Les dates de début et de fin du trimestre et la date du jour.
- L'objectif restant, sa devise et sa base HT ou TTC.
- Une ligne par affaire : identifiant pseudonymisé, montant, devise, base HT ou TTC, étape et probabilité associée.
- Pour chaque affaire : date de clôture prévue, statut signé ou non signé, date de dernière activité et prochaine étape.
- Le maintien ou le départ du relais interne ou du décideur qui soutient l'affaire.
- Le barème étape → probabilité, si les probabilités ne figurent pas dans les lignes.
- Les critères de l'équipe pour apprécier la cohérence entre étape et date de clôture : délais minimaux, jalons requis ou autre règle explicite.
- Le périmètre de l'objectif restant, notamment le traitement des affaires déjà signées.

Ne coller que le nécessaire ; privilégier des identifiants d'affaires sans coordonnées ni noms de contacts.
Les éléments absents sont marqués [NON FOURNI] et listés à la fin, sans interrompre la rédaction.

## Procédure

1. Toujours livrer la sortie complète dès la première réponse, sans demander de précisions ni attendre une confirmation avant de rédiger.
   Ne retenir aucune section ni aucun calcul réalisable ; pour un calcul impossible, afficher [NON FOURNI] et expliquer le blocage.
   Pour une ambiguïté de méthode, écrire « Hypothèse : … » ; pour une donnée d'affaire absente, écrire [NON FOURNI].
   Regrouper toutes les questions et hypothèses à confirmer dans « Données manquantes », en dernier.
2. Recopier exactement chaque chiffre, date, heure et quantité fournis, sans changer leur présentation.
   Montrer l'opération de chaque chiffre dérivé, y compris les écarts en jours ; présenter les montants calculés au format français.
   Ne jamais inventer de montant, probabilité, contact, statut, date ou prochaine étape.
3. Fixer les bornes inclusives du trimestre à partir des dates fournies.
   Si seul le dernier jour d'un trimestre civil est fourni, annoncer l'hypothèse du trimestre civil correspondant.
   Sinon, marquer la borne manquante [NON FOURNI] : l'appartenance au trimestre n'est pas vérifiable.
   Ne jamais remplacer une date du jour manquante par une date supposée.
4. Examiner chaque affaire : sa date de clôture doit se situer entre les deux bornes pour entrer dans la prévision.
   Lister chaque affaire hors calcul et son motif : hors trimestre, date absente ou ambiguë, bornes indéterminées, montant ou probabilité manquants.
   Distinguer les exclusions certaines des affaires non calculables ; ne jamais traiter une donnée manquante comme zéro.
5. Utiliser uniquement la probabilité d'étape explicitement fournie ou celle du barème transmis.
   En cas de contradiction entre ligne et barème, signaler le conflit et ne pas choisir silencieusement.
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
8. Tester les quatre règles suivantes sur toutes les affaires, même hors calcul ; citer les faits qui déclenchent chaque alerte.
   - R1 — Clôture dépassée : date de clôture strictement antérieure à la date du jour et statut non signé.
   - R2 — Inactivité ou absence de suite : date du jour − dernière activité > 21 jours, ou absence explicite de prochaine étape.
   - R3 — Soutien perdu : départ du relais interne ou du décideur explicitement signalé.
   - R4 — Incohérence étape / clôture : contradiction avec un critère fourni par l'équipe ; citer ce critère et les valeurs concernées.
   Ne pas inventer de seuil pour R4. Sans critère, écrire « R4 non vérifiable : critères [NON FOURNI] ».
   Pour toute règle, distinguer une absence confirmée d'un champ vide : un champ vide donne « non vérifiable », pas une alerte certaine.
   Si une branche de R2 est vérifiée, signaler l'alerte même si l'autre branche ne peut pas être évaluée.
9. Préparer exactement une question de coaching par affaire signalée, même si plusieurs règles sont déclenchées.
   La relier à une alerte précise et aux faits fournis, sans présupposer un contact, une action ou un engagement inexistant.
   L'afficher dans « Questions de coaching » et la reprendre dans le regroupement final des questions.
10. Dans la sortie, ne citer aucune loi, aucun article, aucune recommandation d'autorité, aucune décision ni aucune source, sauf si l'entrée en contient.
    Une mention obligatoire fournie par l'utilisateur à reproduire est du contenu, pas une citation.
    Les sources de « Limites » sont destinées au professionnel, pas à être ajoutées automatiquement à la sortie.
    La ligne de limites de la sortie dit seulement : « Le responsable vérifie les règles applicables. »
11. Ajouter le rappel d'une ligne prévu au modèle : pseudonymiser et utiliser un outil approuvé par l'entreprise.
    Ce rappel n'est pas une condition préalable : ne jamais refuser ni suspendre la réponse pour ce motif.
12. Vérifier les cinq sections et leur ordre, les exclusions motivées, les opérations et la présence d'une question par affaire signalée.
    Terminer par les données manquantes, leurs conséquences, les hypothèses à confirmer et toutes les questions ; ne rien ajouter après.

## Format de sortie

```
## Synthèse de la prévision
Trimestre : [début] au [fin] ; date du jour : [date] ; objectif restant : [montant et base].
Prévision [complète/partielle/provisoire] : [contribution A] + [contribution B] = [total].
Écart [définitif sur les données fournies/provisoire] : [objectif restant] − [prévision] = [résultat].
Affaires hors calcul : [identifiant — motif pour chacune, ou aucune].
Nature : estimation interne, pas une information financière.
Rappel : pseudonymiser les données et utiliser un outil approuvé par l'entreprise.
Limites : le responsable vérifie les règles applicables.

## Tableau des affaires
| Affaire | Montant et base | Étape | Probabilité | Clôture | Statut | Traitement et motif | Calcul pondéré |
|---|---|---|---|---|---|---|---|
| [identifiant] | [montant] | [étape] | [probabilité] | [date] | [statut] | [incluse/hors calcul] | [montant × probabilité = contribution] |

## Alertes de risque
[Affaire — règle déclenchée — faits et calcul éventuel ; règles non vérifiables séparées.]

## Questions de coaching
[Affaire — règle visée — une question précise.]

## Données manquantes
[Donnée absente ou ambiguë — affaire concernée — conséquence, ou aucune.]
[Hypothèse : … — à confirmer, ou aucune.]
[Questions : reprendre les questions de coaching et ajouter les demandes de précision.]
```

## Limites

- Usage limité à la France ; ne pas transposer ces indications à d'autres pays.
- Ne jamais inventer les données d'affaires ou présenter une hypothèse de méthode comme un fait.
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
Exemple — 10 000 € HT — Proposition 50 % — clôture 30/11/2026 — non signé — activité 20/10/2026 — prochaine étape : aucune — soutien maintenu.
```

Sortie abrégée :
```
## Synthèse de la prévision
Prévision : 10 000 € × 50 % = 5 000 € HT ; écart : 20 000 € − 5 000 € = 15 000 € HT.
Affaires hors calcul : aucune. Estimation interne, pas une information financière.
Rappel : pseudonymiser les données et utiliser un outil approuvé par l'entreprise.
Limites : le responsable vérifie les règles applicables.
## Tableau des affaires
Exemple — Proposition 50 % — non signé — clôture 30/11/2026 incluse dans le trimestre du 01/10/2026 au 31/12/2026 — 10 000 € × 50 % = 5 000 € HT.
## Alertes de risque
Exemple — R2 : prochaine étape explicitement absente ; 21/10/2026 − 20/10/2026 = 1 jour, sans alerte d'inactivité.
R4 non vérifiable : critères [NON FOURNI].
## Questions de coaching
Exemple — R2 : quelle prochaine étape pouvez-vous convenir avec le client pour cette proposition ?
## Données manquantes
Critères étape / clôture [NON FOURNI] : quels critères l'équipe applique-t-elle ?
Question de coaching à reprendre : quelle prochaine étape pouvez-vous convenir avec le client pour cette proposition ?
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

## Synthèse de la prévision

Trimestre : 01/10/2026 au 31/12/2026 (Hypothèse : trimestre civil, car seule la date de fin — 31/12/2026 — a été fournie) ; date du jour : 19/10/2026 ; objectif restant : 500 000 € HT.

Prévision complète (sur les affaires admissibles identifiées) :
180 000 € × 70 % = 126 000 € (Exemple Industrie)
+ 120 000 € × 40 % = 48 000 € (Modèle Santé)
+ 60 000 € × 90 % = 54 000 € (Test Énergie)
+ 90 000 € × 20 % = 18 000 € (Exemple Retail)
= 126 000 + 48 000 + 54 000 + 18 000 = 246 000 € HT.

Écart (sous hypothèse de trimestre civil ci-dessus) : 500 000 € − 246 000 € = 254 000 € HT restant à couvrir.

Affaires hors calcul : Modèle Transport — clôture 25/01/2027, postérieure au 31/12/2026, donc hors trimestre.

Nature : estimation interne, pas une information financière.
Rappel : pseudonymiser les données et utiliser un outil approuvé par l'entreprise.
Limites : le responsable vérifie les règles applicables.

## Tableau des affaires

1) Exemple Industrie — 180 000 € HT — Négociation — probabilité 70 % — clôture 15/12/2026 — statut [NON FOURNI] — incluse (clôture dans le trimestre 01/10–31/12/2026) — calcul : 180 000 € × 70 % = 126 000 €.

2) Modèle Santé — 120 000 € HT — Proposition — probabilité 40 % — clôture 30/11/2026 — statut [NON FOURNI] — incluse — calcul : 120 000 € × 40 % = 48 000 €.

3) Test Énergie — 60 000 € HT — Engagement — probabilité 90 % — clôture 10/10/2026 — statut non signé (explicite) — incluse (clôture dans le trimestre, même si déjà dépassée) — calcul : 60 000 € × 90 % = 54 000 €.

4) Exemple Retail — 90 000 € HT — Découverte — probabilité 20 % — clôture 20/12/2026 — statut [NON FOURNI] — incluse — calcul : 90 000 € × 20 % = 18 000 €.

5) Modèle Transport — 150 000 € HT — Proposition — probabilité 40 % — clôture 25/01/2027 — statut [NON FOURNI] — hors calcul : clôture 25/01/2027 postérieure au 31/12/2026, donc hors trimestre — aucun calcul pondéré.

## Alertes de risque

1) Exemple Industrie :
R1 non déclenchée (clôture 15/12/2026 postérieure à 19/10/2026).
R2 : dernière activité 16/10/2026 ; écart = 19/10/2026 − 16/10/2026 = 3 jours, pas d'alerte d'inactivité. Prochaine étape non renseignée dans les données fournies → branche « absence de prochaine étape » non vérifiable (champ vide, pas une absence confirmée).
R3 non vérifiable : maintien/départ du soutien [NON FOURNI].
R4 non vérifiable : critères [NON FOURNI].
→ Aucune règle déclenchée avec certitude.

2) Modèle Santé :
R1 non déclenchée (clôture 30/11/2026 postérieure à 19/10/2026).
R2 DÉCLENCHÉE : dernière activité 08/09/2026 ; écart = 08/09/2026 au 19/10/2026 = 41 jours (30 jours jusqu'au 08/10 + 11 jours jusqu'au 19/10) > 21 jours → alerte d'inactivité. (Branche « prochaine étape » non vérifiable, sans incidence car l'autre branche est déjà vérifiée.)
R3 non vérifiable : maintien/départ du soutien [NON FOURNI].
R4 non vérifiable : critères [NON FOURNI].

3) Test Énergie :
R1 DÉCLENCHÉE : clôture 10/10/2026 strictement antérieure à aujourd'hui 19/10/2026 (écart = 9 jours) et statut explicitement non signé.
R2 : dernière activité 09/10/2026 ; écart = 19/10/2026 − 09/10/2026 = 10 jours, pas d'alerte d'inactivité. Prochaine étape non vérifiable (champ vide).
R3 non vérifiable : maintien/départ du soutien [NON FOURNI].
R4 non vérifiable : critères [NON FOURNI].

4) Exemple Retail :
R1 non déclenchée (clôture 20/12/2026 postérieure à 19/10/2026).
R2 : dernière activité 17/10/2026 ; écart = 19/10/2026 − 17/10/2026 = 2 jours, pas d'alerte d'inactivité. Prochaine étape non vérifiable (champ vide).
R3 non vérifiable : l'information fournie (« notre seul contact est le DAF ») précise l'identité du contact mais ne confirme ni maintien ni départ explicite ; statut de soutien [NON FOURNI].
R4 non vérifiable : critères [NON FOURNI].
→ Aucune règle déclenchée avec certitude.

5) Modèle Transport (hors calcul, testée quand même) :
R1 non déclenchée (clôture 25/01/2027 postérieure à 19/10/2026).
R2 : dernière activité 18/10/2026 ; écart = 19/10/2026 − 18/10/2026 = 1 jour, pas d'alerte d'inactivité. Prochaine étape non vérifiable (champ vide).
R3 non vérifiable : [NON FOURNI].
R4 non vérifiable : critères [NON FOURNI].

## Questions de coaching

Modèle Santé — R2 (inactivité, 41 jours) : qu'est-ce qui explique l'absence d'activité enregistrée depuis le 08/09/2026, et quelle relance concrète pouvez-vous planifier avant la clôture prévue du 30/11/2026 ?

Test Énergie — R1 (clôture dépassée, affaire non signée) : la date de clôture du 10/10/2026 est dépassée sans signature ; quelle nouvelle date de clôture reflète la situation réelle de cette affaire ?

## Données manquantes

Borne de début du trimestre — générale — [NON FOURNI], Hypothèse retenue : trimestre civil 01/10/2026–31/12/2026 ; à confirmer, car l'appartenance des affaires au trimestre en dépend.

Statut signé/non signé — affaires Exemple Industrie, Modèle Santé, Exemple Retail, Modèle Transport — [NON FOURNI] ; conséquence : R1 non vérifiable avec certitude pour ces affaires (sans incidence actuelle car leurs clôtures ne sont pas encore dépassées, sauf réévaluation si les dates glissent).

Prochaine étape — toutes les affaires — [NON FOURNI] ; conséquence : branche « absence de prochaine étape » de R2 non vérifiable pour les 5 affaires.

Maintien ou départ du relais interne / décideur — toutes les affaires — [NON FOURNI] ; conséquence : R3 non vérifiable pour les 5 affaires. Pour Exemple Retail, seule l'identité du contact (DAF) est connue, pas son statut de maintien.

Critères de cohérence étape / clôture — général — [NON FOURNI] ; conséquence : R4 non vérifiable pour les 5 affaires.

Traitement des affaires déjà signées dans l'objectif restant — général — [NON FOURNI] ; sans incidence immédiate car aucune affaire de la liste n'est confirmée comme signée, mais à clarifier pour éviter tout double comptage futur.

Questions à reprendre :
— Modèle Santé : qu'est-ce qui explique l'absence d'activité enregistrée depuis le 08/09/2026, et quelle relance concrète pouvez-vous planifier avant la clôture prévue du 30/11/2026 ?
— Test Énergie : la date de clôture du 10/10/2026 est dépassée sans signature ; quelle nouvelle date de clôture reflète la situation réelle de cette affaire ?
— Confirmation à demander : la date de début du trimestre est-elle bien le 01/10/2026 ?
— Confirmation à demander : quel est le statut signé/non signé exact de Exemple Industrie, Modèle Santé, Exemple Retail et Modèle Transport ?
— Confirmation à demander : quels sont les critères de l'équipe pour la cohérence étape/clôture (R4) ?
— Confirmation à demander : le soutien interne (relais ou décideur) est-il maintenu sur chacune des 5 affaires ?

