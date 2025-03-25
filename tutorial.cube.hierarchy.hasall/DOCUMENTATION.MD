# Documentation
### CatalogName : Hierarchy - HasAll-Level
### Schema Hierarchy - HasAll-Level : 
---
### Cubes :

    HasAll Cube

---
#### Cube "HasAll Cube":

    

##### Table: "Fact"

##### Dimensions:
##### Dimension "":

Hierarchies:

    Hierarchy - with HasAll, Hierarchy - with HasAll and Names, Hierarchy - Without HasAll

##### Hierarchy Hierarchy - with HasAll:

Tables: "Fact"

Levels: "theLevel"

###### Level "theLevel" :

    column(s): KEY

##### Hierarchy Hierarchy - with HasAll and Names:

Tables: "Fact"

Levels: "theLevel"

###### Level "theLevel" :

    column(s): KEY

##### Hierarchy Hierarchy - Without HasAll:

Tables: "Fact"

Levels: "theLevel"

###### Level "theLevel" :

    column(s): KEY

### Cube "HasAll Cube" diagram:

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
c0["HasAll Cube"]{
M theMeasure ""
D _ ""
}
d00["Dimension1"] {
H Hierarchy_-_with_HasAll ""
H Hierarchy_-_with_HasAll_and_Names ""
H Hierarchy_-_Without_HasAll ""
}
h000["Hierarchy_-_with_HasAll"] {
L theLevel ""
}
h001["Hierarchy_-_with_HasAll_and_Names"] {
L theLevel ""
}
h002["Hierarchy_-_Without_HasAll"] {
L theLevel ""
}
"c0" ||--|| "d00" : "KEY"
"d00" ||--|| "h000" : "KEY-KEY"
"c0" ||--|| "d00" : "KEY"
"d00" ||--|| "h001" : "KEY-KEY"
"c0" ||--|| "d00" : "KEY"
"d00" ||--|| "h002" : "KEY-KEY"
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
### Cube Matrix for Hierarchy - HasAll-Level:
```mermaid
quadrantChart
title Cube Matrix
x-axis small level number --> high level number
y-axis Low row count --> High row count
quadrant-1 Complex
quadrant-2 Deep
quadrant-3 Simple
quadrant-4 Wide

Cube HasAll_Cube: [0.1500, 0.0001]
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
## Validation result for catalog Hierarchy - HasAll-Level
## <span style='color: red;'>ERROR</span> : 
|Type|   |
|----|---|
|SCHEMA|Dimension connector override name must be set for cube with name HasAll Cube|
|SCHEMA|Hierarchy: Table field must be empty in dimension with name Dimension1|
|DATABASE|Hierarchy: Table value does not correspond to Hierarchy Relation  in dimension with name Dimension1|
## <span style='color: blue;'>WARNING</span> : 
|Type|   |
|----|---|
|DATABASE|Table: Schema must be set|
