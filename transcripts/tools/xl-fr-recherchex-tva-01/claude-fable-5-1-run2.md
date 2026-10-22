# Transcript — xl-fr-recherchex-tva-01 — claude-fable-5-1 — run 2

- model_id: `claude-fable-5-1` (provider `anthropic`)
- started_utc: 2026-10-20T12:39:10+00:00
- duration_s: 17.7
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

1. E2 (taux de TVA via le code TVA de l'article), à recopier vers le bas :

   =RECHERCHEV(RECHERCHEV(A2;Articles!$A$2:$C$4;3;FAUX);Taux!$A$2:$B$4;2;FAUX)

   Variante avec INDEX/EQUIV si vous préférez :
   =INDEX(Taux!$B$2:$B$4;EQUIV(INDEX(Articles!$C$2:$C$4;EQUIV(A2;Articles!$A$2:$A$4;0));Taux!$A$2:$A$4;0))

2. Montants (à recopier vers le bas) :

   F2 (HT)  : =C2*D2
   G2 (TVA) : =ARRONDI(F2*E2;2)
   H2 (TTC) : =F2+G2

3. Valeurs obtenues :

   Ligne 2  FAR-25  taux 5,5 %   HT 220,80   TVA 12,14   TTC 232,94
   Ligne 3  MOU-12  taux 20 %    HT 111,60   TVA 22,32   TTC 133,92
   Ligne 4  TRA-01  taux 10 %    HT 145,00   TVA 14,50   TTC 159,50

   Totaux : HT 477,40 / TVA 48,96 / TTC 526,36

À vérifier :
   - Que la colonne B de « Taux » contient bien des nombres au format pourcentage (0,055 ; 0,2 ; 0,1) et non du texte « 5,5 % », sinon F2*E2 renverra #VALEUR!.
   - Que les codes TVA (R, N, I) sont saisis sans espace parasite dans les deux feuilles, sinon RECHERCHEV renverra #N/A.
   - Que la règle d'arrondi attendue est bien par ligne (ARRONDI de chaque TVA) et non sur le total ; selon le choix, les centimes de TVA globale peuvent différer.

