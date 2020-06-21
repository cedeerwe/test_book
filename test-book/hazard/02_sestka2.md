# Šestka v šiestich II.

V matematickej časti sme robili veľmi veľa výpočtov. Chyba sa mohla stať veľmi jednoducho. Namiesto kontrolovania každého riadku skúsime spočítať počet možností, keď nepadne ani jedna šestka a porovnať tento výsledok s počtom všetkých možností a počtom možností, keď padla aspoň jedna šestka.

Táto úloha je výrazne ľahšia ako tá predchádzajúca. Na každom mieste nepadne šestka, ale hocičo iné a teda môžme jednoducho spočítať $5^6 = 15\,625$. Počet vyhovujúcich možností bude počet všetkých, bez počtu nevyhovujúcich. Počet vyhovujúcich by teda mal byť $46\,656 - 15\,625 = 31\,031$. Nám vyšlo v predchádzajúcej časti niečo iné. Našli sme chybu! Skvelé. Ýzy ju aj našiel na predchádzajúcej strane, podarí sa to aj vám?

Náš opravený výsledok teda bude
```{math}
\frac{31\,031}{46\,656} \approx 0.665. 
```
To je stále zhruba rovnako ďaleko od výsledku simulácie.

```{admonition} Otázka
:class: tip
Čo je zle?
```