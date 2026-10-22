# Transcript — skill sales-managers-pipeline-review [fr] — claude-opus-5-5 — run 1

- model_id: `claude-opus-5-5` (provider `anthropic`)
- started_utc: 2026-10-21T05:59:54+00:00
- duration_s: 62.4
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

Synthèse de la prévision
-------------------------
Trimestre : 01/10/2026 au 31/12/2026 (Hypothèse : trimestre civil, début [NON FOURNI]) ; date du jour : 19/10/2026 ; objectif restant : 500 000 € HT (Hypothèse : base HT, selon « montants en euros HT »).
Prévision provisoire : 126 000 € + 48 000 € + 54 000 € + 18 000 € = 246 000 € HT.
Écart provisoire : 500 000 € − 246 000 € = 254 000 € HT restant à couvrir.
Elle est provisoire pour deux raisons : les dates sans année sont supposées en 2026, et le traitement des affaires signées dans l'objectif est inconnu, avec un risque de double comptage.
Affaires hors calcul : 5) Modèle Transport, exclue avec certitude car sa clôture du 25/01/2027 tombe hors trimestre.
Nature : estimation interne, pas une information financière.
Rappel : pseudonymiser les données et utiliser un outil approuvé par l'entreprise.
Limites : le responsable vérifie les règles applicables.

Tableau des affaires
--------------------
1) Exemple Industrie
   Montant : 180 000 € HT
   Étape : Négociation, probabilité 70 %
   Clôture : 15/12
   Statut : [NON FOURNI]
   Traitement : incluse (15/12/2026 dans le trimestre, selon l'hypothèse sur l'année)
   Calcul : 180 000 € × 70 % = 126 000 €

2) Modèle Santé
   Montant : 120 000 € HT
   Étape : Proposition, probabilité 40 %
   Clôture : 30/11
   Statut : [NON FOURNI]
   Traitement : incluse (30/11/2026 dans le trimestre, selon l'hypothèse sur l'année)
   Calcul : 120 000 € × 40 % = 48 000 €

3) Test Énergie
   Montant : 60 000 € HT
   Étape : Engagement, probabilité 90 %
   Clôture : 10/10
   Statut : pas encore signé
   Traitement : incluse (10/10/2026 dans le trimestre, selon l'hypothèse sur l'année et le début au 01/10)
   Calcul : 60 000 € × 90 % = 54 000 €

4) Exemple Retail
   Montant : 90 000 € HT
   Étape : Découverte, probabilité 20 %
   Clôture : 20/12
   Statut : [NON FOURNI]
   Traitement : incluse (20/12/2026 dans le trimestre, selon l'hypothèse sur l'année)
   Calcul : 90 000 € × 20 % = 18 000 €

5) Modèle Transport
   Montant : 150 000 € HT
   Étape : Proposition, probabilité 40 %
   Clôture : 25/01/2027
   Statut : [NON FOURNI]
   Traitement : hors calcul (hors trimestre)
   Calcul : aucun

Alertes de risque
-----------------
2) Modèle Santé, R2 (inactivité) : dernière activité le 08/09, soit 19/10/2026 − 08/09/2026 = 41 jours. 41 jours dépasse le seuil de 21 jours. Détail : 22 jours du 08/09 au 30/09, puis 19 jours jusqu'au 19/10.
3) Test Énergie, R1 (clôture dépassée) : la clôture du 10/10 est antérieure au 19/10/2026 et l'affaire n'est « pas encore signé ». L'écart est de 19/10/2026 − 10/10/2026 = 9 jours. Pour R2, 19/10/2026 − 09/10/2026 = 10 jours, donc pas d'alerte d'inactivité.

Sans alerte d'inactivité :
- 1) 19/10 − 16/10 = 3 jours.
- 4) 19/10 − 17/10 = 2 jours.
- 5) 19/10 − 18/10 = 1 jour.

R1 n'est déclenchée pour aucune des affaires 1, 2, 4 et 5, car leurs clôtures ne sont pas dépassées.

Règles non vérifiables :
- R2, branche « absence de prochaine étape » : prochaine étape [NON FOURNI] pour les 5 affaires.
- R3 : maintien ou départ du relais ou du décideur [NON FOURNI] pour les 5 affaires. Pour l'affaire 4, « notre seul contact est le DAF » ne signale aucun départ, donc pas d'alerte R3.
- R4 non vérifiable : critères [NON FOURNI].

Questions de coaching
---------------------
2) Modèle Santé, R2 : aucune activité n'est enregistrée depuis le 08/09. Qu'est-ce qui justifie aujourd'hui de maintenir la clôture au 30/11 et la probabilité de 40 % ?
3) Test Énergie, R1 : la clôture prévue le 10/10 est dépassée sans signature. Qu'est-ce qui bloque la signature, et quelle nouvelle date de clôture pouvez-vous justifier ?

Données manquantes
------------------
- Date de début du trimestre [NON FOURNI], toutes affaires concernées. Les bornes reposent sur l'hypothèse du trimestre civil. L'inclusion de l'affaire 3 (10/10) en dépend.
- Année des dates de clôture des affaires 1 à 4 et des dates d'activité des affaires 1 à 5 [NON FOURNI]. L'inclusion et les écarts en jours reposent sur l'hypothèse 2026.
- Statut signé ou non signé [NON FOURNI] pour les affaires 1, 2, 4 et 5. Sans effet sur R1 aujourd'hui, mais ce statut est nécessaire pour le périmètre de l'objectif.
- Prochaine étape [NON FOURNI] pour les 5 affaires. La branche « absence de suite » de R2 n'est pas vérifiable.
- Maintien ou départ du relais ou du décideur [NON FOURNI] pour les 5 affaires. R3 n'est pas vérifiable.
- Critères étape / clôture [NON FOURNI]. R4 n'est pas vérifiable.
- Périmètre de l'objectif restant et traitement des affaires signées [NON FOURNI]. L'écart est provisoire, avec un risque de double comptage.

Hypothèses à confirmer :
- Hypothèse : trimestre du 01/10/2026 au 31/12/2026.
- Hypothèse : les dates sans année sont en 2026.
- Hypothèse : l'objectif restant de 500 000 € est HT.

Questions :
- Modèle Santé (R2) : aucune activité n'est enregistrée depuis le 08/09. Qu'est-ce qui justifie aujourd'hui de maintenir la clôture au 30/11 et la probabilité de 40 % ?
- Test Énergie (R1) : la clôture prévue le 10/10 est dépassée sans signature. Qu'est-ce qui bloque la signature, et quelle nouvelle date de clôture pouvez-vous justifier ?
- Le trimestre commence-t-il bien le 01/10/2026, et toutes les dates sans année sont-elles en 2026 ?
- Quel est le statut signé ou non signé des affaires 1, 2, 4 et 5 ?
- Quelle est la prochaine étape de chaque affaire ?
- Le relais ou le décideur de chaque affaire est-il toujours en poste ?
- Quels critères l'équipe applique-t-elle pour juger la cohérence entre étape et date de clôture ?
- Les affaires déjà signées sont-elles déduites de l'objectif restant de 500 000 € ?

