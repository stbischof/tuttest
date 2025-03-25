# Documentation
### CatalogName : Cube - KPI parent ring
### Schema Cube - KPI parent ring : 
---
### Cubes :

    Cube Kpi

---
#### Cube "Cube Kpi":

    

##### Table: "Fact"

### Cube "Cube Kpi" diagram:

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
c0["Cube Kpi"]{
M Measure1-Sum ""
KPI Kpi1 ""
KPI Kpi2 ""
KPI Kpi3 ""
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
int VALUE "is null (32.0) ✔"
}

```
---
" Aggregation section:

---
```mermaid
   erDiagram
"Fact✔"{
int VALUE "is null (32.0) ✔"
}
```
---
### Cube Matrix for Cube - KPI parent ring:
```mermaid
quadrantChart
title Cube Matrix
x-axis small level number --> high level number
y-axis Low row count --> High row count
quadrant-1 Complex
quadrant-2 Deep
quadrant-3 Simple
quadrant-4 Wide

Cube Cube_Kpi: [0.0000, 0.0001]
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
int VALUE "is null (32.0) ✔"
}

```
---
## Validation result for catalog Cube - KPI parent ring
## <span style='color: blue;'>WARNING</span> : 
|Type|   |
|----|---|
|SCHEMA|KPIs from cube with name Cube Kpi has parent ring|
|DATABASE|Table: Schema must be set|
