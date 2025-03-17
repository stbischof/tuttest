# Documentation
### CatalogName : Schulwesen
### Schema Schulwesen : 
---
### Cubes :

    Schulen in Jena (Institutionen), Pädagogisches Personal an Jenaer Schulen, Schüler:innen an Jenaer Schulen

---
#### Cube "Schulen in Jena (Institutionen)":

    

##### Table: "fact_schulen"

##### Dimensions:
##### Dimension "Schulen":

Hierarchies:

    Schulen nach Ganztagsangebot, Schulen nach Trägerschaft, Schulen nach Art

##### Hierarchy Schulen nach Ganztagsangebot:

Tables: "schule,ganztags_art"

Levels: "Art des Ganztagsangebots, Schule"

###### Level "Art des Ganztagsangebots" :

    column(s): id

###### Level "Schule" :

    column(s): id

##### Hierarchy Schulen nach Trägerschaft:

Tables: "schule,traeger,traeger_art,traeger_kategorie"

Levels: "Schulträger-Kategorie, Schulträger-Art, Schulträger, Schule"

###### Level "Schulträger-Kategorie" :

    column(s): id

###### Level "Schulträger-Art" :

    column(s): id

###### Level "Schulträger" :

    column(s): id

###### Level "Schule" :

    column(s): id

##### Hierarchy Schulen nach Art:

Tables: "schule,schul_art,schul_kategorie"

Levels: "Schulkategorie, Schulart, Schule"

###### Level "Schulkategorie" :

    column(s): id

###### Level "Schulart" :

    column(s): id

###### Level "Schule" :

    column(s): id

##### Dimension "Schuljahr":

Hierarchies:

    Schuljahre

##### Hierarchy Schuljahre:

Tables: "schul_jahr"

Levels: "Schuljahr"

###### Level "Schuljahr" :

    column(s): id

---
#### Cube "Pädagogisches Personal an Jenaer Schulen":

    

##### Table: "fact_personal"

##### Dimensions:
##### Dimension "Schulen":

Hierarchies:

    Schulen nach Ganztagsangebot, Schulen nach Trägerschaft, Schulen nach Art

##### Hierarchy Schulen nach Ganztagsangebot:

Tables: "schule,ganztags_art"

Levels: "Art des Ganztagsangebots, Schule"

###### Level "Art des Ganztagsangebots" :

    column(s): id

###### Level "Schule" :

    column(s): id

##### Hierarchy Schulen nach Trägerschaft:

Tables: "schule,traeger,traeger_art,traeger_kategorie"

Levels: "Schulträger-Kategorie, Schulträger-Art, Schulträger, Schule"

###### Level "Schulträger-Kategorie" :

    column(s): id

###### Level "Schulträger-Art" :

    column(s): id

###### Level "Schulträger" :

    column(s): id

###### Level "Schule" :

    column(s): id

##### Hierarchy Schulen nach Art:

Tables: "schule,schul_art,schul_kategorie"

Levels: "Schulkategorie, Schulart, Schule"

###### Level "Schulkategorie" :

    column(s): id

###### Level "Schulart" :

    column(s): id

###### Level "Schule" :

    column(s): id

##### Dimension "Schuljahr":

Hierarchies:

    Schuljahre

##### Hierarchy Schuljahre:

Tables: "schul_jahr"

Levels: "Schuljahr"

###### Level "Schuljahr" :

    column(s): id

##### Dimension "Altersgruppe":

Hierarchies:

    Altersgruppen

##### Hierarchy Altersgruppen:

Tables: "alters_gruppe"

Levels: "Altersgruppe"

###### Level "Altersgruppe" :

    column(s): id

##### Dimension "Geschlecht":

Hierarchies:

    Geschlecht

##### Hierarchy Geschlecht:

Tables: "geschlecht"

Levels: "Geschlecht"

###### Level "Geschlecht" :

    column(s): id

##### Dimension "Berufsgruppe":

Hierarchies:

    Berufsgruppen

##### Hierarchy Berufsgruppen:

Tables: "personal_art"

Levels: "Berufsgruppe"

###### Level "Berufsgruppe" :

    column(s): id

---
#### Cube "Schüler:innen an Jenaer Schulen":

    

##### Table: "fact_schueler"

##### Dimensions:
##### Dimension "Schulen":

Hierarchies:

    Schulen nach Ganztagsangebot, Schulen nach Trägerschaft, Schulen nach Art

##### Hierarchy Schulen nach Ganztagsangebot:

Tables: "schule,ganztags_art"

Levels: "Art des Ganztagsangebots, Schule"

###### Level "Art des Ganztagsangebots" :

    column(s): id

###### Level "Schule" :

    column(s): id

##### Hierarchy Schulen nach Trägerschaft:

Tables: "schule,traeger,traeger_art,traeger_kategorie"

Levels: "Schulträger-Kategorie, Schulträger-Art, Schulträger, Schule"

###### Level "Schulträger-Kategorie" :

    column(s): id

###### Level "Schulträger-Art" :

    column(s): id

###### Level "Schulträger" :

    column(s): id

###### Level "Schule" :

    column(s): id

##### Hierarchy Schulen nach Art:

Tables: "schule,schul_art,schul_kategorie"

Levels: "Schulkategorie, Schulart, Schule"

###### Level "Schulkategorie" :

    column(s): id

###### Level "Schulart" :

    column(s): id

###### Level "Schule" :

    column(s): id

##### Dimension "Schuljahr":

Hierarchies:

    Schuljahre

##### Hierarchy Schuljahre:

Tables: "schul_jahr"

Levels: "Schuljahr"

###### Level "Schuljahr" :

    column(s): id

##### Dimension "Geschlecht":

Hierarchies:

    Geschlecht

##### Hierarchy Geschlecht:

Tables: "geschlecht"

Levels: "Geschlecht"

###### Level "Geschlecht" :

    column(s): id

##### Dimension "Wohnlandkreis":

Hierarchies:

    Wohnlandkreis

##### Hierarchy Wohnlandkreis:

Tables: "wohnort_landkreis,bundesland"

Levels: "Bundesland, Wohnlandkreis"

###### Level "Bundesland" :

    column(s): id

###### Level "Wohnlandkreis" :

    column(s): id

##### Dimension "Einschulung":

Hierarchies:

    Einschulung

##### Hierarchy Einschulung:

Tables: "einschulung"

Levels: "Einschulung"

###### Level "Einschulung" :

    column(s): id

##### Dimension "Schulabschluss":

Hierarchies:

    Schulabschlüsse

##### Hierarchy Schulabschlüsse:

Tables: "schul_abschluss"

Levels: "Schulabschlüsse"

###### Level "Schulabschlüsse" :

    column(s): id

##### Dimension "Klassenwiederholung":

Hierarchies:

    Klassenwiederholung

##### Hierarchy Klassenwiederholung:

Tables: "klassen_wiederholung"

Levels: "Klassenwiederholung"

###### Level "Klassenwiederholung" :

    column(s): id

##### Dimension "Migrationshintergrund":

Hierarchies:

    Migrationshintergrund

##### Hierarchy Migrationshintergrund:

Tables: "migrations_hintergrund"

Levels: "Migrationshintergrund"

###### Level "Migrationshintergrund" :

    column(s): id

##### Dimension "Sonderpädagogische Förderung":

Hierarchies:

    Sonderpädagogische Förderung

##### Hierarchy Sonderpädagogische Förderung:

Tables: "foerderung_art,sonderpaed_foerderbedarf"

Levels: "Förderbedarf, Art der Förderung"

###### Level "Förderbedarf" :

    column(s): id

###### Level "Art der Förderung" :

    column(s): id

### Cube "Schulen in Jena (Institutionen)" diagram:

---

```mermaid
%%{init: {
"theme": "default",
"themeCSS": [
    ".er.entityBox {stroke: black;}",
    ".er.attributeBoxEven {stroke: black;}",
    ".er.attributeBoxOdd {stroke: black;}",
    "[id^=entity-c] .er.entityBox { fill: lightgreen;} ",
    "[id^=entity-d] .er.entityBox { fill: powderblue;} ",
    "[id^=entity-h] .er.entityBox { fill: pink;} "
]
}}%%
erDiagram
c0["Schulen in Jena (Institutionen)"]{
M Anzahl_Schulen ""
M Anzahl_Klassen ""
D Schulen ""
D Schuljahr ""
}
d00["Schulen"] {
H Schulen_nach_Ganztagsangebot ""
H Schulen_nach_Traegerschaft ""
H Schulen_nach_Art ""
}
h000["Schulen_nach_Ganztagsangebot"] {
L Art_des_Ganztagsangebots ""
L Schule ""
}
h001["Schulen_nach_Traegerschaft"] {
L Schultraeger-Kategorie ""
L Schultraeger-Art ""
L Schultraeger ""
L Schule ""
}
h002["Schulen_nach_Art"] {
L Schulkategorie ""
L Schulart ""
L Schule ""
}
d01["Schuljahr"] {
H Schuljahre ""
}
h010["Schuljahre"] {
L Schuljahr ""
}
"c0" ||--|| "d00" : "schule_id-id"
"d00" ||--|| "h000" : "id-id"
"d00" ||--|| "h000" : "id-id"
"c0" ||--|| "d00" : "schule_id-id"
"d00" ||--|| "h001" : "id-id"
"d00" ||--|| "h001" : "id-id"
"d00" ||--|| "h001" : "id-id"
"d00" ||--|| "h001" : "id-id"
"c0" ||--|| "d00" : "schule_id-id"
"d00" ||--|| "h002" : "id-id"
"d00" ||--|| "h002" : "id-id"
"d00" ||--|| "h002" : "id-id"
"c0" ||--|| "d01" : "schul_jahr_id-id"
"d01" ||--|| "h010" : "id-id"
```
---
### Database :
---
```mermaid
---
title: Diagram;
---
erDiagram
"alters_gruppe✔"{
int id "is null (32.0) ✔"
string altersgruppe "is null (1000000000.0) ✔"
}
"bundesland✔"{
int id "is null (32.0) ✔"
string kuerzel "is null (1000000000.0) ✔"
string bezeichnung "is null (1000000000.0) ✔"
}
"einschulung✔"{
int id "is null (32.0) ✔"
string einschulung "is null (1000000000.0) ✔"
}
"fact_personal✔"{
int schule_id "is null (32.0) ✔"
int schul_jahr_id "is null (32.0) ✔"
int alters_gruppe_id "is null (32.0) ✔"
int geschlecht_id "is null (32.0) ✔"
int personal_art_id "is null (32.0) ✔"
int anzahl_personen "is null (32.0) ✔"
}
"fact_schueler✔"{
int schule_id "is null (32.0) ✔"
int schul_jahr_id "is null (32.0) ✔"
int geschlecht_id "is null (32.0) ✔"
int wohn_lk_id "is null (32.0) ✔"
int einschulung_id "is null (32.0) ✔"
int schul_abschluss_id "is null (32.0) ✔"
int klassen_wdh "is null (32.0) ✔"
int migrations_hg_id "is null (32.0) ✔"
int foerder_art_id "is null (32.0) ✔"
int anzahl_schueler "is null (32.0) ✔"
}
"fact_schulen✔"{
int schule_id "is null (32.0) ✔"
int schul_jahr_id "is null (32.0) ✔"
int anzahl_schulen "is null (32.0) ✔"
int anzahl_klassen "is null (32.0) ✔"
}
"foerderung_art✔"{
int id "is null (32.0) ✔"
string foerderung_art "is null (1000000000.0) ✔"
int sp_foerderbedarf_id "is null (32.0) ✔"
}
"ganztags_art✔"{
int id "is null (32.0) ✔"
string schul_umfang "is null (1000000000.0) ✔"
}
"geschlecht✔"{
int id "is null (32.0) ✔"
string kuerzel "is null (1000000000.0) ✔"
string bezeichnung "is null (1000000000.0) ✔"
}
"klassen_wiederholung✔"{
int id "is null (32.0) ✔"
string klassenwiederholung "is null (1000000000.0) ✔"
}
"migrations_hintergrund✔"{
int id "is null (32.0) ✔"
string migrations_hintergrund "is null (1000000000.0) ✔"
}
"personal_art✔"{
int id "is null (32.0) ✔"
string bezeichnung "is null (1000000000.0) ✔"
}
"schul_abschluss✔"{
int id "is null (32.0) ✔"
string schulabschluss "is null (1000000000.0) ✔"
}
"schul_art✔"{
int id "is null (32.0) ✔"
string schulart_name "is null (1000000000.0) ✔"
int schul_kategorie_id "is null (32.0) ✔"
}
"schul_jahr✔"{
int id "is null (32.0) ✔"
string schul_jahr "is null (1000000000.0) ✔"
int order "is null (32.0) ✔"
}
"schul_kategorie✔"{
int id "is null (32.0) ✔"
string schul_kategorie_name "is null (1000000000.0) ✔"
}
"schule✔"{
int id "is null (32.0) ✔"
int schul_nummer "is null (32.0) ✔"
string schul_name "is null (1000000000.0) ✔"
int traeger_id "is null (32.0) ✔"
int schul_art_id "is null (32.0) ✔"
int ganztags_art_id "is null (32.0) ✔"
}
"sonderpaed_foerderbedarf✔"{
int id "is null (32.0) ✔"
string sonderpaed_bedarf "is null (1000000000.0) ✔"
}
"traeger✔"{
int id "is null (32.0) ✔"
string traeger_name "is null (1000000000.0) ✔"
int traeger_art_id "is null (32.0) ✔"
}
"traeger_art✔"{
int id "is null (32.0) ✔"
string traeger_art "is null (1000000000.0) ✔"
string traeger_kat_id "is null (1000000000.0) ✔"
}
"traeger_kategorie✔"{
int id "is null (32.0) ✔"
string traeger_kategorie "is null (1000000000.0) ✔"
}
"wohnort_landkreis✔"{
int id "is null (32.0) ✔"
string kuerzel "is null (1000000000.0) ✔"
string bezeichnung "is null (1000000000.0) ✔"
int bundesland_id "is null (32.0) ✔"
}

"fact_schulen✔" ||--o{ "schule✔" : "schule_id-id"
"schule✔" ||--o{ "ganztags_art✔" : "ganztags_art_id-id"
"fact_schulen✔" ||--o{ "schule✔" : "schule_id-id"
"schule✔" ||--o{ "traeger✔" : "traeger_id-id"
"traeger✔" ||--o{ "traeger_art✔" : "traeger_art_id-id"
"traeger_art✔" ||--o{ "traeger_kategorie✔" : "traeger_kat_id-id"
"fact_schulen✔" ||--o{ "schule✔" : "schule_id-id"
"schule✔" ||--o{ "schul_art✔" : "schul_art_id-id"
"schul_art✔" ||--o{ "schul_kategorie✔" : "schul_kategorie_id-id"
"fact_schulen✔" ||--o{ "schul_jahr✔" : "schul_jahr_id-id"
"fact_personal✔" ||--o{ "schule✔" : "schule_id-id"
"schule✔" ||--o{ "ganztags_art✔" : "ganztags_art_id-id"
"fact_personal✔" ||--o{ "schule✔" : "schule_id-id"
"schule✔" ||--o{ "traeger✔" : "traeger_id-id"
"traeger✔" ||--o{ "traeger_art✔" : "traeger_art_id-id"
"traeger_art✔" ||--o{ "traeger_kategorie✔" : "traeger_kat_id-id"
"fact_personal✔" ||--o{ "schule✔" : "schule_id-id"
"schule✔" ||--o{ "schul_art✔" : "schul_art_id-id"
"schul_art✔" ||--o{ "schul_kategorie✔" : "schul_kategorie_id-id"
"fact_personal✔" ||--o{ "schul_jahr✔" : "schul_jahr_id-id"
"fact_personal✔" ||--o{ "alters_gruppe✔" : "alters_gruppe_id-id"
"fact_personal✔" ||--o{ "geschlecht✔" : "geschlecht_id-id"
"fact_personal✔" ||--o{ "personal_art✔" : "personal_art_id-id"
"fact_schueler✔" ||--o{ "schule✔" : "schule_id-id"
"schule✔" ||--o{ "ganztags_art✔" : "ganztags_art_id-id"
"fact_schueler✔" ||--o{ "schule✔" : "schule_id-id"
"schule✔" ||--o{ "traeger✔" : "traeger_id-id"
"traeger✔" ||--o{ "traeger_art✔" : "traeger_art_id-id"
"traeger_art✔" ||--o{ "traeger_kategorie✔" : "traeger_kat_id-id"
"fact_schueler✔" ||--o{ "schule✔" : "schule_id-id"
"schule✔" ||--o{ "schul_art✔" : "schul_art_id-id"
"schul_art✔" ||--o{ "schul_kategorie✔" : "schul_kategorie_id-id"
"fact_schueler✔" ||--o{ "schul_jahr✔" : "schul_jahr_id-id"
"fact_schueler✔" ||--o{ "geschlecht✔" : "geschlecht_id-id"
"fact_schueler✔" ||--o{ "wohnort_landkreis✔" : "wohn_lk_id-id"
"wohnort_landkreis✔" ||--o{ "bundesland✔" : "bundesland_id-id"
"fact_schueler✔" ||--o{ "einschulung✔" : "einschulung_id-id"
"fact_schueler✔" ||--o{ "schul_abschluss✔" : "schul_abschluss_id-id"
"fact_schueler✔" ||--o{ "klassen_wiederholung✔" : "klassen_wdh-id"
"fact_schueler✔" ||--o{ "migrations_hintergrund✔" : "migrations_hg_id-id"
"fact_schueler✔" ||--o{ "foerderung_art✔" : "foerder_art_id-id"
"foerderung_art✔" ||--o{ "sonderpaed_foerderbedarf✔" : "sp_foerderbedarf_id-id"
```
---
" Aggregation section:

---
```mermaid
   erDiagram
"fact_schulen✔"{
int schule_id "is null (32.0) ✔"
int schul_jahr_id "is null (32.0) ✔"
int anzahl_schulen "is null (32.0) ✔"
int anzahl_klassen "is null (32.0) ✔"
}
```
---
### Cube "Pädagogisches Personal an Jenaer Schulen" diagram:

---

```mermaid
%%{init: {
"theme": "default",
"themeCSS": [
    ".er.entityBox {stroke: black;}",
    ".er.attributeBoxEven {stroke: black;}",
    ".er.attributeBoxOdd {stroke: black;}",
    "[id^=entity-c] .er.entityBox { fill: lightgreen;} ",
    "[id^=entity-d] .er.entityBox { fill: powderblue;} ",
    "[id^=entity-h] .er.entityBox { fill: pink;} "
]
}}%%
erDiagram
c1["Pädagogisches Personal an Jenaer Schulen"]{
M Anzahl_Personen ""
D Schulen ""
D Schuljahr ""
D Altersgruppe ""
D Geschlecht ""
D Berufsgruppe ""
}
d10["Schulen"] {
H Schulen_nach_Ganztagsangebot ""
H Schulen_nach_Traegerschaft ""
H Schulen_nach_Art ""
}
h100["Schulen_nach_Ganztagsangebot"] {
L Art_des_Ganztagsangebots ""
L Schule ""
}
h101["Schulen_nach_Traegerschaft"] {
L Schultraeger-Kategorie ""
L Schultraeger-Art ""
L Schultraeger ""
L Schule ""
}
h102["Schulen_nach_Art"] {
L Schulkategorie ""
L Schulart ""
L Schule ""
}
d11["Schuljahr"] {
H Schuljahre ""
}
h110["Schuljahre"] {
L Schuljahr ""
}
d12["Altersgruppe"] {
H Altersgruppen ""
}
h120["Altersgruppen"] {
L Altersgruppe ""
}
d13["Geschlecht"] {
H Geschlecht ""
}
h130["Geschlecht"] {
L Geschlecht ""
}
d14["Berufsgruppe"] {
H Berufsgruppen ""
}
h140["Berufsgruppen"] {
L Berufsgruppe ""
}
"c1" ||--|| "d10" : "schule_id-id"
"d10" ||--|| "h100" : "id-id"
"d10" ||--|| "h100" : "id-id"
"c1" ||--|| "d10" : "schule_id-id"
"d10" ||--|| "h101" : "id-id"
"d10" ||--|| "h101" : "id-id"
"d10" ||--|| "h101" : "id-id"
"d10" ||--|| "h101" : "id-id"
"c1" ||--|| "d10" : "schule_id-id"
"d10" ||--|| "h102" : "id-id"
"d10" ||--|| "h102" : "id-id"
"d10" ||--|| "h102" : "id-id"
"c1" ||--|| "d11" : "schul_jahr_id-id"
"d11" ||--|| "h110" : "id-id"
"c1" ||--|| "d12" : "alters_gruppe_id-id"
"d12" ||--|| "h120" : "id-id"
"c1" ||--|| "d13" : "geschlecht_id-id"
"d13" ||--|| "h130" : "id-id"
"c1" ||--|| "d14" : "personal_art_id-id"
"d14" ||--|| "h140" : "id-id"
```
---
### Database :
---
```mermaid
---
title: Diagram;
---
erDiagram
"alters_gruppe✔"{
int id "is null (32.0) ✔"
string altersgruppe "is null (1000000000.0) ✔"
}
"bundesland✔"{
int id "is null (32.0) ✔"
string kuerzel "is null (1000000000.0) ✔"
string bezeichnung "is null (1000000000.0) ✔"
}
"einschulung✔"{
int id "is null (32.0) ✔"
string einschulung "is null (1000000000.0) ✔"
}
"fact_personal✔"{
int schule_id "is null (32.0) ✔"
int schul_jahr_id "is null (32.0) ✔"
int alters_gruppe_id "is null (32.0) ✔"
int geschlecht_id "is null (32.0) ✔"
int personal_art_id "is null (32.0) ✔"
int anzahl_personen "is null (32.0) ✔"
}
"fact_schueler✔"{
int schule_id "is null (32.0) ✔"
int schul_jahr_id "is null (32.0) ✔"
int geschlecht_id "is null (32.0) ✔"
int wohn_lk_id "is null (32.0) ✔"
int einschulung_id "is null (32.0) ✔"
int schul_abschluss_id "is null (32.0) ✔"
int klassen_wdh "is null (32.0) ✔"
int migrations_hg_id "is null (32.0) ✔"
int foerder_art_id "is null (32.0) ✔"
int anzahl_schueler "is null (32.0) ✔"
}
"fact_schulen✔"{
int schule_id "is null (32.0) ✔"
int schul_jahr_id "is null (32.0) ✔"
int anzahl_schulen "is null (32.0) ✔"
int anzahl_klassen "is null (32.0) ✔"
}
"foerderung_art✔"{
int id "is null (32.0) ✔"
string foerderung_art "is null (1000000000.0) ✔"
int sp_foerderbedarf_id "is null (32.0) ✔"
}
"ganztags_art✔"{
int id "is null (32.0) ✔"
string schul_umfang "is null (1000000000.0) ✔"
}
"geschlecht✔"{
int id "is null (32.0) ✔"
string kuerzel "is null (1000000000.0) ✔"
string bezeichnung "is null (1000000000.0) ✔"
}
"klassen_wiederholung✔"{
int id "is null (32.0) ✔"
string klassenwiederholung "is null (1000000000.0) ✔"
}
"migrations_hintergrund✔"{
int id "is null (32.0) ✔"
string migrations_hintergrund "is null (1000000000.0) ✔"
}
"personal_art✔"{
int id "is null (32.0) ✔"
string bezeichnung "is null (1000000000.0) ✔"
}
"schul_abschluss✔"{
int id "is null (32.0) ✔"
string schulabschluss "is null (1000000000.0) ✔"
}
"schul_art✔"{
int id "is null (32.0) ✔"
string schulart_name "is null (1000000000.0) ✔"
int schul_kategorie_id "is null (32.0) ✔"
}
"schul_jahr✔"{
int id "is null (32.0) ✔"
string schul_jahr "is null (1000000000.0) ✔"
int order "is null (32.0) ✔"
}
"schul_kategorie✔"{
int id "is null (32.0) ✔"
string schul_kategorie_name "is null (1000000000.0) ✔"
}
"schule✔"{
int id "is null (32.0) ✔"
int schul_nummer "is null (32.0) ✔"
string schul_name "is null (1000000000.0) ✔"
int traeger_id "is null (32.0) ✔"
int schul_art_id "is null (32.0) ✔"
int ganztags_art_id "is null (32.0) ✔"
}
"sonderpaed_foerderbedarf✔"{
int id "is null (32.0) ✔"
string sonderpaed_bedarf "is null (1000000000.0) ✔"
}
"traeger✔"{
int id "is null (32.0) ✔"
string traeger_name "is null (1000000000.0) ✔"
int traeger_art_id "is null (32.0) ✔"
}
"traeger_art✔"{
int id "is null (32.0) ✔"
string traeger_art "is null (1000000000.0) ✔"
string traeger_kat_id "is null (1000000000.0) ✔"
}
"traeger_kategorie✔"{
int id "is null (32.0) ✔"
string traeger_kategorie "is null (1000000000.0) ✔"
}
"wohnort_landkreis✔"{
int id "is null (32.0) ✔"
string kuerzel "is null (1000000000.0) ✔"
string bezeichnung "is null (1000000000.0) ✔"
int bundesland_id "is null (32.0) ✔"
}

"fact_schulen✔" ||--o{ "schule✔" : "schule_id-id"
"schule✔" ||--o{ "ganztags_art✔" : "ganztags_art_id-id"
"fact_schulen✔" ||--o{ "schule✔" : "schule_id-id"
"schule✔" ||--o{ "traeger✔" : "traeger_id-id"
"traeger✔" ||--o{ "traeger_art✔" : "traeger_art_id-id"
"traeger_art✔" ||--o{ "traeger_kategorie✔" : "traeger_kat_id-id"
"fact_schulen✔" ||--o{ "schule✔" : "schule_id-id"
"schule✔" ||--o{ "schul_art✔" : "schul_art_id-id"
"schul_art✔" ||--o{ "schul_kategorie✔" : "schul_kategorie_id-id"
"fact_schulen✔" ||--o{ "schul_jahr✔" : "schul_jahr_id-id"
"fact_personal✔" ||--o{ "schule✔" : "schule_id-id"
"schule✔" ||--o{ "ganztags_art✔" : "ganztags_art_id-id"
"fact_personal✔" ||--o{ "schule✔" : "schule_id-id"
"schule✔" ||--o{ "traeger✔" : "traeger_id-id"
"traeger✔" ||--o{ "traeger_art✔" : "traeger_art_id-id"
"traeger_art✔" ||--o{ "traeger_kategorie✔" : "traeger_kat_id-id"
"fact_personal✔" ||--o{ "schule✔" : "schule_id-id"
"schule✔" ||--o{ "schul_art✔" : "schul_art_id-id"
"schul_art✔" ||--o{ "schul_kategorie✔" : "schul_kategorie_id-id"
"fact_personal✔" ||--o{ "schul_jahr✔" : "schul_jahr_id-id"
"fact_personal✔" ||--o{ "alters_gruppe✔" : "alters_gruppe_id-id"
"fact_personal✔" ||--o{ "geschlecht✔" : "geschlecht_id-id"
"fact_personal✔" ||--o{ "personal_art✔" : "personal_art_id-id"
"fact_schueler✔" ||--o{ "schule✔" : "schule_id-id"
"schule✔" ||--o{ "ganztags_art✔" : "ganztags_art_id-id"
"fact_schueler✔" ||--o{ "schule✔" : "schule_id-id"
"schule✔" ||--o{ "traeger✔" : "traeger_id-id"
"traeger✔" ||--o{ "traeger_art✔" : "traeger_art_id-id"
"traeger_art✔" ||--o{ "traeger_kategorie✔" : "traeger_kat_id-id"
"fact_schueler✔" ||--o{ "schule✔" : "schule_id-id"
"schule✔" ||--o{ "schul_art✔" : "schul_art_id-id"
"schul_art✔" ||--o{ "schul_kategorie✔" : "schul_kategorie_id-id"
"fact_schueler✔" ||--o{ "schul_jahr✔" : "schul_jahr_id-id"
"fact_schueler✔" ||--o{ "geschlecht✔" : "geschlecht_id-id"
"fact_schueler✔" ||--o{ "wohnort_landkreis✔" : "wohn_lk_id-id"
"wohnort_landkreis✔" ||--o{ "bundesland✔" : "bundesland_id-id"
"fact_schueler✔" ||--o{ "einschulung✔" : "einschulung_id-id"
"fact_schueler✔" ||--o{ "schul_abschluss✔" : "schul_abschluss_id-id"
"fact_schueler✔" ||--o{ "klassen_wiederholung✔" : "klassen_wdh-id"
"fact_schueler✔" ||--o{ "migrations_hintergrund✔" : "migrations_hg_id-id"
"fact_schueler✔" ||--o{ "foerderung_art✔" : "foerder_art_id-id"
"foerderung_art✔" ||--o{ "sonderpaed_foerderbedarf✔" : "sp_foerderbedarf_id-id"
```
---
" Aggregation section:

---
```mermaid
   erDiagram
"fact_personal✔"{
int schule_id "is null (32.0) ✔"
int schul_jahr_id "is null (32.0) ✔"
int alters_gruppe_id "is null (32.0) ✔"
int geschlecht_id "is null (32.0) ✔"
int personal_art_id "is null (32.0) ✔"
int anzahl_personen "is null (32.0) ✔"
}
```
---
### Cube "Schüler:innen an Jenaer Schulen" diagram:

---

```mermaid
%%{init: {
"theme": "default",
"themeCSS": [
    ".er.entityBox {stroke: black;}",
    ".er.attributeBoxEven {stroke: black;}",
    ".er.attributeBoxOdd {stroke: black;}",
    "[id^=entity-c] .er.entityBox { fill: lightgreen;} ",
    "[id^=entity-d] .er.entityBox { fill: powderblue;} ",
    "[id^=entity-h] .er.entityBox { fill: pink;} "
]
}}%%
erDiagram
c2["Schüler:innen an Jenaer Schulen"]{
M Anzahl_Schueler_innen ""
D Schulen ""
D Schuljahr ""
D Geschlecht ""
D Wohnlandkreis ""
D Einschulung ""
D Schulabschluss ""
D Klassenwiederholung ""
D Migrationshintergrund ""
D Sonderpaedagogische_Foerderung ""
}
d20["Schulen"] {
H Schulen_nach_Ganztagsangebot ""
H Schulen_nach_Traegerschaft ""
H Schulen_nach_Art ""
}
h200["Schulen_nach_Ganztagsangebot"] {
L Art_des_Ganztagsangebots ""
L Schule ""
}
h201["Schulen_nach_Traegerschaft"] {
L Schultraeger-Kategorie ""
L Schultraeger-Art ""
L Schultraeger ""
L Schule ""
}
h202["Schulen_nach_Art"] {
L Schulkategorie ""
L Schulart ""
L Schule ""
}
d21["Schuljahr"] {
H Schuljahre ""
}
h210["Schuljahre"] {
L Schuljahr ""
}
d22["Geschlecht"] {
H Geschlecht ""
}
h220["Geschlecht"] {
L Geschlecht ""
}
d23["Wohnlandkreis"] {
H Wohnlandkreis ""
}
h230["Wohnlandkreis"] {
L Bundesland ""
L Wohnlandkreis ""
}
d24["Einschulung"] {
H Einschulung ""
}
h240["Einschulung"] {
L Einschulung ""
}
d25["Schulabschluss"] {
H Schulabschluesse ""
}
h250["Schulabschluesse"] {
L Schulabschluesse ""
}
d26["Klassenwiederholung"] {
H Klassenwiederholung ""
}
h260["Klassenwiederholung"] {
L Klassenwiederholung ""
}
d27["Migrationshintergrund"] {
H Migrationshintergrund ""
}
h270["Migrationshintergrund"] {
L Migrationshintergrund ""
}
d28["Sonderpädagogische Förderung"] {
H Sonderpaedagogische_Foerderung ""
}
h280["Sonderpaedagogische_Foerderung"] {
L Foerderbedarf ""
L Art_der_Foerderung ""
}
"c2" ||--|| "d20" : "schule_id-id"
"d20" ||--|| "h200" : "id-id"
"d20" ||--|| "h200" : "id-id"
"c2" ||--|| "d20" : "schule_id-id"
"d20" ||--|| "h201" : "id-id"
"d20" ||--|| "h201" : "id-id"
"d20" ||--|| "h201" : "id-id"
"d20" ||--|| "h201" : "id-id"
"c2" ||--|| "d20" : "schule_id-id"
"d20" ||--|| "h202" : "id-id"
"d20" ||--|| "h202" : "id-id"
"d20" ||--|| "h202" : "id-id"
"c2" ||--|| "d21" : "schul_jahr_id-id"
"d21" ||--|| "h210" : "id-id"
"c2" ||--|| "d22" : "geschlecht_id-id"
"d22" ||--|| "h220" : "id-id"
"c2" ||--|| "d23" : "wohn_lk_id-id"
"d23" ||--|| "h230" : "id-id"
"d23" ||--|| "h230" : "id-id"
"c2" ||--|| "d24" : "einschulung_id-id"
"d24" ||--|| "h240" : "id-id"
"c2" ||--|| "d25" : "schul_abschluss_id-id"
"d25" ||--|| "h250" : "id-id"
"c2" ||--|| "d26" : "klassen_wdh-id"
"d26" ||--|| "h260" : "id-id"
"c2" ||--|| "d27" : "migrations_hg_id-id"
"d27" ||--|| "h270" : "id-id"
"c2" ||--|| "d28" : "foerder_art_id-id"
"d28" ||--|| "h280" : "id-id"
"d28" ||--|| "h280" : "id-id"
```
---
### Database :
---
```mermaid
---
title: Diagram;
---
erDiagram
"alters_gruppe✔"{
int id "is null (32.0) ✔"
string altersgruppe "is null (1000000000.0) ✔"
}
"bundesland✔"{
int id "is null (32.0) ✔"
string kuerzel "is null (1000000000.0) ✔"
string bezeichnung "is null (1000000000.0) ✔"
}
"einschulung✔"{
int id "is null (32.0) ✔"
string einschulung "is null (1000000000.0) ✔"
}
"fact_personal✔"{
int schule_id "is null (32.0) ✔"
int schul_jahr_id "is null (32.0) ✔"
int alters_gruppe_id "is null (32.0) ✔"
int geschlecht_id "is null (32.0) ✔"
int personal_art_id "is null (32.0) ✔"
int anzahl_personen "is null (32.0) ✔"
}
"fact_schueler✔"{
int schule_id "is null (32.0) ✔"
int schul_jahr_id "is null (32.0) ✔"
int geschlecht_id "is null (32.0) ✔"
int wohn_lk_id "is null (32.0) ✔"
int einschulung_id "is null (32.0) ✔"
int schul_abschluss_id "is null (32.0) ✔"
int klassen_wdh "is null (32.0) ✔"
int migrations_hg_id "is null (32.0) ✔"
int foerder_art_id "is null (32.0) ✔"
int anzahl_schueler "is null (32.0) ✔"
}
"fact_schulen✔"{
int schule_id "is null (32.0) ✔"
int schul_jahr_id "is null (32.0) ✔"
int anzahl_schulen "is null (32.0) ✔"
int anzahl_klassen "is null (32.0) ✔"
}
"foerderung_art✔"{
int id "is null (32.0) ✔"
string foerderung_art "is null (1000000000.0) ✔"
int sp_foerderbedarf_id "is null (32.0) ✔"
}
"ganztags_art✔"{
int id "is null (32.0) ✔"
string schul_umfang "is null (1000000000.0) ✔"
}
"geschlecht✔"{
int id "is null (32.0) ✔"
string kuerzel "is null (1000000000.0) ✔"
string bezeichnung "is null (1000000000.0) ✔"
}
"klassen_wiederholung✔"{
int id "is null (32.0) ✔"
string klassenwiederholung "is null (1000000000.0) ✔"
}
"migrations_hintergrund✔"{
int id "is null (32.0) ✔"
string migrations_hintergrund "is null (1000000000.0) ✔"
}
"personal_art✔"{
int id "is null (32.0) ✔"
string bezeichnung "is null (1000000000.0) ✔"
}
"schul_abschluss✔"{
int id "is null (32.0) ✔"
string schulabschluss "is null (1000000000.0) ✔"
}
"schul_art✔"{
int id "is null (32.0) ✔"
string schulart_name "is null (1000000000.0) ✔"
int schul_kategorie_id "is null (32.0) ✔"
}
"schul_jahr✔"{
int id "is null (32.0) ✔"
string schul_jahr "is null (1000000000.0) ✔"
int order "is null (32.0) ✔"
}
"schul_kategorie✔"{
int id "is null (32.0) ✔"
string schul_kategorie_name "is null (1000000000.0) ✔"
}
"schule✔"{
int id "is null (32.0) ✔"
int schul_nummer "is null (32.0) ✔"
string schul_name "is null (1000000000.0) ✔"
int traeger_id "is null (32.0) ✔"
int schul_art_id "is null (32.0) ✔"
int ganztags_art_id "is null (32.0) ✔"
}
"sonderpaed_foerderbedarf✔"{
int id "is null (32.0) ✔"
string sonderpaed_bedarf "is null (1000000000.0) ✔"
}
"traeger✔"{
int id "is null (32.0) ✔"
string traeger_name "is null (1000000000.0) ✔"
int traeger_art_id "is null (32.0) ✔"
}
"traeger_art✔"{
int id "is null (32.0) ✔"
string traeger_art "is null (1000000000.0) ✔"
string traeger_kat_id "is null (1000000000.0) ✔"
}
"traeger_kategorie✔"{
int id "is null (32.0) ✔"
string traeger_kategorie "is null (1000000000.0) ✔"
}
"wohnort_landkreis✔"{
int id "is null (32.0) ✔"
string kuerzel "is null (1000000000.0) ✔"
string bezeichnung "is null (1000000000.0) ✔"
int bundesland_id "is null (32.0) ✔"
}

"fact_schulen✔" ||--o{ "schule✔" : "schule_id-id"
"schule✔" ||--o{ "ganztags_art✔" : "ganztags_art_id-id"
"fact_schulen✔" ||--o{ "schule✔" : "schule_id-id"
"schule✔" ||--o{ "traeger✔" : "traeger_id-id"
"traeger✔" ||--o{ "traeger_art✔" : "traeger_art_id-id"
"traeger_art✔" ||--o{ "traeger_kategorie✔" : "traeger_kat_id-id"
"fact_schulen✔" ||--o{ "schule✔" : "schule_id-id"
"schule✔" ||--o{ "schul_art✔" : "schul_art_id-id"
"schul_art✔" ||--o{ "schul_kategorie✔" : "schul_kategorie_id-id"
"fact_schulen✔" ||--o{ "schul_jahr✔" : "schul_jahr_id-id"
"fact_personal✔" ||--o{ "schule✔" : "schule_id-id"
"schule✔" ||--o{ "ganztags_art✔" : "ganztags_art_id-id"
"fact_personal✔" ||--o{ "schule✔" : "schule_id-id"
"schule✔" ||--o{ "traeger✔" : "traeger_id-id"
"traeger✔" ||--o{ "traeger_art✔" : "traeger_art_id-id"
"traeger_art✔" ||--o{ "traeger_kategorie✔" : "traeger_kat_id-id"
"fact_personal✔" ||--o{ "schule✔" : "schule_id-id"
"schule✔" ||--o{ "schul_art✔" : "schul_art_id-id"
"schul_art✔" ||--o{ "schul_kategorie✔" : "schul_kategorie_id-id"
"fact_personal✔" ||--o{ "schul_jahr✔" : "schul_jahr_id-id"
"fact_personal✔" ||--o{ "alters_gruppe✔" : "alters_gruppe_id-id"
"fact_personal✔" ||--o{ "geschlecht✔" : "geschlecht_id-id"
"fact_personal✔" ||--o{ "personal_art✔" : "personal_art_id-id"
"fact_schueler✔" ||--o{ "schule✔" : "schule_id-id"
"schule✔" ||--o{ "ganztags_art✔" : "ganztags_art_id-id"
"fact_schueler✔" ||--o{ "schule✔" : "schule_id-id"
"schule✔" ||--o{ "traeger✔" : "traeger_id-id"
"traeger✔" ||--o{ "traeger_art✔" : "traeger_art_id-id"
"traeger_art✔" ||--o{ "traeger_kategorie✔" : "traeger_kat_id-id"
"fact_schueler✔" ||--o{ "schule✔" : "schule_id-id"
"schule✔" ||--o{ "schul_art✔" : "schul_art_id-id"
"schul_art✔" ||--o{ "schul_kategorie✔" : "schul_kategorie_id-id"
"fact_schueler✔" ||--o{ "schul_jahr✔" : "schul_jahr_id-id"
"fact_schueler✔" ||--o{ "geschlecht✔" : "geschlecht_id-id"
"fact_schueler✔" ||--o{ "wohnort_landkreis✔" : "wohn_lk_id-id"
"wohnort_landkreis✔" ||--o{ "bundesland✔" : "bundesland_id-id"
"fact_schueler✔" ||--o{ "einschulung✔" : "einschulung_id-id"
"fact_schueler✔" ||--o{ "schul_abschluss✔" : "schul_abschluss_id-id"
"fact_schueler✔" ||--o{ "klassen_wiederholung✔" : "klassen_wdh-id"
"fact_schueler✔" ||--o{ "migrations_hintergrund✔" : "migrations_hg_id-id"
"fact_schueler✔" ||--o{ "foerderung_art✔" : "foerder_art_id-id"
"foerderung_art✔" ||--o{ "sonderpaed_foerderbedarf✔" : "sp_foerderbedarf_id-id"
```
---
" Aggregation section:

---
```mermaid
   erDiagram
"fact_schueler✔"{
int schule_id "is null (32.0) ✔"
int schul_jahr_id "is null (32.0) ✔"
int geschlecht_id "is null (32.0) ✔"
int wohn_lk_id "is null (32.0) ✔"
int einschulung_id "is null (32.0) ✔"
int schul_abschluss_id "is null (32.0) ✔"
int klassen_wdh "is null (32.0) ✔"
int migrations_hg_id "is null (32.0) ✔"
int foerder_art_id "is null (32.0) ✔"
int anzahl_schueler "is null (32.0) ✔"
}
```
---
### Cube Matrix for Schulwesen:
```mermaid
quadrantChart
title Cube Matrix
x-axis small level number --> high level number
y-axis Low row count --> High row count
quadrant-1 Complex
quadrant-2 Deep
quadrant-3 Simple
quadrant-4 Wide

Cube Schulen_in_Jena__Institutionen_: [0.5000, 0.0001]
Cube Paedagogisches_Personal_an_Jenaer_Schulen: [0.6500, 0.0001]
Cube Schueler_innen_an_Jenaer_Schulen: [0.9500, 0.0001]
```
---
### Database :
---
```mermaid
---
title: Diagram;
---
erDiagram
"alters_gruppe✔"{
int id "is null (32.0) ✔"
string altersgruppe "is null (1000000000.0) ✔"
}
"bundesland✔"{
int id "is null (32.0) ✔"
string kuerzel "is null (1000000000.0) ✔"
string bezeichnung "is null (1000000000.0) ✔"
}
"einschulung✔"{
int id "is null (32.0) ✔"
string einschulung "is null (1000000000.0) ✔"
}
"fact_personal✔"{
int schule_id "is null (32.0) ✔"
int schul_jahr_id "is null (32.0) ✔"
int alters_gruppe_id "is null (32.0) ✔"
int geschlecht_id "is null (32.0) ✔"
int personal_art_id "is null (32.0) ✔"
int anzahl_personen "is null (32.0) ✔"
}
"fact_schueler✔"{
int schule_id "is null (32.0) ✔"
int schul_jahr_id "is null (32.0) ✔"
int geschlecht_id "is null (32.0) ✔"
int wohn_lk_id "is null (32.0) ✔"
int einschulung_id "is null (32.0) ✔"
int schul_abschluss_id "is null (32.0) ✔"
int klassen_wdh "is null (32.0) ✔"
int migrations_hg_id "is null (32.0) ✔"
int foerder_art_id "is null (32.0) ✔"
int anzahl_schueler "is null (32.0) ✔"
}
"fact_schulen✔"{
int schule_id "is null (32.0) ✔"
int schul_jahr_id "is null (32.0) ✔"
int anzahl_schulen "is null (32.0) ✔"
int anzahl_klassen "is null (32.0) ✔"
}
"foerderung_art✔"{
int id "is null (32.0) ✔"
string foerderung_art "is null (1000000000.0) ✔"
int sp_foerderbedarf_id "is null (32.0) ✔"
}
"ganztags_art✔"{
int id "is null (32.0) ✔"
string schul_umfang "is null (1000000000.0) ✔"
}
"geschlecht✔"{
int id "is null (32.0) ✔"
string kuerzel "is null (1000000000.0) ✔"
string bezeichnung "is null (1000000000.0) ✔"
}
"klassen_wiederholung✔"{
int id "is null (32.0) ✔"
string klassenwiederholung "is null (1000000000.0) ✔"
}
"migrations_hintergrund✔"{
int id "is null (32.0) ✔"
string migrations_hintergrund "is null (1000000000.0) ✔"
}
"personal_art✔"{
int id "is null (32.0) ✔"
string bezeichnung "is null (1000000000.0) ✔"
}
"schul_abschluss✔"{
int id "is null (32.0) ✔"
string schulabschluss "is null (1000000000.0) ✔"
}
"schul_art✔"{
int id "is null (32.0) ✔"
string schulart_name "is null (1000000000.0) ✔"
int schul_kategorie_id "is null (32.0) ✔"
}
"schul_jahr✔"{
int id "is null (32.0) ✔"
string schul_jahr "is null (1000000000.0) ✔"
int order "is null (32.0) ✔"
}
"schul_kategorie✔"{
int id "is null (32.0) ✔"
string schul_kategorie_name "is null (1000000000.0) ✔"
}
"schule✔"{
int id "is null (32.0) ✔"
int schul_nummer "is null (32.0) ✔"
string schul_name "is null (1000000000.0) ✔"
int traeger_id "is null (32.0) ✔"
int schul_art_id "is null (32.0) ✔"
int ganztags_art_id "is null (32.0) ✔"
}
"sonderpaed_foerderbedarf✔"{
int id "is null (32.0) ✔"
string sonderpaed_bedarf "is null (1000000000.0) ✔"
}
"traeger✔"{
int id "is null (32.0) ✔"
string traeger_name "is null (1000000000.0) ✔"
int traeger_art_id "is null (32.0) ✔"
}
"traeger_art✔"{
int id "is null (32.0) ✔"
string traeger_art "is null (1000000000.0) ✔"
string traeger_kat_id "is null (1000000000.0) ✔"
}
"traeger_kategorie✔"{
int id "is null (32.0) ✔"
string traeger_kategorie "is null (1000000000.0) ✔"
}
"wohnort_landkreis✔"{
int id "is null (32.0) ✔"
string kuerzel "is null (1000000000.0) ✔"
string bezeichnung "is null (1000000000.0) ✔"
int bundesland_id "is null (32.0) ✔"
}

"fact_schulen✔" ||--o{ "schule✔" : "schule_id-id"
"schule✔" ||--o{ "ganztags_art✔" : "ganztags_art_id-id"
"fact_schulen✔" ||--o{ "schule✔" : "schule_id-id"
"schule✔" ||--o{ "traeger✔" : "traeger_id-id"
"traeger✔" ||--o{ "traeger_art✔" : "traeger_art_id-id"
"traeger_art✔" ||--o{ "traeger_kategorie✔" : "traeger_kat_id-id"
"fact_schulen✔" ||--o{ "schule✔" : "schule_id-id"
"schule✔" ||--o{ "schul_art✔" : "schul_art_id-id"
"schul_art✔" ||--o{ "schul_kategorie✔" : "schul_kategorie_id-id"
"fact_schulen✔" ||--o{ "schul_jahr✔" : "schul_jahr_id-id"
"fact_personal✔" ||--o{ "schule✔" : "schule_id-id"
"schule✔" ||--o{ "ganztags_art✔" : "ganztags_art_id-id"
"fact_personal✔" ||--o{ "schule✔" : "schule_id-id"
"schule✔" ||--o{ "traeger✔" : "traeger_id-id"
"traeger✔" ||--o{ "traeger_art✔" : "traeger_art_id-id"
"traeger_art✔" ||--o{ "traeger_kategorie✔" : "traeger_kat_id-id"
"fact_personal✔" ||--o{ "schule✔" : "schule_id-id"
"schule✔" ||--o{ "schul_art✔" : "schul_art_id-id"
"schul_art✔" ||--o{ "schul_kategorie✔" : "schul_kategorie_id-id"
"fact_personal✔" ||--o{ "schul_jahr✔" : "schul_jahr_id-id"
"fact_personal✔" ||--o{ "alters_gruppe✔" : "alters_gruppe_id-id"
"fact_personal✔" ||--o{ "geschlecht✔" : "geschlecht_id-id"
"fact_personal✔" ||--o{ "personal_art✔" : "personal_art_id-id"
"fact_schueler✔" ||--o{ "schule✔" : "schule_id-id"
"schule✔" ||--o{ "ganztags_art✔" : "ganztags_art_id-id"
"fact_schueler✔" ||--o{ "schule✔" : "schule_id-id"
"schule✔" ||--o{ "traeger✔" : "traeger_id-id"
"traeger✔" ||--o{ "traeger_art✔" : "traeger_art_id-id"
"traeger_art✔" ||--o{ "traeger_kategorie✔" : "traeger_kat_id-id"
"fact_schueler✔" ||--o{ "schule✔" : "schule_id-id"
"schule✔" ||--o{ "schul_art✔" : "schul_art_id-id"
"schul_art✔" ||--o{ "schul_kategorie✔" : "schul_kategorie_id-id"
"fact_schueler✔" ||--o{ "schul_jahr✔" : "schul_jahr_id-id"
"fact_schueler✔" ||--o{ "geschlecht✔" : "geschlecht_id-id"
"fact_schueler✔" ||--o{ "wohnort_landkreis✔" : "wohn_lk_id-id"
"wohnort_landkreis✔" ||--o{ "bundesland✔" : "bundesland_id-id"
"fact_schueler✔" ||--o{ "einschulung✔" : "einschulung_id-id"
"fact_schueler✔" ||--o{ "schul_abschluss✔" : "schul_abschluss_id-id"
"fact_schueler✔" ||--o{ "klassen_wiederholung✔" : "klassen_wdh-id"
"fact_schueler✔" ||--o{ "migrations_hintergrund✔" : "migrations_hg_id-id"
"fact_schueler✔" ||--o{ "foerderung_art✔" : "foerder_art_id-id"
"foerderung_art✔" ||--o{ "sonderpaed_foerderbedarf✔" : "sp_foerderbedarf_id-id"
```
---
