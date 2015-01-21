---
layout: page
title: FAFF25
---

# **Disclaimer: Swedish notes for my course on photonics**

# Kapitel 12: Reflektion och brytning

<hr>

#### **Våg- eller partikelteori**

**Isaac Newton (1642-1727)** valde partikelteorin på grund av att tunna ljusstrålar inte skulle kunna utbreda sig i ett elastiskt material utan att spridas ut.

**Thomas Young (1773-1829)** redovisade sitt berömda dubbelspaltförsök år 1802 vilket resulterade i att partikelteorin dog ut sakta men säkert.

**Foucault** visade år 1850 att ljusets fart var mindre i vatten än i luft vilket fick korpuskelteorin att dö ut fullständigt.

<hr>

#### **Huygens princip**
**Robert Hooke (1635-1703)** introducerade en vågteori för ljus. Färgerna, som uppkommer via interferens i tunna skikt, förklarades med att ljuset är en vågrörelse.

**Christian Huygens (1629-1695)** utnyttjade vågteorin framgångsrikt.

> **Huygens princip:**

> Varje punkt på en vågfront utgör en källa för cirkulära elementarvågor. Varje elementarvåg har samma frekvens och utbredningshastighet som primärvågen i den punkten. Primärvågens position vid en senare tidpunkt konstrueras fram med hjälp av elementarvågorna.

*Huygens princip* kan t.ex. visa varför vågfronterna böjs när en plan våg passerar ett hinder.

*Huygens* lyckades härleda **reflektions**- och **brytningslagen** med att förklara **böjning** och **dubbelbrytning**.

**Augustin Jean Fresnel (1788-1827)** satte samman **Youngs** superpositionsprincip och **Huygens** princip till dagens förklaring av ljusets vågnatur.

**Huygens princip** förklarar brytningen för vågfronter vid övergång mellan två material med olika våghastighet.

<hr>

#### **Geometrisk optik**

Böjning uppstår när vågor passerar ett hinder som är till storlek samma som våglängden.

Kan försumma böjningsfenom då våglängden är förhållandevis kort, ljus beter sig rätlinjigt i homogena material.

<hr>

#### **Skugga**

**Kärnskugga:** Med punktformig ljuskälla blir gränsen mellan ljus och mörker skarp.

**Halvskugga:** Med bred ljuskälla bildas en halvskugga runtom en kärnskugga.

Avstånd från ljuskällan påverkar halvskuggans utseende.

<hr>

#### **Brytningslagen**

Med hjälp av **Huygens princip** kan vi härleda brytningslagen för ljus:

> **Brytningslagen:**
{% include katex_import.html %}
<div class="equation" data-expr="\footnotesize{n_1\sin(a_1) = n_2\sin(a_2)}"></div>
<div class="equation" data-expr="\tiny{n_1 = \text{refractive index for material 1}}"></div>
<div class="equation" data-expr="\tiny{n_2 = \text{refractive index for material 2}}"></div>
<div class="equation" data-expr="\tiny{\sin(a_1) = \lambda_1  \text{wavelength for the incoming ray}}"></div>
<div class="equation" data-expr="\tiny{\sin(a_2) = \lambda_2 \text{wavelength for the outgoing ray}}"></div>
{% include katex_render.html %}

**Brytningslagen** är **våglängdsberoende**.

**Exempel:** Fiskar man med pilbåge måste man sikta framför objektet som man ser ovan vattenytan.

<hr>
#### **Reflektionslagen**

Om en plan våg åker mot gränsen mellan två olika medium kommer en del av vågen att reflekteras tillbaka.
Reflektionen kommer att utbreda sig med samma fart som den infallande fast i normalriktningen till den ursprungliga riktningen.

> **Reflektionslagen:**

> Infallsvinkeln är lika med utfallsvinkeln.

<hr>
#### **Reflektans***

Det reflekteras alltid ljus vid gränsövergång.

> ** Reflektansen R**
{% include katex_import.html %}
<div class="equation" data-expr="\footnotesize{R = \frac{I_{\text{refl}}}{I_{\text{in}}}}"></div>
{% include katex_render.html %}

> Om strålningen infaller vinkelrätt mot gränsytan:

{% include katex_import.html %}
<div class="equation" data-expr="\footnotesize{R = \left(\frac{n_2-n_1}{n_2+n_1}\right)^2}"></div>
{% include katex_render.html %}

**Exempel på applicering:** Hur mycket ljus går genom en fönsterruta respektive treglasfönster?

<hr>
#### **Totalreflektion**
Utfallsvinkeln är 90 grader.

> **Totalreflektion:**
{% include katex_import.html %}
<div class="equation" data-expr="\footnotesize{n_1\sin{a_{\text{g}}} = n_2\sin{90^{\text{o}}}}"></div>
<div class="equation" data-expr="\footnotesize{a_{\text{g}} = \arcsin{\frac{n_2}{n_1}}}"></div>
{% include katex_render.html %}
> Om infallsvinkeln är större än a_g så totalreflekteras ljuset.

<hr>
#### **Optisk tunneleffekt**

Ljusvågor kan tunnlas genom ett gap och t.ex. få ett objekt att se ut som om det befinner sig på två ställen samtidigt.
Termen finns även inom kvantfysiken.

<hr>
#### **Fiberoptik**
I **optiska fibrer** kan ljus traversera långa sträckor genom att totalreflekteras inuti kärnen av det optiska fibret.

**Kärnan** omsluts av en **mantel**.

**Överhöring** eller **cross-talk** kan uppstå via optisk tunneleffekt då optiska fibrer kommer nära varandra.
**Manteln** skyddar mot detta. **Kärnan** måste ha ett högre brytningsindex än **manteln**.

<hr>
#### **Prismor**

Prismor kan användas för att vinkla ljus.
Vinklingen kallas för **deviation**. Det sker alltid en diviation, den minsta sådana kallas för **minimidiviation**.

{% include katex_import.html %}
<div class="equation" data-expr="\footnotesize{}"></div>
{% include katex_render.html %}
