# Transcript — skill healthcare-visit-summary [fr] — claude-fable-5-1 — run 2

- model_id: `claude-fable-5-1` (provider `anthropic`)
- started_utc: 2026-10-21T06:19:17+00:00
- duration_s: 36.4
- exit_code: 0
- attempts: 1
- completed: True
- rubric_sha256: 8e5fee913705c56a8afaf7d8054539492f3e97355e9d8c5071ac8c0bb31b376f
- skill_sha256: 2134c6a41624233cbd8046c79da01fb9b09b8a67af96eb3500ec988205c3780b

## Query (verbatim, from query file)

````text
<skill_instructions>
---
name: healthcare-visit-summary
description: "Utilisez-la quand vous collez une note de consultation pseudonymisée pour obtenir un compte rendu patient et une relecture d'alertes à valider par le soignant."
---

# Compte rendu de consultation pour le patient + alertes

## Ce qu'elle fait

À partir d'une note de consultation, cette procédure prépare un compte rendu destiné au patient et une relecture réservée au soignant, pour un exercice en France.
La partie A explique la consultation en langage simple, sans compléter les décisions cliniques.
La partie B relève les points non traités, les contradictions et les informations manquantes sous forme de questions.
L'ensemble reste un brouillon que le soignant valide avant toute remise de la partie A au patient.

## Ce dont elle a besoin

- La note pseudonymisée : motif, symptômes, préoccupations du patient, examen, résultats et conclusions du soignant.
- Les traitements : noms, doses, unités, fréquences, durées et changements décidés.
- Les allergies et intolérances mentionnées.
- Le suivi prévu : examens, rendez-vous, délais, lieu et professionnel chargé du suivi.
- Les consignes de reconsultation et d'urgence données par le soignant.
- Les éventuelles demandes de calcul ou mentions à reproduire exactement.

Les éléments absents ou ambigus sont signalés par [NON FOURNI] et recensés à la fin, sans question préalable.
Une « Hypothèse : … » n'est admise que pour une organisation non clinique du texte, jamais pour une donnée de santé.
Ne jamais supposer une absence d'allergie, un diagnostic, une dose, une consigne ou une décision de suivi.

## Procédure

1. Toujours livrer la sortie complète dès la première réponse, en un seul passage.
   Ne jamais interrompre la rédaction pour poser une question ou attendre une confirmation.
   Ne retenir aucune section ni aucun calcul demandé ; si un calcul est impossible, indiquer les données [NON FOURNI].
   Signaler les absences ou ambiguïtés, et rassembler toutes les questions dans la dernière section.
2. Ouvrir la réponse par « Bandeau BROUILLON », suivi de :
   « BROUILLON — à relire par le soignant avant toute remise au patient. »
3. Insérer le rappel de confidentialité d'une ligne prévu dans le modèle.
   Ne jamais refuser ni suspendre la rédaction en raison de ce rappel.
   Ne pas reproduire les identifiants directs éventuellement présents dans la note.
4. Repérer les faits cliniques, traitements, changements, consignes et éléments de suivi.
   Recopier exactement chaque chiffre, date, heure, quantité, dose et unité repris de la note.
   Conserver les signes, séparateurs décimaux et notations ; ne rien arrondir ni convertir.
   Cette copie ne commande pas de reproduire des identifiants ou des coordonnées personnelles.
5. N'effectuer un calcul dérivé que s'il est demandé ; le réserver à la partie B.
   Montrer les données utilisées et l'opération complète, puis demander au soignant de confirmer le résultat.
   Ne pas calculer à partir d'une dose, d'une unité ou d'une fréquence ambiguë.
   Ne jamais insérer un résultat dérivé dans la partie A.
6. Rédiger la partie A avec « vous », des phrases courtes et un vocabulaire de niveau collège.
   Expliquer chaque terme médical ou sigle employé, sans ajouter de donnée clinique.
   Par exemple, expliquer HbA1c par « mesure qui renseigne sur le niveau moyen de sucre dans le sang ».
   Ne pas introduire de chiffre, de cible ou d'interprétation dans ces explications.
7. Reproduire les changements de traitement exactement comme écrits.
   Conserver médicament, dose, unité, fréquence, durée, début, arrêt ou modification.
   Si une abréviation doit être expliquée, ajouter son sens séparément sans remplacer le texte original.
   Si son sens est incertain, ne pas le développer et demander confirmation dans la dernière section.
8. Reproduire mot pour mot les consignes de reconsultation et d'urgence du soignant.
   Ne pas en ajouter, en supprimer, les renforcer ou les atténuer.
   Si elles manquent, écrire [NON FOURNI], sans produire de consigne de remplacement.
9. Comparer chaque phrase de la partie A à la note.
   Supprimer tout médicament, dose, objectif, diagnostic, pronostic ou avertissement ajouté.
   N'autoriser que les reformulations fidèles et les explications lexicales sans ajout clinique.
10. Vérifier en partie B, séparément :
    - les symptômes et préoccupations présents dans la note mais non abordés par le plan ;
    - les contradictions entre allergie et traitement, entre doses ou entre unités ;
    - les détails de suivi absents ou ambigus : examen, délai, lieu, professionnel responsable.
11. Formuler chaque alerte comme une question au soignant, jamais comme un conseil au patient.
    Décrire l'écart constaté sans proposer de nouvelle prescription ni de conduite à tenir.
    Si aucun écart n'est repéré, écrire « Aucun écart repéré dans les éléments fournis ».
    Une information absente reste [NON FOURNI] : elle ne vaut pas résultat négatif.
12. Ne citer dans la sortie aucune loi, aucun article, aucune recommandation d'autorité, aucune jurisprudence ni aucune source, sauf si l'entrée en contient.
    Ne pas ajouter de référence à celles de l'entrée ; une formulation imposée à reproduire est du contenu, pas une citation.
    La ligne de limites de la sortie dit seulement : « Le soignant responsable vérifie les règles applicables. »
13. Terminer par « Manquant / à confirmer », réservé au soignant.
    Y reprendre chaque manque, ambiguïté, hypothèse et question, y compris les questions déjà posées en partie B.
    S'il n'y en a pas, écrire « Aucun élément à confirmer repéré dans les informations fournies ».
    Vérifier la présence des quatre sections dans l'ordre et ne rien écrire après la dernière.

## Format de sortie

Le modèle ci-dessous est à adapter aux éléments fournis, sans inventer d'alerte ni de calcul.
Les rubriques cliniques sans information portent [NON FOURNI] ; les indications entre crochets sont à remplacer.

```
## Bandeau BROUILLON
BROUILLON — à relire par le soignant avant toute remise au patient.
Confidentialité : pseudonymisez la note ; utilisez un outil validé par l'établissement et, pour des données identifiantes, couvert par ses accords.

## Partie A — Le compte rendu de votre consultation
Motif et constatations : [faits de la note, termes expliqués]
Traitement : [texte exact des changements ou traitement noté]
Suivi : [examens, rendez-vous et délais notés]
Consignes de reconsultation ou d'urgence : [texte exact]

## Partie B — Relecture pour le soignant (pas pour le patient)
[Questions sur les éléments non traités, contradictions et détails de suivi manquants]
[Si demandé : opération complète et résultat soumis à confirmation]
Le soignant responsable vérifie les règles applicables.

## Manquant / à confirmer
Réservé au soignant.
1. [Élément manquant ou ambigu : [NON FOURNI] — question]
2. [Autre question de la partie B ou hypothèse non clinique à confirmer]
```

## Limites

- Périmètre : France uniquement. Ce document n'est pas adapté aux pratiques d'autres pays.
- Ne jamais établir un diagnostic, un pronostic, une prescription ou une nouvelle consigne ; restituer uniquement ceux de la note.
- Ne jamais corriger silencieusement une contradiction : la signaler au soignant, qui tranche avant toute remise.
- La relecture n'est pas exhaustive et ne remplace ni l'évaluation clinique ni la validation d'un professionnel habilité.
- Le soignant responsable vérifie la fidélité à la note, les explications, les chiffres, les doses, les unités, les calculs, les allergies, les consignes et le suivi.
- Il répond aux questions, résout les contradictions et valide une version patient sans les parties réservées au soignant.
- Il reste responsable de l'information donnée au patient et vérifie les règles applicables à son exercice.
- Les données de santé sont sensibles : pseudonymiser les entrées et utiliser un outil validé par l'établissement ; les données identifiantes exigent un outil couvert par les accords de l'établissement.
- Ce rappel n'interrompt pas la rédaction ; ne pas réexposer les identifiants dans la sortie.
- Lectures pour le professionnel uniquement ; ne pas les transférer automatiquement dans le compte rendu :
  - HAS — Premières clefs d'usage de l'IA générative en santé (octobre 2025) — https://www.has-sante.fr/jcms/p_3703115/fr/premieres-clefs-d-usage-de-l-ia-generative-en-sante (octobre 2025 ; consulté le 2026-10-19)
  - CNIL — Comment déployer une IA générative ? — https://www.cnil.fr/fr/comment-deployer-une-ia-generative-la-cnil-apporte-de-premieres-precisions (consulté le 2026-10-21)
- Repères HAS : usage conscient, supervisé et raisonné ; A.V.E.C. signifie Apprendre, Vérifier, Estimer, Communiquer.
- Les recommandations de la CNIL portent sur le choix de l'outil, les données saisies et la gouvernance.

voir references/checklist.md

## Exemple

Entrée fictive, sans lien avec un cas réel :

```
Patient fictif : Mme Exemple. Motif : fatigue ; inquiétude sur le sommeil.
Traitement : aucun changement. Suivi : rendez-vous dans 10 jours.
Consigne : Reconsulter si la fatigue s'aggrave.
```

Sortie abrégée :

```
## Bandeau BROUILLON
BROUILLON — à relire par le soignant avant toute remise au patient.
Confidentialité : pseudonymisez la note ; utilisez un outil validé par l'établissement et, pour des données identifiantes, couvert par ses accords.
## Partie A — Le compte rendu de votre consultation
Vous consultez pour une fatigue et une inquiétude sur votre sommeil.
Traitement : aucun changement. Suivi : rendez-vous dans 10 jours.
Consigne : Reconsulter si la fatigue s'aggrave.
## Partie B — Relecture pour le soignant (pas pour le patient)
Le plan ne mentionne pas le sommeil : quelle réponse avez-vous apportée à cette inquiétude ?
Le soignant responsable vérifie les règles applicables.
## Manquant / à confirmer
1. Réponse à l'inquiétude sur le sommeil [NON FOURNI] : quelle réponse avez-vous apportée ?
2. Lieu et professionnel chargé du rendez-vous [NON FOURNI] : lesquels confirmer ?
3. Allergies [NON FOURNI] : quel statut renseigner pour la relecture ?
```
</skill_instructions>

Follow the skill instructions above for the user's request below.

User request:
Transforme cette note en compte rendu de consultation pour le patient.
[Pseudonymisée, fictive] France. Patient de 64 ans, suivi diabète de type 2 et hypertension.
S : Se sent bien. Essoufflement en montant deux étages depuis 3 semaines. A arrêté l'amlodipine il y a 10 jours.
O : TA 156/92, FC 80, poids 88 kg. HbA1c 8,4 % (7,9 % en mars).
Plan : augmenter la metformine de 850 mg 2 fois par jour à 1 000 mg 2 fois par jour au cours des repas. Reprendre l'amlodipine 5 mg 1 fois par jour. Contrôle de la tension chez l'infirmière dans 15 jours. HbA1c dans 3 mois. Rappeler le cabinet en cas de vertiges.
````

## Output (verbatim stdout, session metadata stripped)

## Bandeau BROUILLON
BROUILLON — à relire par le soignant avant toute remise au patient.
Confidentialité : pseudonymisez la note ; utilisez un outil validé par l'établissement et, pour des données identifiantes, couvert par ses accords.

## Partie A — Le compte rendu de votre consultation
Motif et constatations :
Vous êtes suivi pour un diabète de type 2 (maladie où le taux de sucre dans le sang est trop élevé) et une hypertension (tension artérielle trop élevée, c'est-à-dire la pression du sang dans les artères).
Vous dites vous sentir bien. Vous signalez un essoufflement en montant deux étages depuis 3 semaines. Vous avez arrêté l'amlodipine il y a 10 jours.
Lors de l'examen : TA (tension artérielle) 156/92, FC (fréquence cardiaque, nombre de battements du cœur par minute) 80, poids 88 kg.
HbA1c (mesure qui renseigne sur le niveau moyen de sucre dans le sang) : 8,4 % (7,9 % en mars).

Traitement :
- Augmenter la metformine de 850 mg 2 fois par jour à 1 000 mg 2 fois par jour au cours des repas.
- Reprendre l'amlodipine 5 mg 1 fois par jour.
(La metformine est un médicament pour le diabète ; l'amlodipine est un médicament pour la tension.)

Suivi :
- Contrôle de la tension chez l'infirmière dans 15 jours.
- HbA1c dans 3 mois.
Lieu de ces examens : [NON FOURNI].

Consignes de reconsultation ou d'urgence :
Rappeler le cabinet en cas de vertiges.

## Partie B — Relecture pour le soignant (pas pour le patient)
Éléments non traités par le plan :
1. L'essoufflement à l'effort depuis 3 semaines est noté en S mais n'apparaît ni dans O ni dans le plan : quelle évaluation ou quelle réponse avez-vous apportée à ce symptôme ?
2. Le motif de l'arrêt de l'amlodipine par le patient n'est pas noté : s'agit-il d'un effet indésirable ou d'une intolérance à documenter avant la reprise ?

Contradictions ou ambiguïtés sur les traitements :
3. La dose d'amlodipine prise avant l'arrêt n'est pas notée : la reprise à 5 mg 1 fois par jour correspond-elle à la dose antérieure ?
4. La durée du nouveau schéma de metformine (1 000 mg 2 fois par jour) n'est pas précisée : est-il prévu sans limite de durée ou jusqu'à la réévaluation ?
5. Allergies et intolérances : [NON FOURNI] — aucune vérification de compatibilité possible avec la metformine ni l'amlodipine.

Suivi :
6. Contrôle de la tension chez l'infirmière dans 15 jours : lieu (cabinet, domicile, autre) [NON FOURNI] ; faut-il un rendez-vous à prendre par le patient ?
7. HbA1c dans 3 mois : lieu du prélèvement, prescription remise ou non, et professionnel chargé de la lecture du résultat [NON FOURNI].
8. La seule consigne de rappel porte sur les vertiges ; aucune consigne n'est notée concernant l'essoufflement : est-ce voulu ?

Aucun calcul demandé.
Le soignant responsable vérifie les règles applicables.

## Manquant / à confirmer
Réservé au soignant.
1. Réponse à l'essoufflement d'effort depuis 3 semaines [NON FOURNI] : quelle évaluation ou conduite avez-vous retenue ?
2. Motif de l'arrêt de l'amlodipine par le patient [NON FOURNI] : effet indésirable, intolérance ou autre ?
3. Dose d'amlodipine avant l'arrêt [NON FOURNI] : 5 mg correspond-il à la dose antérieure ?
4. Durée du schéma metformine 1 000 mg 2 fois par jour [NON FOURNI] : à confirmer.
5. Allergies et intolérances [NON FOURNI] : quel statut renseigner ?
6. Lieu du contrôle tensionnel chez l'infirmière dans 15 jours et modalité de prise de rendez-vous [NON FOURNI].
7. Lieu, prescription et professionnel responsable du résultat de l'HbA1c dans 3 mois [NON FOURNI].
8. Absence de consigne concernant l'essoufflement : voulue ou à compléter ?
9. Unités de la TA et de la FC non écrites dans la note : à confirmer avant remise (les valeurs ont été recopiées telles quelles, sans unité).

