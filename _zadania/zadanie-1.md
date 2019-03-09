---
layout: zadanie
cislo: 1
typ: Zadanie
predmet: wpub
title: Osobná webová prezentácia
github_url: https://github.com/MatusPilnan/MatusPilnan.github.io
---
Úlohou bolo vytvoriť si vlastné webové sídlo predovšetkým s pomocou nástroja [Jekyll](https://jekyllrb.com). Okrem tohoto nástroja je tu použitý aj [Bootstrap](https://getbootstrap.com/) na štýlovanie.

## Použité rozloženia (layouts)
V projekte sú použité nasledujúce rozloženia:
- **default** - základné rozloženie. Obsahuje HTML hlavičku s prepojeniami na potrebné CSS súbory a skripty (Bootstrap a [GitHub Buttons](https://buttons.github.io/)). Súčasťou tohoto layoutu je aj navigačný panel a päta stránky. Je použitý ako základ pre ostatné rozloženia a používajú ho všetky podstránky, ktoré nie sú generované z Markdown-u (teda domov, wpub, blog, about, hobbies a projects)  
- **post** - rozloženie pre blogový príspevok. Vo vrchnej časti je názov príspevku, dátum pridania a vypočítaný rozdiel, ako dávno bol príspevok pridaný. Nasleduje horizontálny oddelovač, pod ktorým je samotný príspevok. Pod príspevkom môže byť galéria obrázkov, pokiaľ ich príspevok má.  
- **zadanie** - rozloženie pre zadania a projekty. Nad nadpisom je odkaz na GitHub repozitár k danému projektu a tlačidlo na stiahnutie celého repozitára ako .zip súbor pomocou [GitHub Buttons](https://buttons.github.io/). Nasleduje názov zadania, horizontálny oddelovač a samotný obsah stránky týkajúci sa projektu (generovaný z Markdown-u).

## Použité premenné
V projekte sú použité nasledujúce premenné:
- Všeobecné:  
  - ```title``` - názov zadania, nadpis blogového príspevku, názov podstránky a pod.
- V projektoch:  
  - ```cislo``` - poradové číslo zadania,
  - ```typ``` - pre rozlíšenie zadaní a iných projektov,
  - ```predmet``` - študijný predmet, na ktorý bolo dané zadanie vypracované, predovšetkým používané na filtrovanie zadaní z WPUB,  
  - ```github_url``` - link na GitHub repozitár prislúchajúci danému projektu.
- V záujmoch:
  - ```obrazok``` - umiestnenie obrázku, ktorý sa má zobraziť na kartičke v zozname záujmov,
  - ```popis``` - krátky popis ktorý sa zobrazí na stránke so záujmami.
- V blogových príspevkoch:
  - ```date``` - dátum pridania príspevku,
  - ```obrazky``` - pole umiestnení obrázkov, ktoré sa majú zobraziť v galérii.

## Kolekcie
V projekte sú okrem základnej kolekcie blogových príspevkov ```posts``` použité dve vlastné kolekcie. Kolekcia ```zadania``` na zadania a projekty a kolekcia ```zaujmy``` na osobné záujmy. Z kolekcie ```zaujmy``` sa negenerujú samostatné stránky, obsah všetkých Markdown súborov sa vloží do stránky [Záujmy](/about/hobbies.html).

## Filtre a tagy
V projekte sú použité nasledujúce filtre a tagy:
- ```if```
  - v rozložení ```default``` na zvýraznenie aktuálnej stránky v navigačnom paneli,  
  - v rozložení ```post``` na rozhodnutie, či sa má vykresľovať galéria (či má príspevok aspoň jeden obrázok)
- ```for```
  - v rozložení ```post``` na vytvorenie karuselu s obrázkami
  - v stránkach, kde sa vykresľujú zoznamy na základe kolekcií (projekty, záujmy, zadania, blog)
- ```date_to_string``` v rozložení ```post``` a v stránke [Blog](/blog) na vypísanie dátumu pridania príspevku,
- ```timeago``` v rozložení ```post``` na slovné vypísanie toho, ako dávno bol príspevok pridaný (plugin [jekyll-timeago](https://github.com/markets/jekyll-timeago)),
- ```assign``` na vytvorenie dočasných zoznamov v stránkach [WPUB](/wpub) a [Projekty](/projects),
- ```where``` na vyfiltrovanie zadaní, ktoré majú premennú ```predmet``` nastavenú na hodnotu ```wpub``` pri zobrazovaní zadaní v sekcii [Webové publikovanie](/wpub)
- ```sort_natural``` a ```sort``` na zoradenie zadaní podľa abecedy,
- ```increment``` na zvyšovanie počítadla ID-čok HTML elementov ktoré sa majú schovávať na stránke [Záujmy](/aboutt/hobbies.html).

## Plugin
V projekte je použítý plugin [jekyll-timeago](https://github.com/markets/jekyll-timeago) na slovný výpis veku jednotlivých príspevkov na blogu.

