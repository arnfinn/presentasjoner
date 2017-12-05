name: normal
layout: true
class: left, inverse

---
name: oppgave
layout: true
class: left

---
name: inverse
layout: true
class: center, middle, inverse
---
template: inverse

.title[SAS-makroer]

.subtitle[Internkurs ved SKDE]

.author[Arnfinn og Hanne Sigrun]

.date[Sjette desember 2017, Tromsø]

.footnote[Presentasjonen finnes her: [https://tinyurl.com/makrokurs](https://tinyurl.com/makrokurs)]


---
template: inverse

# Hva er en SAS-makro?

---
template: normal

# SAS-makro

```sas
%macro makronavn(parameter1 = , parameter2 = );

 /*
 Gjør noe her
 */ 

%mend;
```

---
template: normal

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
template: normal

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
template: oppgave

# Oppgave

```sas
%macro makronavn(parameter1 = default1, parameter2 = default2);
 
%put NOTE: parameter1 er &parameter1;
%put NOTE: parameter2 er &parameter2;
 
%mend;
```

1. Kjør makroen med og uten parametere. Hva blir resultatet?
2. Prøv å kjøre koden `%put NOTE: parameter1 er &parameter1;` utenfor makroen.
3. Lag tilsvarende makro som ikke tar argumenter, ved bruk av makrovariabler (`%let ...;`). Er det noen fordeler eller ulemper ved å gjøre det slik?
4. Ekstraoppgave: bytt ut `NOTE` med `ERROR`. Hva skjer i loggen? Hvordan kan man bruke dette i en makro? Hvilken konsekvens får dette?

---
template: inverse

# Felles makroer

---
template: normal

# Felles makroer

- Disse ligger på `\\tos-sas-skde-01\SKDE_SAS\Makroer\master` og kan brukes ved å legge inn følgende i sas-programmet
```sas
%let filbane=\\tos-sas-skde-01\SKDE_SAS\;
options sasautos=("&filbane.Makroer\master" SASAUTOS);
```

--

- Eksempel: legge til `bohf` etc. i et datasett, ved bruk av `boomraader`-makroen:
```
data avd;
set npr_skde.T17_magnus_avd_2016;
%boomraader;
run;
```

--
- Kan bruke andre definisjoner av boområder, ved å sende inn parametre.

--
- Dokumentasjon finnes her: [skde-analyse.github.io/sas_macroer](http://skde-analyse.github.io/sas_macroer/)

---
template: inverse

# Oppgave

---
template: oppgave

# Oppgave

```
data avd;
set npr_skde.T17_magnus_avd_2016;
%boomraader;
run;
```

- Kjøre `boomraade`-makroen på `npr_skde.T17_magnus_avd_2016` slik at *Bergen* blir splittet på boområdene *Bergen* og *Haraldsplass*.
- Se på kildekoden til makroen `VarFraParvus`. Hva gjør den og hvordan gjør den det?

---
template: inverse

# Bivirkninger

---
template: normal

# Bivirkninger ("Side effects")

- En makro som ikke har bivirkninger vil kun returnere *verdier*, basert på hva man sender inn.

--

- Makroene våre har neste alltid bivirkninger:
  - Legger til verdier i datasett
  - Lager nye datasett
  - Lager andre filer og output

--
- Noe man må være klar over når man lager makroer, spesielt hvis de skal brukes av andre.
  - Den som kjører makroen burde vite hva slags bivirkninger makroen gir
  - Den som lager makroen burde sørge for at makroen ikke gir uønskede bivirkninger

---
template: inverse

# Oppgave

---
template: oppgave

# Oppgave

1. Førte makroen `boomraader` til noen bivirkninger i forrige oppgave? Kan det være noen av disse var uønskede?
2. Kjør makroen `VarFraParvus` med `avd`-datasettet (hent f.eks *emigrertDato*) som mangler `aar`. Hva skjer med datasettet ditt?

---
template: inverse

# Oppgave

---
template: oppgave

# Oppgave


- Tell antall avdelingsopphold (kontakter) i 2016 for menn i følgende aldersgrupper, uten bruk av makro og presenter i tabell:

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

- Gjør det så med en makro.

--
- gjør det heller for kvinner.

---




De forhåndsvalge parametrene `default1` og `default2` blir her erstattet med `ditt` og `datt`.

