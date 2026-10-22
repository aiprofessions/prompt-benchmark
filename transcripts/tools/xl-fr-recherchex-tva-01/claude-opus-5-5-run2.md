# Transcript — xl-fr-recherchex-tva-01 — claude-opus-5-5 — run 2

- model_id: `claude-opus-5-5` (provider `anthropic`)
- started_utc: 2026-10-20T12:38:38+00:00
- duration_s: 17.9
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

   =RECHERCHEX(RECHERCHEX(A2;Articles!$A$2:$A$4;Articles!$C$2:$C$4);Taux!$A$2:$A$4;Taux!$B$2:$B$4)

   La formule cherche le code TVA de l'article dans « Articles », puis le taux correspondant dans « Taux ». Appliquez le format Pourcentage à la colonne E.

   Si votre Excel n'a pas RECHERCHEX (avant 2021 ou 365), utilisez :
   =INDEX(Taux!$B$2:$B$4;EQUIV(INDEX(Articles!$C$2:$C$4;EQUIV(A2;Articles!$A$2:$A$4;0));Taux!$A$2:$A$4;0))

2. Montants (à recopier vers le bas)

   F2 (HT)  : =ARRONDI(C2*D2;2)
   G2 (TVA) : =ARRONDI(F2*E2;2)
   H2 (TTC) : =F2+G2

3. Résultats

   Ligne   Article   Taux    HT         TVA       TTC
   2       FAR-25    5,5 %   220,80 €   12,14 €   232,94 €
   3       MOU-12    20 %    111,60 €   22,32 €   133,92 €
   4       TRA-01    10 %    145,00 €   14,50 €   159,50 €
   Total                     477,40 €   48,96 €   526,36 €

   Ligne 2 : la TVA brute vaut 12,144 €, arrondie à 12,14 €.

À vérifier

   - Les taux proviennent uniquement de votre feuille « Taux ». Faites confirmer leur application à chaque produit par votre comptable.
   - La TVA est arrondie ligne par ligne. Calculée sur le total HT par taux, elle peut différer d'un centime. Choisissez une méthode et gardez-la sur toutes vos factures.
   - Les taux de la colonne B de « Taux » doivent être des nombres (0,055 affiché 5,5 %), pas du texte. Si vous ajoutez des articles ou des codes, élargissez les plages $A$2:$A$4 (ou utilisez des tableaux structurés).

