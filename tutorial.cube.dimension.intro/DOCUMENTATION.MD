# Documentation
### CatalogName : Dimension - Introduction
### Schema Dimension - Introduction : 
---
### Cubes :

    CubeWithSimpleDimension

---
#### Cube "CubeWithSimpleDimension":

    

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

### Cube "CubeWithSimpleDimension" diagram:

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
c0["CubeWithSimpleDimension"]{
M theMeasure ""
D _ ""
}
d00["theDimension"] {
H theHierarchy ""
}
h000["theHierarchy"] {
L theLevel ""
}
"c0" ||--|| "d00" : "KEY"
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
}
```
---
### Cube Matrix for Dimension - Introduction:
```mermaid
quadrantChart
title Cube Matrix
x-axis small level number --> high level number
y-axis Low row count --> High row count
quadrant-1 Complex
quadrant-2 Deep
quadrant-3 Simple
quadrant-4 Wide

Cube CubeWithSimpleDimension: [0.0500, 0.0001]
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
}

```
---
## Validation result for catalog Dimension - Introduction
## <span style='color: blue;'>WARNING</span> : 
|Type|   |
|----|---|
|DATABASE|Table: Schema must be set|
