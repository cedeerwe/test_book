---
jupytext:
  text_representation:
    extension: .md
    format_name: myst
    format_version: '0.8'
    jupytext_version: '1.4.1'
kernelspec:
  display_name: Python 3
  language: python
  name: python3
---

Simulácia
============

Podobných simulácii sme už na minulej hodine niekoľko robili, nemalo by ísť o nič nové. Pozorne si ale kód prečítajte, aby ste mu dobre rozumeli a vedeli aj sami napísať niečo podobné.

```{code-cell} ipython3
import random
HLAVA = "H" # uložíme si tieto dva špeciálne znaky, aby sa nám lepšie čítal kód
ZNAK = "Z"

def hadz_hlava_hlava_proti_hlava_znak():
    posledny_hod = ""
    while True:
        hod = HLAVA if random.random() < 0.5 else ZNAK
        # porovnáme minulý hod a súčasný proti hlave a znaku.
        if [posledny_hod, hod] == [HLAVA, ZNAK]: 
            return 1 # vyhral prvý hráč
        # porovnáme minulý hod a súčasný proti hlave a hlave.
        if [posledny_hod, hod] == [HLAVA, HLAVA]: 
            return 0 # vyhral druhý hráč
        posledny_hod = hod # ak nikto nevyhral, súčasným hodom si prepíšeme posledný
```

```{code-cell} ipython3
hadz_hlava_hlava_proti_hlava_znak()
```

```{code-cell} ipython3
N = 10000
sum(hadz_hlava_hlava_proti_hlava_znak() for i in range(N)) / N
```