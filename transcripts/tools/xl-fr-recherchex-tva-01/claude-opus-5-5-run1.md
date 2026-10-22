# Transcript — xl-fr-recherchex-tva-01 — claude-opus-5-5 — run 1

- model_id: `claude-opus-5-5` (provider `anthropic`)
- started_utc: 2026-10-20T12:34:44+00:00
- duration_s: 18.9
- exit_code: 0
- attempts: 1
- completed: True
- rubric_sha256: 09a43241cc283546579b9f6941517efb5778d1ac3493814dcecbed11707135aa

## Query (verbatim, from query file)

```text
Vous êtes un assistant Excel pour une petite entreprise en France. Mon Excel est en français : noms de fonctions en français, séparateur d'arguments point-virgule, virgule décimale.

À partir UNIQUEMENT des tableaux ci-dessous :
1. Donnez la formule de la cellule E2 de la feuille « Facture » qui renvoie le taux de TVA de l'article de la ligne (via son code TVA), à recopier vers le bas.
2. Donnez les formules HT (F2), TVA arrondie au centime (G2) et TTC (H2).
3. Indiquez les valeurs HT, TVA et TTC obtenues pour les 3 lignes.
4. Terminez par une note « À vérifier » de 3 puces maximum.

N'affirmez pas quel taux de TVA s'applique légalement à un produit : les taux viennent du tableau de l'utilisateur.

Feuille « Articles » (A1:C4, en-têtes ligne 1) — données fictives :
Ligne | A : Code article | B : Libellé | C : Code TVA
2 | FAR-25 | Farine T65 sac 25 kg | R
3 | MOU-12 | Moule inox 12 cm | N
4 | TRA-01 | Repas traiteur (forfait) | I

Feuille « Taux » (A1:B4) :
Ligne | A : Code TVA | B : Taux
2 | N | 20 %
3 | R | 5,5 %
4 | I | 10 %

Feuille « Facture » (A1:H4) :
Ligne | A : Code article | B : Libellé | C : PU HT (€) | D : Quantité | E : Taux | F : HT | G : TVA | H : TTC
2 | FAR-25 | Farine T65 sac 25 kg | 18,40 | 12 | | | |
3 | MOU-12 | Moule inox 12 cm | 27,90 | 4 | | | |
4 | TRA-01 | Repas traiteur (forfait) | 145,00 | 1 | | | |
```

## Output (verbatim stdout, session metadata stripped)

1. Taux (E2, à recopier vers le bas)

   =RECHERCHEV(RECHERCHEV(A2;Articles!$A$2:$C$4;3;FAUX);Taux!$A$2:$B$4;2;FAUX)

   La recherche interne trouve le code TVA de l'article dans « Articles ». La recherche externe trouve ensuite le taux correspondant dans « Taux ». Mettez E2 au format Pourcentage.

2. Formules (ligne 2, à recopier vers le bas)

   F2 (HT) :  =C2*D2
   G2 (TVA) : =ARRONDI(F2*E2;2)
   H2 (TTC) : =F2+G2

3. Valeurs obtenues

   Ligne | Article | Taux  | HT       | TVA     | TTC
   2     | FAR-25  | 5,5 % | 220,80 € | 12,14 € | 232,94 €
   3     | MOU-12  | 20 %  | 111,60 € | 22,32 € | 133,92 €
   4     | TRA-01  | 10 %  | 145,00 € | 14,50 € | 159,50 €

   Total : HT 477,40 €, TVA 48,96 €, TTC 526,36 €.
   La TVA de la ligne 2 est de 12,144 €, arrondie à 12,14 €.

4. À vérifier

   - Dans « Taux », les taux doivent être de vrais pourcentages. Par exemple, 5,5 % doit être stocké comme 0,055 et non comme 5,5, sinon la TVA sera multipliée par 100.
   - Les codes TVA attribués dans « Articles » (R, N, I) et les taux de la feuille « Taux » viennent de vos données. Faites-les valider par votre expert-comptable ou auprès des sources officielles. C'est particulièrement important pour le repas traiteur, dont le taux peut dépendre des conditions de vente.
   - L'arrondi est fait ligne par ligne. Si votre logiciel ou votre comptable calcule la TVA sur le total par taux, il peut y avoir un écart de quelques centimes. Vérifiez aussi que les codes articles de « Facture » correspondent exactement à ceux d'« Articles », sans espaces parasites, sinon vous obtiendrez #N/A.

