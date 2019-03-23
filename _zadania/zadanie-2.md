---
layout: zadanie
cislo: 2
typ: Zadanie
predmet: wpub
title: Transformácia vybraného dokumentu do formátu DocBook
github_url: https://github.com/MatusPilnan/wpub-docbook
---
Pôvodný text bol do DocBook formátu z .docx zkonvertovaný [online nástrojom](http://www.xmlmind.com/w2x/docx_to_docbook.html). Text je členený na kapitoly a podkapitoly elementami ```<chapter>``` a ```<section>```, prílohu tvorí element ```<appendix>```. Nadpisy častí sú určené elementmi ```<title>```. Zvýraznenie textu je použité v tabuľkách (bold na názvy stĺpcov) a v prílohe (podčiarknutie), použitý je element ```<emphasis>``` s atribútom ```role```. Odrážky sú použité v kapitole 1.5.8. Odkazy na URL (element ```<ulink>``` s atribútom ```url```) sú v poznámkach pod čiarou (element ```<footnote>```), napríklad na 12. strane. Obrázok aj s odkazom (element ```<xref>``` s atribútom ```linkend```) v texte je napríklad v kapitole 2.1, tabuľka je ve kapitole 1.5.5. Pre vygenerovanie zoznamu obrázkov a tabuliek bola urobená nasledujúca zmena v šablóne:
```
<xsl:param name="generate.toc">
book      title,toc,figure,table
</xsl:param>
```
Zoznam použitej literatúry je tvorený elementom ```<bibliography>```, elementami ```<bibliomixed>```, na citácie sú použité elementy ```<citation>``` v texte a ```<abbrev>``` pri jednotlivých zdrojoch. Forma bibliografických záznamov je taká, akú vygeneroval Word pri vytváraní bibliografie podľa svojej šablóny ISO690. Register pojmov je vygenerovaný elementom ```<index />```, jednotlivé záznamy registra sú v elementoch ```<indexterm>```, ```<primary>``` alebo ```<secondary>``` na príslušných miestach v texte. 

Šablóna titulnej strany bola zmenená nasledovne:
```
<xsl:template name="book.titlepage.before.recto"><fo:block hyphenate="false" xmlns:fo="http://www.w3.org/1999/XSL/Format" text-align="center" font-size="20pt" border-bottom-width="0.5pt" border-bottom-style="solid" font-family="sans-serif" text-transform="uppercase">
      <xsl:value-of select="/book/bookinfo//affiliation/orgname"/>
    </fo:block><fo:block xmlns:fo="http://www.w3.org/1999/XSL/Format" space-before="6pt" text-align="center" font-size="14pt" font-family="sans-serif">
      <xsl:value-of select="/book/bookinfo//affiliation/orgdiv[@role='fakulta']"/>
    </fo:block><fo:block xmlns:fo="http://www.w3.org/1999/XSL/Format" space-before="3pt" text-align="center" font-size="12pt" font-family="sans-serif">
      <xsl:value-of select="/book/bookinfo//affiliation/orgdiv[@role='katedra']"/>
    </fo:block><fo:block xmlns:fo="http://www.w3.org/1999/XSL/Format" space-before="12pt" space-after="1cm" text-align="center">
      <fo:external-graphic src="url(BP-NER-Pilnan_files\STU-FIIT-zcv.png)" width="6cm" content-width="scale-to-fit"/>
    </fo:block>
</xsl:template>
```
- vypnutie rozdeľovania slov
- zmena obrázku (logo fakulty)
- preklad „Vedoucí“ na „Vedúci“ práce (nie je v ukážke)


