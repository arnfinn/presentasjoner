var slideshow = remark.create({
  // Set the slideshow display ratio
  // Default: '4:3'
  // Alternatives: '16:9', ...
  ratio: '4:3',

  // Navigation options
  navigation: {
    // Enable or disable navigating using scroll
    // Default: true
    // Alternatives: false
    scroll: true,

    // Enable or disable navigation using touch
    // Default: true
    // Alternatives: false
    touch: true,

    // Enable or disable navigation using click
    // Default: false
    // Alternatives: true
    click: false
  },

  // Customize slide number label, either using a format string..
  slideNumberFormat: 'Slide %current% of %total%',
  // .. or by using a format function
  slideNumberFormat: function (current, total) {
    return 'Slide ' + current + ' of ' + total;
  },

  // Enable or disable counting of incremental slides in the slide counting
  countIncrementalSlides: true
}); 

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
class:left, inverse

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
class:left, inverse

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
layout: false
class:left, inverse

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

# Oppgave 2


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

