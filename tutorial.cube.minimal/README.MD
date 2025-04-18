# Introduction into Cubes

Data cubes are the most important objects in OLAP. Cubes provide access to data related to a specific topic, which corresponds to the cube's name. Within the catalog, each data cube must have a unique name.


## Database Schema

The cube defined in this example is based on a single table that stores all the data. The table is named `Fact` and contains two columns: `KEY` and `VALUE`. The KEY column serves as a discriminator, while the `VALUE` column contains the measurements to be aggregated.


```xmi
<roma:DatabaseSchema   id="_dbschema">
  <tables xsi:type="roma:PhysicalTable" id="_tab" name="Fact">
    <columns xsi:type="roma:PhysicalColumn" id="_col_key" name="KEY"/>
    <columns xsi:type="roma:PhysicalColumn" id="_col_value" name="VALUE" type="Integer"/>
  </tables>
</roma:DatabaseSchema>

```

## Query

The bridge between the cube and the database is the query element. In this case, it is a TableQuery, as it directly references the physical table `Fact`. The query element is not visible to users accessing the cube through the XMLA API, such as Daanse Dashboard, Power BI, or Excel.


```xmi
<roma:TableQuery  id="_query" table="_tab"/>

```

## Cube, MeasureGroup and Measure

The cube is the element visible to users in analysis tools. A cube is based on elements such as measures, dimensions, hierarchies, KPIs, and named sets. In this case, we only define measures, which are the minimal required elements. The other elements are optional. To link a measure to the cube, we use the `MeasureGroup` element. The `MeasureGroup` is useful for organizing multiple measures into logical groups. Measures are used to define the data that should be aggregated. In this example, the measure is named Measure-Sum and references the `VALUE` column in the Fact table. The measure is aggregated using summation.


```xmi
<roma:PhysicalCube  id="_cube" name="MinimalCube" query="_query">
  <measureGroups>
    <measures id="_measure" name="Measure-Sum" column="_col_value" aggregator="sum"/>
  </measureGroups>
</roma:PhysicalCube>

```


## Definition

This files represent the complete definition of the catalog.

```xmi
<?xml version="1.0" encoding="UTF-8"?>
<xmi:XMI xmi:version="2.0" xmlns:xmi="http://www.omg.org/XMI" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:roma="https://www.daanse.org/spec/org.eclipse.daanse.rolap.mapping">
  <roma:Catalog id="_cat" name="Cube - Minimal" cubes="_cube" dbschemas="_dbschema"/>
  <roma:DatabaseSchema id="_dbschema">
    <tables xsi:type="roma:PhysicalTable" id="_tab" name="Fact">
      <columns xsi:type="roma:PhysicalColumn" id="_col_key" name="KEY"/>
      <columns xsi:type="roma:PhysicalColumn" id="_col_value" name="VALUE" type="Integer"/>
    </tables>
  </roma:DatabaseSchema>
  <roma:TableQuery id="_query" table="_tab"/>
  <roma:PhysicalCube id="_cube" name="MinimalCube" query="_query">
    <measureGroups>
      <measures id="_measure" name="Measure-Sum" column="_col_value" aggregator="sum"/>
    </measureGroups>
  </roma:PhysicalCube>
</xmi:XMI>

```
## Documentation

More information and visualisations about this Catalog you can find in the [Documentation](./DOCUMENTATION.MD).

## csv data


This files represent the data in the tables.

- [Fact](./data/Fact.csv)

