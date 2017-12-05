
name: inverse
layout: true
class: center, middle, inverse
---
##Internkurs om
#SAS-makroer

.author[Arnfinn Hykkerud og Hanne Sigrun]

.date[5. desember 2017, Tromsø]

.footnote[Presentasjonen finnes på [GitHub](https://github.com/arnfinn/presentasjoner/makrokurs_2017_12_06)]


---

template: inverse
# Hva er en SAS-makro?

---
layout: false
class:left

# SAS-makro

```sas
%macro makronavn(parameter1 = , parameter2 = );
 /*
 Gjør noe her
 */
 
%mend;
```


---
layout: false
class:left

# SAS-makro

```sas
%macro makronavn(parameter1 = default1, parameter2 = default2);
 /*
 Gjør noe her
 */
 
%mend;
```


--

# SAS-makro

Kjøres slik:

```sas
%makronavn(parameter1 = ditt, parameter2 = datt);
```

--

De forhåndsvalge parametrene `default1` og `default2` blir her erstattet med `ditt` og `datt`.

