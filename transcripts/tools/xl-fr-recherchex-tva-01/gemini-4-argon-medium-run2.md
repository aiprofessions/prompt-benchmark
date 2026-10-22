# Transcript — xl-fr-recherchex-tva-01 — gemini-4-argon-medium — run 2

- model_id: `gemini-4-argon-medium` (provider `google`)
- started_utc: 2026-10-20T12:39:16+00:00
- duration_s: 13.4
- exit_code: 0
- attempts: 1
- completed: True
- rubric_sha256: 09a43241cc283546579b9f6941517efb5778d1ac3493814dcecbed11707135aa
- agy_usage: {"input_tokens": 1088, "output_tokens": 863, "thinking_tokens": 0, "cache_read_tokens": 0, "total_tokens": 1951}
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

Voici les formules et les résultats basés uniquement sur vos tableaux :

### 1. Formule pour le taux de TVA (cellule E2)
Pour récupérer le code TVA dans la feuille « Articles » à partir du code article (A2), puis chercher le taux correspondant dans la feuille « Taux » :

* **Avec toutes les versions d'Excel (`RECHERCHEV`) :**
  ```excel
  =RECHERCHEV(RECHERCHEV(A2;Articles!$A$2:$C$4;3;FAUX);Taux!$A$2:$B$4;2;FAUX)
  ```
* **Alternative avec Excel 365 / 2021 (`RECHERCHEX`) :**
  ```excel
  =RECHERCHEX(RECHERCHEX(A2;Articles!$A$2:$A$4;Articles!$C$2:$C$4);Taux!$A$2:$A$4;Taux!$B$2:$B$4)
  ```
*(Les signes `$` permettent de figer les plages pour recopier la formule vers le bas jusqu'en E4).*

---

### 2. Formules de calcul (cellules F2, G2 et H2)
À saisir sur la ligne 2 puis à recopier vers le bas :

* **Montant HT (en F2) :**
  ```excel
  =C2*D2
  ```
  *(Si vos prix unitaires sont eux-mêmes issus de calculs, vous pouvez sécuriser avec `=ARRONDI(C2*D2;2)`).*

* **Montant TVA arrondi au centime (en G2) :**
  ```excel
  =ARRONDI(F2*E2;2)
  ```

* **Montant TTC (en H2) :**
  ```excel
  =F2+G2
  ```

---

### 3. Valeurs obtenues pour les 3 lignes

| Ligne | Code article | E : Taux (via code) | F : HT | G : TVA (arrondie) | H : TTC |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Ligne 2** | FAR-25 | 5,5 % *(Code R)* | **220,80 €** | **12,14 €** *(12,144)* | **232,94 €** |
| **Ligne 3** | MOU-12 | 20 % *(Code N)* | **111,60 €** | **22,32 €** | **133,92 €** |
| **Ligne 4** | TRA-01 | 10 % *(Code I)* | **145,00 €** | **14,50 €** | **159,50 €** |

---

### 4. À vérifier
* **Format de nombre :** Assurez-vous que la colonne **E** est au format *Pourcentage* (avec 1 décimale pour afficher 5,5 %) et les colonnes **F à H** au format *Monétaire* ou *Nombre* à 2 décimales.
* **Plages de recherche :** Si vous ajoutez de nouveaux articles ou taux à l'avenir, pensez à étendre les plages bloquées (`$A$2:$C$4` et `$A$2:$B$4`) ou à convertir vos plages en **Tableaux structurés** Excel (`Insertion > Tableau`).
* **Méthode d'arrondi de la TVA :** Le calcul ci-dessus arrondit la TVA à la ligne (`G2`). Vérifiez que cette méthode correspond bien aux règles de gestion de votre logiciel comptable (plutôt qu'un arrondi calculé sur le total HT par taux en pied de facture).
