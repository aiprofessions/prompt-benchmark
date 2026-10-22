# Transcript — skill healthcare-visit-summary [fr] — claude-opus-5-5 — run 2

- model_id: `claude-opus-5-5` (provider `anthropic`)
- started_utc: 2026-10-21T06:29:35+00:00
- duration_s: 28.0
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
Vous êtes suivi pour un diabète de type 2 et une hypertension.
Le diabète de type 2 est une maladie où le sucre dans le sang est trop élevé.
L'hypertension est une tension artérielle trop élevée.
Vous dites que vous vous sentez bien.
Vous êtes essoufflé quand vous montez deux étages, depuis 3 semaines.
Vous avez arrêté l'amlodipine il y a 10 jours.
Mesures faites pendant la consultation :
  - TA (tension artérielle, la force du sang dans les vaisseaux) : 156/92.
  - FC (fréquence cardiaque, le nombre de battements du cœur par minute) : 80.
  - Poids : 88 kg.
  - HbA1c (mesure qui renseigne sur le niveau moyen de sucre dans le sang) : 8,4 %. En mars, elle était de 7,9 %.
Conclusion du soignant : [NON FOURNI]

Traitement :
  - « augmenter la metformine de 850 mg 2 fois par jour à 1 000 mg 2 fois par jour au cours des repas ».
    La metformine est un médicament du diabète.
  - « Reprendre l'amlodipine 5 mg 1 fois par jour ».
    L'amlodipine est un médicament de la tension.

Suivi :
  - « Contrôle de la tension chez l'infirmière dans 15 jours. »
  - « HbA1c dans 3 mois. »

Consignes de reconsultation ou d'urgence :
« Rappeler le cabinet en cas de vertiges. »

## Partie B — Relecture pour le soignant (pas pour le patient)
1. L'essoufflement en montant deux étages depuis 3 semaines n'est pas abordé dans le plan : quelle évaluation ou quelle réponse avez-vous apportée ?
2. Aucune consigne n'est notée sur l'évolution de cet essoufflement : souhaitez-vous qu'une consigne figure dans le compte rendu, et si oui avec quel texte exact ?
3. Le motif de l'arrêt de l'amlodipine il y a 10 jours n'est pas renseigné : quel était-il, et a-t-il été discuté avant la reprise ?
4. Allergies et intolérances : [NON FOURNI]. Quel statut renseigner pour vérifier la compatibilité avec la metformine et l'amlodipine ?
5. Aucune conclusion clinique n'est écrite dans la note : souhaitez-vous en faire figurer une dans la partie A ?
6. Contrôle de la tension dans 15 jours : quelle infirmière, quel lieu, et qui reçoit le résultat ?
7. HbA1c dans 3 mois : où réaliser l'examen (laboratoire), une ordonnance est-elle remise, et qui interprète le résultat ?
8. Durée des traitements et moment de début de la nouvelle dose de metformine : [NON FOURNI]. Faut-il les préciser ?
9. Moment de prise de l'amlodipine dans la journée : [NON FOURNI]. Faut-il le préciser ?
Le soignant responsable vérifie les règles applicables.

## Manquant / à confirmer
Réservé au soignant.
1. Prise en charge de l'essoufflement depuis 3 semaines [NON FOURNI] : quelle évaluation ou réponse avez-vous apportée ?
2. Consigne concernant l'essoufflement [NON FOURNI] : faut-il en ajouter une, et avec quel texte exact ?
3. Motif de l'arrêt de l'amlodipine [NON FOURNI] : lequel, et a-t-il été discuté avant la reprise ?
4. Allergies et intolérances [NON FOURNI] : quel statut renseigner ?
5. Conclusion clinique de la consultation [NON FOURNI] : faut-il en faire figurer une ?
6. Contrôle tensionnel à 15 jours : infirmière, lieu et destinataire du résultat [NON FOURNI] — lesquels ?
7. HbA1c à 3 mois : laboratoire, ordonnance et professionnel qui interprète [NON FOURNI] — lesquels ?
8. Durée des traitements et date de début de la nouvelle dose de metformine [NON FOURNI] : faut-il les préciser ?
9. Moment de prise de l'amlodipine [NON FOURNI] : faut-il le préciser ?

