# Transcript — skill accountants-month-end-reconciliation [fr] — claude-sonnet-5 — run 1

- model_id: `claude-sonnet-5` (provider `anthropic`)
- started_utc: 2026-10-21T06:02:07+00:00
- duration_s: 70.4
- exit_code: 0
- attempts: 1
- completed: True
- rubric_sha256: 41ec1d90007b8c06fbe4b733c80ce61d1e81f3f2b77614a0e2886cb12a629f01
- skill_sha256: 609553aa0f0dcfc7398f4f660940226eceda4413fa67e0d686dc26b3de5a932b

## Query (verbatim, from query file)

````text
<skill_instructions>
---
name: accountants-month-end-reconciliation
description: "Utilisez-la quand vous collez les soldes du relevé bancaire et du compte 512 avec les suspens pour obtenir une note de rapprochement de clôture."
---

# Note de rapprochement bancaire de clôture

## Ce qu'elle fait

Elle prépare une note de rapprochement bancaire pour un dossier comptable en France. Elle compare le solde bancaire ajusté au solde comptable ajusté, avec les calculs détaillés et chaque suspens classé. Elle propose uniquement les écritures côté comptabilité, précise les justificatifs nécessaires et laisse les écarts inexpliqués visibles. Le professionnel responsable contrôle et vise la note.

## Ce dont elle a besoin

- Le solde du relevé bancaire, sa date et son sens débiteur ou créditeur.
- Le solde du compte 512 Banques à la même date, avec son sens débiteur ou créditeur.
- Tous les suspens, avec montant, date, référence disponible et indication de leur présence au relevé ou en comptabilité.
- Pour une erreur : montant saisi, montant justifié, nature de l’opération et comptes utilisés.
- Les justificatifs disponibles et, facultativement, le pseudonyme du dossier et les quatre derniers chiffres du compte bancaire.

Les informations manquantes sont notées [NON FOURNI] et les questions sont regroupées à la fin, sans interrompre la rédaction. Une ambiguïté peut être traitée par une « Hypothèse : … » raisonnable et explicite ; aucun montant, date ou fait justificatif n’est inventé.

## Procédure

1. Toujours livrer la sortie complète dès la première réponse, sans poser de question préalable ni attendre de confirmation. Ne retenir aucune section ni aucun calcul : afficher les calculs possibles et, sinon, la formule avec [NON FOURNI] et la cause du blocage. Regrouper toutes les questions dans la dernière section.
2. Recopier exactement chaque chiffre, date, heure et quantité de l’entrée, en conservant le format des montants fourni. Exception de confidentialité : masquer les identifiants de comptes bancaires, avec quatre derniers chiffres au maximum ; cette règle ne masque pas les codes comptables PCG.
3. Vérifier que les soldes concernent le même compte et la même date. Signaler tout désaccord sans inventer de solde intermédiaire. Expliquer la convention : trésorerie disponible positive, découvert négatif ; un solde créditeur du relevé et un solde débiteur du 512 représentent normalement une trésorerie positive. Si le sens manque, afficher une hypothèse à confirmer.
4. Inventorier chaque suspens une seule fois et le classer :
   - décalage côté banque : chèques ou virements émis déjà comptabilisés, non débités ; remises ou dépôts déjà comptabilisés, non crédités ;
   - élément côté comptabilité : frais, intérêts, impayés ou autres mouvements bancaires non saisis, erreurs d’enregistrement ;
   - mouvement bancaire non identifié : élément côté comptabilité à qualifier, jamais présenté comme produit ou charge établi.
   Si la présence dans les deux supports est incertaine, signaler le classement hypothétique et demander confirmation en dernière section.
5. Côté banque, partir du solde du relevé converti selon la convention annoncée. Ajouter chaque remise ou dépôt non crédité ; retrancher chaque chèque ou virement émis non débité. Afficher une ligne par opération avec signe, montant et calcul du solde intermédiaire, puis le solde bancaire ajusté.
6. Pour chaque erreur, calculer montant justifié − montant saisi et expliquer le sens de correction du 512. Règlement saisi trop haut : augmentation ; trop bas : diminution. Encaissement saisi trop haut : diminution ; trop bas : augmentation. Montrer le calcul du montant de la correction, sans appliquer deux fois l’erreur.
7. Côté comptabilité, partir du solde du 512 converti selon la convention annoncée. Déduire les frais, intérêts débiteurs et impayés non saisis ; ajouter les intérêts créditeurs non saisis ; appliquer chaque autre correction selon sa nature. Afficher une ligne par opération avec signe, montant et solde intermédiaire, puis le solde comptable ajusté.
8. Garder tout crédit ou débit non identifié comme suspens en attente de justificatif. Si son montant, son sens au relevé et son absence du 512 sont établis, montrer son effet sur le solde ajusté, sans présumer sa nature. Sinon, laisser son traitement à confirmer et ne pas annoncer de rapprochement établi.
9. Calculer et afficher : écart = solde bancaire ajusté − solde comptable ajusté. Ne jamais forcer l’égalité ni créer d’écriture pour absorber l’écart. Présenter toute différence comme « écart non expliqué » et ajouter une question finale ; un écart nul sous hypothèses reste à confirmer.
10. Proposer des écritures uniquement pour les éléments côté comptabilité, avec comptes, débit, crédit, montant et statut. Aucune écriture pour les décalages côté banque. Frais : débit 627 Services bancaires / crédit 512 Banques ; impayé client justifié : débit 411 Clients / crédit 512 Banques. Pour une erreur fournisseur, vérifier la contrepartie 401 Fournisseurs ; sinon, indiquer [À CONFIRMER PAR LE PROFESSIONNEL].
11. Une proposition en 471 Compte d’attente reste facultative et porte « en attente de justificatif — à valider par le professionnel ». Crédit bancaire non identifié : débit 512 / crédit 471 ; débit bancaire non identifié : débit 471 / crédit 512. Ne jamais présenter ces propositions comme déjà comptabilisées ou comme une affectation définitive.
12. Associer à chaque écriture proposée les pièces nécessaires avant comptabilisation et leur état : fournies ou à obtenir. Pour chaque décalage bancaire, préciser également la preuve permettant d’en vérifier la réalité et le dénouement.
13. Ne citer dans la sortie aucune loi, aucun article, aucune recommandation de régulateur, aucune décision ni aucune source absente de l’entrée. Une formulation imposée par l’utilisateur est du contenu à reproduire, non une citation documentaire. Les sources de « Limites » sont destinées au professionnel, pas à être ajoutées à la note.
14. Insérer le rappel de confidentialité sans refuser ni suspendre la rédaction. La ligne de limites indique seulement que le professionnel responsable vérifie les règles applicables. Laisser vierges les champs « préparé par », « revu par » et « date ». Terminer par toutes les questions et tous les points à confirmer, ou « Aucun ».

## Format de sortie

Reprendre les rubriques ci-dessous dans cet ordre. Répéter les lignes nécessaires pour couvrir tous les suspens ; ne pas conserver une ligne illustrative sans opération correspondante.

```
## Synthèse du rapprochement
Dossier : [pseudonyme ou NON FOURNI] — compte bancaire : [référence masquée ou NON FOURNI]
Clôture : [date ou NON FOURNI] — convention de signes : […]
Soldes ajustés : banque […] ; comptabilité […] ; écart […]
Hypothèse : […] / Aucune hypothèse.
Informations manquantes : […]

## Côté banque
Solde du relevé : […] ; solde selon la convention : […]
[Référence, date] : [décalage] ; calcul : [solde précédent] +/− [montant] = […]
Solde bancaire ajusté : [calcul récapitulatif] = […]

## Côté comptabilité
Solde du 512 : […] ; solde selon la convention : […]
[Référence, date] : [élément] ; calcul : [solde précédent] +/− [montant] = […]
Erreur : [justifié] − [saisi] = […] ; correction : […] ; augmente/diminue le 512.
Mouvement non identifié : […] ; traitement provisoire et justificatif attendu : […]
Solde comptable ajusté : [calcul récapitulatif] = […]

## Écart
[Solde bancaire ajusté] − [solde comptable ajusté] = […]
[Écart non expliqué / Écart nul, sous réserves éventuelles / Non calculable : motif]

## Écritures proposées (côté comptabilité uniquement)
[Référence] — [libellé] — débit [compte et montant] ; crédit [compte et montant].
Statut : [à valider / en attente de justificatif — à valider par le professionnel].
Aucune écriture pour les décalages côté banque.

## Justificatifs à obtenir avant comptabilisation
[Référence de chaque écriture] : [pièces nécessaires ; fournies / à obtenir].
[Référence de chaque décalage] : [preuve du décalage et de son dénouement].

## Revue et visa
Confidentialité : pseudonymiser les données clients et utiliser un outil validé par le cabinet.
Limites : le professionnel responsable vérifie les règles applicables.
Préparé par : __________
Revu par (professionnel comptable responsable) : __________
Date : __________

## Questions et points à confirmer
[Liste exhaustive des questions, hypothèses à confirmer et informations manquantes / Aucun]
```

## Limites

- France uniquement ; ne pas appliquer cette procédure à un dossier relevant de Belgique, de Suisse ou du Canada sans adaptation professionnelle.
- Ne jamais inventer de données, masquer un écart, imputer définitivement une opération non identifiée ou passer une écriture. La note reste une proposition de travail.
- Le professionnel comptable responsable doit vérifier les soldes d’origine, les dates, l’exhaustivité des suspens, les signes, chaque calcul et l’absence de doublons.
- Avant comptabilisation, il doit contrôler les justificatifs, les comptes PCG, le sens débit/crédit et le traitement des opérations non identifiées. L’expert-comptable ou le professionnel responsable, pas le modèle, vise le rapprochement.
- L’expert-comptable est tenu au secret professionnel. Anonymiser ou pseudonymiser les données clients et utiliser uniquement un outil validé par le cabinet ; ne jamais reproduire les identifiants bancaires complets. Ce rappel ne constitue pas une condition préalable à la rédaction.
- Le rapprochement ne remplace pas les obligations de facturation électronique : depuis le 1er septembre 2026, les grandes entreprises et les entreprises de taille intermédiaire émettent leurs factures via une plateforme agréée et toutes les entreprises doivent pouvoir recevoir des factures électroniques.
- Les sources ci-dessous sont des lectures pour le professionnel ; leur présence ici n’autorise pas leur citation automatique dans la note :
  - Ordre des experts-comptables — Travaux Data et IA (guide « Parlons data & IA ») — https://www.experts-comptables.fr/travaux-data-et-ia (consulté le 2026-10-21)
  - impots.gouv.fr — Facturation électronique (actualité publiée le 28/09/2026) — https://www.impots.gouv.fr/actualite/facturation-electronique (28/09/2026 ; consulté le 2026-10-19)

voir references/checklist.md

## Exemple

Entrée fictive :

```
Dossier Exemple ; soldes du même compte à la même clôture, date non précisée.
Relevé : 1 200,00 € créditeur ; compte 512 : 950,00 € débiteur.
Chèque déjà comptabilisé, non débité : 200,00 €.
Règlement fournisseur Modèle saisi 150,00 € au lieu de 100,00 €, contrepartie 401.
```

Sortie abrégée :

```
Synthèse du rapprochement : Exemple ; clôture et référence bancaire [NON FOURNI] ; trésorerie positive.
Côté banque : 1 200,00 € − 200,00 € = 1 000,00 €.
Côté comptabilité : erreur, 100,00 € − 150,00 € = −50,00 € ; règlement saisi trop haut.
Correction : 150,00 € − 100,00 € = 50,00 €, augmente le 512.
Solde comptable ajusté : 950,00 € + 50,00 € = 1 000,00 €.
Écart : 1 000,00 € − 1 000,00 € = 0,00 € ; pièces à contrôler.
Écritures proposées (côté comptabilité uniquement) : débit 512 50,00 € ; crédit 401 50,00 €, à valider.
Aucune écriture pour le chèque en décalage.
Justificatifs à obtenir avant comptabilisation : pièce du règlement Modèle et écriture d’origine.
Pour le chèque : preuve d’émission et relevé permettant de vérifier son dénouement.
Revue et visa : préparé par : ____ ; revu par (professionnel comptable responsable) : ____ ; date : ____.
Confidentialité : pseudonymiser les données clients et utiliser un outil validé par le cabinet.
Limites : le professionnel responsable vérifie les règles applicables.
Questions et points à confirmer : date de clôture ? Référence bancaire masquée ? Pièces disponibles ?
```
</skill_instructions>

Follow the skill instructions above for the user's request below.

User request:
Prépare la note de rapprochement bancaire de clôture de septembre pour le dossier.
Société : Exemple Menuiserie SARL (fictive), France. Clôture au 30 septembre 2026. Compte bancaire se terminant par 2208.
Solde du relevé bancaire : 18 640,20 €
Solde comptable du 512 : 19 521,00 €
Suspens :
- Remise de chèques de 2 115,00 € comptabilisée le 30/09, crédit en banque le 01/10.
- Virement émis au fournisseur Modèle Bois SAS de 1 250,00 €, comptabilisé le 29/09, pas encore débité.
- Chèque n° 4471 émis de 480,60 €, comptabilisé, pas encore encaissé.
- Frais de tenue de compte 18,90 € au relevé, non comptabilisés.
- Prélèvement d'un client rejeté : 640,00 € + 7,50 € de frais de rejet, au relevé, non comptabilisés.
- Règlement client comptabilisé pour 1 380,00 € ; la banque a crédité 1 200,00 € ; la facture est de 1 200,00 €.
- Virement reçu de 350,00 € le 23/09, libellé « VIR REF 90417 » : personne ne sait encore à quoi il correspond.
````

## Output (verbatim stdout, session metadata stripped)

## Synthèse du rapprochement
Dossier : Exemple Menuiserie SARL (fictive) — compte bancaire : ****2208
Clôture : 30/09/2026 — convention de signes : trésorerie disponible positive (relevé créditeur / 512 débiteur)
Soldes ajustés : banque 19 024,60 € ; comptabilité 19 024,60 € ; écart 0,00 €
Hypothèse : le sens (débiteur/créditeur) des deux soldes n'est pas précisé dans l'entrée ; on retient la convention usuelle — relevé créditeur et 512 débiteur, représentant une trésorerie positive — à confirmer par le professionnel.
Informations manquantes : sens explicite des soldes ; copie de la facture 1 200,00 € ; identité de l'émetteur du virement de 350,00 €.

## Côté banque
Solde du relevé : 18 640,20 € ; solde selon la convention : 18 640,20 € (positif)

Remise de chèques, comptabilisée 30/09, créditée 01/10 : décalage côté banque (remise non créditée) ;
calcul : 18 640,20 + 2 115,00 = 20 755,20

Virement émis Modèle Bois SAS, comptabilisé 29/09, non débité : décalage côté banque (virement émis non débité) ;
calcul : 20 755,20 − 1 250,00 = 19 505,20

Chèque n° 4471, émis et comptabilisé, non encaissé : décalage côté banque (chèque émis non débité) ;
calcul : 19 505,20 − 480,60 = 19 024,60

Solde bancaire ajusté : 18 640,20 + 2 115,00 − 1 250,00 − 480,60 = 19 024,60 €

## Côté comptabilité
Solde du 512 : 19 521,00 € ; solde selon la convention : 19 521,00 € (positif)

Frais de tenue de compte au relevé, non comptabilisés : élément côté comptabilité ;
calcul : 19 521,00 − 18,90 = 19 502,10

Prélèvement client rejeté (impayé), au relevé, non comptabilisé : élément côté comptabilité ;
calcul : 19 502,10 − 640,00 = 18 862,10

Frais de rejet lié au prélèvement, au relevé, non comptabilisés : élément côté comptabilité ;
calcul : 18 862,10 − 7,50 = 18 854,60

Erreur : règlement client — justifié 1 200,00 − saisi 1 380,00 = −180,00 ; encaissement saisi trop haut → correction en diminution.
Correction : 1 380,00 − 1 200,00 = 180,00 ; diminue le 512.
calcul : 18 854,60 − 180,00 = 18 674,60

Mouvement non identifié : virement reçu 350,00 € le 23/09 (libellé « VIR REF 90417 »), présent au relevé, absent du 512 ; traitement provisoire et justificatif attendu : affectation à confirmer, aucune nature présumée.
calcul : 18 674,60 + 350,00 = 19 024,60

Solde comptable ajusté : 19 521,00 − 18,90 − 640,00 − 7,50 − 180,00 + 350,00 = 19 024,60 €

## Écart
19 024,60 − 19 024,60 = 0,00 €
Écart nul, sous réserve de la confirmation du sens des soldes (hypothèse ci-dessus) et de la nature du virement non identifié.

## Écritures proposées (côté comptabilité uniquement)
Frais bancaires — débit 627 Services bancaires 18,90 € ; crédit 512 Banques 18,90 €.
Statut : à valider.

Impayé client (prélèvement rejeté) — débit 411 Clients 640,00 € ; crédit 512 Banques 640,00 €.
Statut : à valider.

Frais de rejet — débit 627 Services bancaires 7,50 € ; crédit 512 Banques 7,50 €.
Statut : à valider.

Correction erreur règlement client — débit 411 Clients 180,00 € ; crédit 512 Banques 180,00 €.
Statut : à valider.

Virement non identifié (350,00 €) — débit 512 Banques 350,00 € ; crédit 471 Compte d'attente 350,00 €.
Statut : en attente de justificatif — à valider par le professionnel.

Aucune écriture pour les décalages côté banque (remise de chèques, virement Modèle Bois SAS, chèque n° 4471).

## Justificatifs à obtenir avant comptabilisation
Frais bancaires : avis/détail de frais figurant sur le relevé — fourni (montant visible au relevé), détail à obtenir.
Impayé + frais de rejet : avis de rejet de prélèvement émis par la banque — à obtenir.
Correction erreur règlement client : copie de la facture 1 200,00 € et écriture comptable d'origine (1 380,00 €) — à obtenir.
Virement non identifié (471) : identification de l'émetteur et objet du virement « VIR REF 90417 » — à obtenir.

Remise de chèques : bordereau de remise et relevé du mois suivant confirmant le crédit du 01/10 — à obtenir.
Virement Modèle Bois SAS : ordre de virement et relevé suivant confirmant le débit — à obtenir.
Chèque n° 4471 : copie du chèque émis et relevé suivant confirmant son encaissement — à obtenir.

## Revue et visa
Confidentialité : pseudonymiser les données clients et utiliser un outil validé par le cabinet.
Limites : le professionnel responsable vérifie les règles applicables.
Préparé par : __________
Revu par (professionnel comptable responsable) : __________
Date : __________

## Questions et points à confirmer
- Le sens (débiteur/créditeur) du solde du relevé et du solde du 512 n'est pas précisé : confirmer que le relevé est créditeur et le 512 débiteur (trésorerie positive), hypothèse retenue ici.
- Quelle est la nature du virement reçu de 350,00 € (« VIR REF 90417 ») et doit-il rester en 471 en attente, ou être affecté à un client/tiers identifié ?
- La facture de 1 200,00 € correspondant au règlement client peut-elle être fournie pour confirmer le montant justifié de la correction de 180,00 € ?
- Les comptes 411 Clients retenus pour les corrections (impayé et erreur de règlement) sont-ils bien ceux à utiliser, ou existe-t-il des comptes clients spécifiques dans le dossier ?

