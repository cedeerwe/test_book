---
jupytext:
  text_representation:
    format_name: myst
kernelspec:
  display_name: Python 3
  name: python3
---


# Šestka v šiestich III.

Potom ako si Ýzy našiel chybu vo výpočtoch, rozhodol sa pozrieť sa na svoj kód. To je často desivá predstava hocikoho, kto napísal ľubovoľný kus kódu. O to desivejšie to je ešte pre tých ako ste vy, ktorí ten kód ani nenapísali. 

Jeden zo skvelých spôsobov ako hľadať chyby v kóde je napísať si naň základné testy. Najčastejšie je totiž chyba úplne triviálna a základné testy ju odhalia. Pozrime sa napríklad na našu prvú funkciu:
```{code-cell} ipython3
from random import randint # sprístupníme si funkciu na vygene rovanie náhodných celých čísel

def hod_kockou(): # zadefinujeme si vlastnú funkciu "hod_kockou" 
    return randint(1, 7) # vygenerujeme celé číslo medzi 1 (vrátane) a 7 (nevrátane)
```
Ýzy sa pozrie na túto funkciu a povie si o nej nejaké základné predpoklady. Napríklad je zjavné, že očakávame od nej iba hodnoty $\{1,2,3,4,5,6\}$. Skúste to otestovať sami. Stlačte hore tlačídlo `BinderHub`, ktoré vám otvorí túto stránku v interaktívnej verzii.

```{code-cell} ipython3
# tu otestujte, či naša funkcia vracia iba čísla {1,2,3,4,5,6}. 
```

