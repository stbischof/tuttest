# Documentation
### CatalogName : Cube - CalculatedMembers Intro
### Schema Cube - CalculatedMembers Intro : 
---
### Cubes :

    Cube CalculatedMember

---
#### Cube "Cube CalculatedMember":

    

##### Table: "Fact"

##### Dimensions:
##### Dimension "":

Hierarchies:

    theHierarchy

##### Hierarchy theHierarchy:

Tables: "Fact"

Levels: "theLevel"

###### Level "theLevel" :

    column(s): KEY

### Cube "Cube CalculatedMember" diagram:

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
c0["Cube CalculatedMember"]{
M Measure1-Sum ""
M Measure2-Count ""
D _ ""
CM Calculated_Member_1 ""
CM Calculated_Member_2 ""
}
d00["theDimension"] {
H theHierarchy ""
}
h000["theHierarchy"] {
L theLevel ""
}
"c0" ||--|| "d00" : "KEY-KEY"
"d00" ||--|| "h000" : "KEY-KEY"
```
---
### Database :
---
```mermaid
---
title: Diagram;
---
erDiagram
"Fact✔"{
string KEY "is null (1000000000.0) ✔"
int VALUE "is null (32.0) ✔"
double VALUE_NUMERIC "is null (100000.0) ✔"
}

```
---
" Aggregation section:

---
```mermaid
   erDiagram
"Fact✔"{
string KEY "is null (1000000000.0) ✔"
int VALUE "is null (32.0) ✔"
double VALUE_NUMERIC "is null (100000.0) ✔"
}
```
---
### Cube Matrix for Cube - CalculatedMembers Intro:
```mermaid
quadrantChart
title Cube Matrix
x-axis small level number --> high level number
y-axis Low row count --> High row count
quadrant-1 Complex
quadrant-2 Deep
quadrant-3 Simple
quadrant-4 Wide

Cube Cube_CalculatedMember: [0.0500, 0.0001]
```
---
### Database :
---
```mermaid
---
title: Diagram;
---
erDiagram
"Fact✔"{
string KEY "is null (1000000000.0) ✔"
int VALUE "is null (32.0) ✔"
double VALUE_NUMERIC "is null (100000.0) ✔"
}

```
---
