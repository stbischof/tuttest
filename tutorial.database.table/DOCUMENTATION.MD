# Documentation
### CatalogName : Database - Table
### Schema Database - Table : 
---
### Cubes :

    

### Cube Matrix for Database - Table:
```mermaid
quadrantChart
title Cube Matrix
x-axis small level number --> high level number
y-axis Low row count --> High row count
quadrant-1 Complex
quadrant-2 Deep
quadrant-3 Simple
quadrant-4 Wide

```
---
### Database :
---
```mermaid
---
title: Diagram;
---
erDiagram
"TableOne✔"{
string ColumnOne "is null (1000000000.0) ✔"
}
"ViewOne❌"{
Varchar ColumnOne "is null ❌"
}

```
---
## Validation result for catalog Database - Table
## <span style='color: red;'>ERROR</span> : 
|Type|   |
|----|---|
|DATABASE|Table ViewOne does not exist in database|
