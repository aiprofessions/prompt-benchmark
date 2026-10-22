# Transcript — xl-fr-recherchex-tva-01 — gemini-4-argon-medium — run 1

- model_id: `gemini-4-argon-medium` (provider `google`)
- started_utc: 2026-10-20T12:35:26+00:00
- duration_s: 28.3
- exit_code: 0
- attempts: 1
- completed: True
- rubric_sha256: 09a43241cc283546579b9f6941517efb5778d1ac3493814dcecbed11707135aa
- agy_usage: {"input_tokens": 1088, "output_tokens": 979, "thinking_tokens": 0, "cache_read_tokens": 0, "total_tokens": 2067}
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

Voici les formules et les résultats basés uniquement sur vos tableaux (avec la syntaxe d'Excel en français).

### 1. Formule du taux de TVA en `E2` (feuille « Facture »)

Cette formule recherche d'abord le **Code TVA** de l'article dans la feuille `Articles`, puis utilise ce code pour récupérer le **Taux** dans la feuille `Taux`. Les références absolues (`$`) permettent de la recopier vers le bas sans décaler les plages de recherche :

* **Avec `RECHERCHEV` (compatible toutes versions d'Excel) :**
  ```excel
  =RECHERCHEV(RECHERCHEV(A2;Articles!$A$2:$C$4;3;FAUX);Taux!$A$2:$B$4;2;FAUX)
  ```
* **Alternative avec `RECHERCHEX` (Excel 2021 / Microsoft 365) :**
  ```excel
  =RECHERCHEX(RECHERCHEX(A2;Articles!$A$2:$A$4;Articles!$C$2:$C$4);Taux!$A$2:$A$4;Taux!$B$2:$B$4)
  ```

---

### 2. Formules HT, TVA et TTC sur la ligne 2 (à recopier vers le bas)

* **Montant HT en `F2` :**
  ```excel
  =C2*D2
  ```
  *(ou `=ARRONDI(C2*D2;2)` si vos prix unitaires ou quantités peuvent comporter plus de décimales)*
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

| Ligne | A : Code article | E : Taux (via code) | F : HT (€) | G : TVA (€) | H : TTC (€) |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **2** | FAR-25 | 5,5 % *(code R)* | **220,80** *(18,40 × 12)* | **12,14** *(220,80 × 5,5 % = 12,144)* | **232,94** |
| **3** | MOU-12 | 20 % *(code N)* | **111,60** *(27,90 × 4)* | **22,32** *(111,60 × 20 %)* | **133,92** |
| **4** | TRA-01 | 10 % *(code I)* | **145,00** *(145,00 × 1)* | **14,50** *(145,00 × 10 %)* | **159,50** |

---

### 4. À vérifier
* **Format des cellules :** Assurez-vous que la colonne `E` est au format **Pourcentage** (avec 1 ou 2 décimales pour bien afficher `5,5 %`) et que les colonnes `C`, `F`, `G` et `H` sont au format **Monétaire** ou **Nombre** à 2 décimales.
* **Extension des plages :** Si vous ajoutez de nouveaux articles ou codes TVA à l'avenir, pensez à agrandir les plages `$A$2:$C$4` et `$A$2:$B$4` dans la formule en `E2` (ou convertissez vos plages en **Tableaux structurés** Excel via `Insertion > Tableau` pour que les plages s'adaptent automatiquement).
* **Méthode d'arrondi de la TVA :** Le calcul et l'arrondi de la TVA sont effectués ici ligne par ligne (`G2`). Vérifiez que ce mode de calcul (plutôt qu'un calcul de la TVA sur le total HT global par taux en bas de facture) correspond bien à vos usages de facturation et à votre logiciel comptable.
