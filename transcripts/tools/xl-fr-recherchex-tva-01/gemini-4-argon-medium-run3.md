# Transcript — xl-fr-recherchex-tva-01 — gemini-4-argon-medium — run 3

- model_id: `gemini-4-argon-medium` (provider `google`)
- started_utc: 2026-10-20T12:42:59+00:00
- duration_s: 28.3
- exit_code: 0
- attempts: 1
- completed: True
- rubric_sha256: 09a43241cc283546579b9f6941517efb5778d1ac3493814dcecbed11707135aa
- agy_usage: {"input_tokens": 1088, "output_tokens": 1286, "thinking_tokens": 387, "cache_read_tokens": 0, "total_tokens": 2374}
- agy_num_turns: 1
- agy_tool_calls: 0 (transcript steps 2)

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

Voici les formules et les résultats pour votre fichier Excel en français :

### 1. Formule du taux de TVA en `E2` (feuille « Facture »)
Pour récupérer d'abord le code TVA de l'article dans la feuille « Articles », puis le taux correspondant dans la feuille « Taux » (avec des références absolues `$` pour pouvoir recopier la formule vers le bas) :

* **Avec `RECHERCHEV` (toutes versions d'Excel) :**
  ```excel
  =RECHERCHEV(RECHERCHEV(A2;Articles!$A$2:$C$4;3;FAUX);Taux!$A$2:$B$4;2;FAUX)
  ```
* **Alternative avec `RECHERCHEX` (Excel 2021 / Microsoft 365) :**
  ```excel
  =RECHERCHEX(RECHERCHEX(A2;Articles!$A$2:$A$4;Articles!$C$2:$C$4);Taux!$A$2:$A$4;Taux!$B$2:$B$4)
  ```

---

### 2. Formules HT (`F2`), TVA (`G2`) et TTC (`H2`)
À saisir sur la ligne 2 puis à étirer vers le bas jusqu'à la ligne 4 :

* **Montant HT en `F2` :**
  ```excel
  =C2*D2
  ```
  *(ou `=ARRONDI(C2*D2;2)` si vos prix unitaires comportent plus de 2 décimales)*
* **Montant TVA arrondi au centime en `G2` :**
  ```excel
  =ARRONDI(F2*E2;2)
  ```
* **Montant TTC en `H2` :**
  ```excel
  =F2+G2
  ```

---

### 3. Valeurs obtenues pour les 3 lignes

| Ligne | Code article | Code TVA (via Articles) | E : Taux (via Taux) | F : HT (€) | G : TVA (€) | H : TTC (€) |
| :--- | :--- | :---: | :---: | :---: | :---: | :---: |
| **2** | FAR-25 | R | 5,5 % | **220,80** | **12,14** *(12,144 arrondi)* | **232,94** |
| **3** | MOU-12 | N | 20 % | **111,60** | **22,32** | **133,92** |
| **4** | TRA-01 | I | 10 % | **145,00** | **14,50** | **159,50** |

---

### 4. À vérifier
* **Format des cellules et plages :** Assurez-vous que la colonne `E` est bien au format **Pourcentage** (avec au moins 1 décimale pour afficher `5,5 %`) et pensez à agrandir les plages `$A$2:$C$4` et `$A$2:$B$4` (ou à utiliser des **Tableaux structurés** Excel) si vous ajoutez de nouveaux articles ou codes TVA.
* **Espaces invisibles dans les codes :** Vérifiez qu'aucun espace superflu ne s'est glissé avant ou après les codes articles (`FAR-25`, etc.) ou les codes TVA (`N`, `R`, `I`), ce qui provoquerait une erreur `#N/A`.
* **Méthode d'arrondi de la TVA :** Sur une facture comportant plusieurs lignes, la réglementation comptable/fiscale permet de calculer la TVA soit ligne par ligne (comme demandé ici en `G2`), soit sur le total HT par taux de TVA en bas de facture ; vérifiez que ce mode de calcul correspond bien au paramétrage de votre logiciel de comptabilité.
