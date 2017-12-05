
name: inverse
layout: true
class: center, middle, inverse
---

.title[SAS-makroer]

.subtitle[Internkurs ved SKDE]

.author[Arnfinn og Hanne Sigrun]

.date[Sjette desember 2017, Tromsø]

.footnote[Presentasjonen finnes her: [https://tinyurl.com/makrokurs](https://tinyurl.com/makrokurs)]


---

name: agenda

# Agenda

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

# SAS-makro

```sas
%macro makronavn(parameter1 = , parameter2 = );
 
%put NOTE: parameter1 er &parameter1;
%put NOTE: parameter2 er &parameter2;
 
%mend;
```

--

Kjøres slik:

```sas
%makronavn(parameter1 = ditt, parameter2 = datt);
```

---

# SAS-makro

```sas
%macro makronavn(parameter1 = default1, parameter2 = default2);
 
%put NOTE: parameter1 er &parameter1;
%put NOTE: parameter2 er &parameter2;
 
%mend;
```

Kjøres slik:

```sas
%makronavn(parameter1 = ditt, parameter2 = datt);
```

--
Eller slik
```sas
%makronavn;
```

---

template: inverse
# Oppgave 1

---

# Oppgave

- ...


---

template: inverse
# Oppgave 2

---



- Tell antall avdelingsopphold (kontakter) i 2016 for menn i følgende aldersgrupper:

| Gruppe | Alder |
| --- | ---: | 
| 1 | 0-9 år   |
| 2 | 10-19 år |
| 3 | 20-29 år |
| 4 | 30-39 år |
| 5 | 40-49 år |
| 6 | 50-59 år |
| 7 | 60-69 år |
| 8 | 70-79 år |
| 9 | 80-89 år |

- Presenter i tabell

---




De forhåndsvalge parametrene `default1` og `default2` blir her erstattet med `ditt` og `datt`.

