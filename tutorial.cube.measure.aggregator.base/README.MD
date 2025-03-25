# Multiple Measures and Aggragators

Data cubes can also have multiple measures when different aggregations are required for a column.


## Database Schema

The cube defined in this example is based on a single table that stores all the data. The table, named `Fact`, contains two columns: `KEY` and `VALUE`. The `KEY` column acts as a discriminator, while the `VALUE` column holds the measurements to be aggregated.


```xmi
<roma:DatabaseSchema   id="databaseSchema">
  <tables xsi:type="roma:PhysicalTable" id="_tab" name="Fact">
    <columns xsi:type="roma:PhysicalColumn" id="_col_key" name="KEY"/>
    <columns xsi:type="roma:PhysicalColumn" id="_col" name="VALUE" type="Integer"/>
  </tables>
</roma:DatabaseSchema>

```

## Query

This example uses a TableQuery, as it directly references the physical table `Fact`.


```xmi
<roma:TableQuery  id="_query" table="_tab"/>

```

## Cube, MeasureGroup and Measure

In this example, multiple measures are defined. All measures reference the `VALUE` column and use the following aggregation functions:
- SUM – Calculates the sum of the values.
- MIN – Retrieves the minimum value.
- MAX – Retrieves the maximum value.
- AVG – Computes the average of the values.


```xmi
<roma:PhysicalCube  id="_cube" name="MeasuresAggregatorsCube" query="_query">
  <measureGroups>
    <measures id="_measure1" name="Sum of Value" column="_col" aggregator="sum"/>
    <measures id="_measure2" name="Max of Value" column="_col" aggregator="max"/>
    <measures id="_measure3" name="Min of Value" column="_col" aggregator="min"/>
    <measures id="_measure4" name="Avg of Value" column="_col" aggregator="avg"/>
  </measureGroups>
</roma:PhysicalCube>

```


## Definition

This files represent the complete definition of the catalog.

```xmi
<?xml version="1.0" encoding="UTF-8"?>
<xmi:XMI xmi:version="2.0" xmlns:xmi="http://www.omg.org/XMI" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:roma="https://www.daanse.org/spec/org.eclipse.daanse.rolap.mapping">
  <roma:Catalog name="Cube - Measures and Aggregators" cubes="_cube" dbschemas="databaseSchema"/>
  <roma:DatabaseSchema id="databaseSchema">
    <tables xsi:type="roma:PhysicalTable" id="_tab" name="Fact">
      <columns xsi:type="roma:PhysicalColumn" id="_col_key" name="KEY"/>
      <columns xsi:type="roma:PhysicalColumn" id="_col" name="VALUE" type="Integer"/>
    </tables>
  </roma:DatabaseSchema>
  <roma:TableQuery id="_query" table="_tab"/>
  <roma:PhysicalCube id="_cube" name="MeasuresAggregatorsCube" query="_query">
    <measureGroups>
      <measures id="_measure1" name="Sum of Value" column="_col" aggregator="sum"/>
      <measures id="_measure2" name="Max of Value" column="_col" aggregator="max"/>
      <measures id="_measure3" name="Min of Value" column="_col" aggregator="min"/>
      <measures id="_measure4" name="Avg of Value" column="_col" aggregator="avg"/>
    </measureGroups>
  </roma:PhysicalCube>
</xmi:XMI>

```
## Documentation

More information and visualisations about this Catalog you can find in the [Documentation](./DOCUMENTATION.MD).

## csv data


This files represent the data in the tables.

- [Fact](./data/Fact.csv)

