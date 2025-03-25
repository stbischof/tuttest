# Documentation
### CatalogName : Cube - Measures Multiple
### Schema Cube - Measures Multiple : 
---
### Cubes :

    MultipleMeasuresCube

---
#### Cube "MultipleMeasuresCube":

    

##### Table: "Fact"

### Cube "MultipleMeasuresCube" diagram:

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
c0["MultipleMeasuresCube"]{
M Sum_of_Value1 ""
M Sum_of_Value2 ""
M Sum_of_Value3 ""
}
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
int VALUE1 "is null (32.0) ✔"
int VALUE2 "is null (32.0) ✔"
int VALUE3 "is null (32.0) ✔"
}

```
---
" Aggregation section:

---
```mermaid
   erDiagram
"Fact✔"{
string KEY "is null (1000000000.0) ✔"
int VALUE1 "is null (32.0) ✔"
int VALUE2 "is null (32.0) ✔"
int VALUE3 "is null (32.0) ✔"
}
```
---
### Cube Matrix for Cube - Measures Multiple:
```mermaid
quadrantChart
title Cube Matrix
x-axis small level number --> high level number
y-axis Low row count --> High row count
quadrant-1 Complex
quadrant-2 Deep
quadrant-3 Simple
quadrant-4 Wide

Cube MultipleMeasuresCube: [0.0000, 0.0001]
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
int VALUE1 "is null (32.0) ✔"
int VALUE2 "is null (32.0) ✔"
int VALUE3 "is null (32.0) ✔"
}

```
---
## Validation result for catalog Cube - Measures Multiple
## <span style='color: blue;'>WARNING</span> : 
|Type|   |
|----|---|
|DATABASE|Table: Schema must be set|
