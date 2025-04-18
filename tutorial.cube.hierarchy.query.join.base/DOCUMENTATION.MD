# Documentation
### CatalogName : Hierarchy - Query based on Join
### Schema Hierarchy - Query based on Join : 
---
### Cubes :

    Cube Query linked Tables

---
#### Cube "Cube Query linked Tables":

    

##### Table: "Fact"

##### Dimensions:
##### Dimension "":

Hierarchies:

    TownHierarchy

##### Hierarchy TownHierarchy:

Tables: "Town,Country"

Levels: "Town, County"

###### Level "Town" :

    column(s): ID

###### Level "County" :

    column(s): ID

### Cube "Cube Query linked Tables" diagram:

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
c0["Cube Query linked Tables"]{
M theMeasure ""
D _ ""
}
d00["Town"] {
H TownHierarchy ""
}
h000["TownHierarchy"] {
L Town ""
L County ""
}
"c0" ||--|| "d00" : "TOWN_ID-ID"
"d00" ||--|| "h000" : "ID-ID"
"d00" ||--|| "h000" : "ID-ID"
```
---
### Database :
---
```mermaid
---
title: Diagram;
---
erDiagram
"Country✔"{
int ID "is null (32.0) ✔"
string NAME "is null (1000000000.0) ✔"
}
"Fact✔"{
int TOWN_ID "is null (32.0) ✔"
int VALUE "is null (32.0) ✔"
}
"Town✔"{
int ID "is null (32.0) ✔"
string NAME "is null (1000000000.0) ✔"
int COUNTRY_ID "is null (32.0) ✔"
}

"Fact✔" ||--o{ "Town✔" : "TOWN_ID-ID"
"Town✔" ||--o{ "Country✔" : "ID-ID"
```
---
" Aggregation section:

---
```mermaid
   erDiagram
"Fact✔"{
int TOWN_ID "is null (32.0) ✔"
int VALUE "is null (32.0) ✔"
}
```
---
### Cube Matrix for Hierarchy - Query based on Join:
```mermaid
quadrantChart
title Cube Matrix
x-axis small level number --> high level number
y-axis Low row count --> High row count
quadrant-1 Complex
quadrant-2 Deep
quadrant-3 Simple
quadrant-4 Wide

Cube Cube_Query_linked_Tables: [0.1000, 0.0001]
```
---
### Database :
---
```mermaid
---
title: Diagram;
---
erDiagram
"Country✔"{
int ID "is null (32.0) ✔"
string NAME "is null (1000000000.0) ✔"
}
"Fact✔"{
int TOWN_ID "is null (32.0) ✔"
int VALUE "is null (32.0) ✔"
}
"Town✔"{
int ID "is null (32.0) ✔"
string NAME "is null (1000000000.0) ✔"
int COUNTRY_ID "is null (32.0) ✔"
}

"Fact✔" ||--o{ "Town✔" : "TOWN_ID-ID"
"Town✔" ||--o{ "Country✔" : "ID-ID"
```
---
## Validation result for catalog Hierarchy - Query based on Join
## <span style='color: blue;'>WARNING</span> : 
|Type|   |
|----|---|
|DATABASE|Table: Schema must be set|
