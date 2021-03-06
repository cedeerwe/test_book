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


# Výhody transmisívneho a konštruktivistického štýlu - pokračovanie

Ak ste si dali záležať, tabuľky v minulej časti nebolo moc jednoduché vyplniť. Jednak, že sa celkom líšili v jednotlivých situáciách, ale taktiež aj preto, lebo situácia nie je taká jednoduchá, aby sa dala zapísať do tabuľky. Dovolili sme si zakresliť porovnanie transmisívneho a konštruktivistického štýlu do grafu.

```{code-cell} ipython3
:tags: ["remove-input"]
import plotly.graph_objects as go
import numpy as np

fig = go.Figure()

x = np.arange(0, 9, 0.1)

fig.add_trace(
    go.Scatter(
        line=dict(color="red"),
        name="transmisívne",
        x = x,
        y =  -np.multiply(x - 5, x - 5) / 25 + 1
    )
)

fig.add_trace(
    go.Scatter(
        line=dict(color="blue"),
        name="konštruktívne",
        x = x,
        y = x / 10
    )
)

fig.update_xaxes(showticklabels=False, title="čas", title_font={"size": 15}, showgrid=False, zeroline=False)
fig.update_yaxes(showticklabels=False, title="vedomosti", title_font={"size": 15}, showgrid=False, zeroline=False)
fig.update_layout(
    title="Zavádzajúci názorný obrázok konštruktistického vs. trasmisívneho vzdelávania",
    title_font={"size": 18},
    annotations=[
        dict(
            x=0,
            y=0,
            xref="x",
            yref="y",
            text="nájdenie návodu",
            showarrow=True,
            arrowhead=7,
            ax=70,
            ay=-220,
            font={"size": 12, "color": "red"}
        ),
        dict(
            x=5,
            y=1,
            xref="x",
            yref="y",
            text="použitie vedomostí",
            showarrow=True,
            arrowhead=7,
            ax=0,
            ay=40,
            font={"size": 12, "color": "red"}
        ),
        dict(
            x=1,
            y=1/10,
            xref="x",
            yref="y",
            text="experimentovanie",
            showarrow=True,
            arrowhead=7,
            ax=20,
            ay=40,
            font={"size": 12}
        ),
        dict(
            x=3,
            y=3/10,
            xref="x",
            yref="y",
            text="horší stav ako na začiatku",
            showarrow=True,
            arrowhead=7,
            ax=0,
            ay=-60,
            font={"size": 12}
        ),
        dict(
            x=6,
            y=6/10,
            xref="x",
            yref="y",
            text="naučenie sa úplne nesúvisiacej blbosti",
            showarrow=True,
            arrowhead=7,
            ax=0,
            ay=70,
            font={"size": 12}
        ),
        dict(
            x=8,
            y=8/10,
            xref="x",
            yref="y",
            text="už tomu rozumieme",
            showarrow=True,
            arrowhead=7,
            ax=0,
            ay=-40,
            font={"size": 12}
        )
    ])

fig.show()
```

Ako samotný názov grafu napovedá, je zavádzajúci. Situácia môže totiž vyzerať úplne ináč a veľmi záleží od konkrétnych okolností, ako by takýto graf vyzeral. Na teraz ale ignorujme fakt, že je zavádzajúci a poďme ho trocha zanalyzovať.

Ak máme na daný problém k dispozícií návod alebo ľubovoľný zdroj, naše pochopenie začne rásť veľmi rýchlo. Využívame znalosti iných ľudí o danej problematike a vďaka tomu sa posúvame rýchlo dopredu. Vystihuje to aj známa fráza [standing on the shoulders of the giants](https://en.wikipedia.org/wiki/Standing_on_the_shoulders_of_giants). Veľmi často sa ale stane, že tieto znalosti všetky spracujeme, využijeme a potom ich postupne stratíme. Keď je na daný proces dostupný návod, načo by sme si ho pamätali? Bohužiaľ, veľmi často sa v školách vyučuje presne takýmto spôsobom. Žiaci sa naučia návod na riešenie problému, napíšu písomku a následne znalosti zabudnú. Ak nie hneď, tak skoro určite o niekoľko rokov neskôr. Pamätáte si napríklad na to, čo je to striedavý uhol?

Na druhej strane máme konštruktivizmus, ktorý sa podobá skôr na hranie ako na učenie. S problematikou experimentujeme a pomaly sa o nej učíme. Postupujeme výrazne pomalšie, ako keby sme si čítali návod, predsa len si ho musíme sami vymyslieť namiesto toho, aby sme si ho iba prečítali. Celý čas sa ale učíme, aj keď nie nutne veci, čo priamo súvisia s našou úlohou. Splniť úlohu sa nám ale pravdepodobne podarí výrazne neskôr, ako za pomoci nejakej pomôcky. Ak sa nám ju vôbec podarí splniť.

Ak je úloha veľmi zložitá (napríklad postavenie atómovej elektrárne), neprichádza v úvahu postaviť sa k nej konštruktivisticky. Veľa ľudí strávilo veľa času, aby vyskúšali a spísali všetky vedomosti o danej problematike, ktoré musíme nutne využiť, aby sme sa mohli pohnúť ďalej. Často trvalo niekoľko desiatok až stoviek rokov na niečo prísť a nemali by sme tento fakt ignorovať.

Ak je úloha naopak rozumne jednoduchá, má cenu nechať človeka, aby na riešenie prišiel sám. Ak napríklad dostanete za úlohu narúbať drevo a nepovedia vám ako, chvíľu bude trvať, kým zistíte, ako to ide najlepšie. Počas toho času ale rovnako zistíte, prečo sú všetky ostatné spôsoby horšie, čo by ste sa nikdy nedozvedeli, keby vám niekto rovno povedal, čo máte robiť. Učenie bude trvať kúsok dlhšie, ale budete tomu rozumieť lepšie, lebo si to viete sami vysvetliť.

Oba prístupy majú svoje plusy a mínusy. Ak chcete niečo spraviť rýchlo a nepotrebujete vedieť, prečo to riešenie funguje, siahnete po návode. Ak sa niečo chcete naučiť poriadne, skúsite si to vymyslieť sami. Dieťaťu je dobré povedať, aby nebehalo na cestu, ale rovnako je úplne v poriadku ak sa dieťa naučí samé od seba chodiť. Pri chodení riskujeme akurát to, že padne a bude to skúšať znova. Pri ceste riskujeme omnoho viac. Všetko závisí od kontextu. Nedá sa povedať, že niektorí z prístupov je univerzálne lepší.

Musíme na záver povedať, že porovnávať tieto dva prístupy na teoretickej rovine nie je úplne ono. Treba si oba prístupy zažiť, najlepšie z oboch strán. Po našich zamysleniach budeme pokračovať k poslednej otázke a tá je: *Prečo nie je konštruktivizmus viac rozšírený?*. Opäť vám odporúčame premyslieť si znova túto otázku po čerstvo nadobudnutých vedomostiach.