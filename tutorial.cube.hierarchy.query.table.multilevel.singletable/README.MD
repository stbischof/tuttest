# Hierarchy - Query based on all in one Table

In some cases, all data are stored in one table, the fact as well as multiple levels. This Tutorial shows how to handle this case.


## Database Schema

The cube defined in this example is based on only one tables. The Fact table contains a measures the name of the Town and the Country.


```xmi
<roma:DatabaseSchema   id="_dbschema">
  <tables xsi:type="roma:PhysicalTable" id="_tab_fact" name="Fact">
    <columns xsi:type="roma:PhysicalColumn" id="_col_fact_country" name="KEY"/>
    <columns xsi:type="roma:PhysicalColumn" id="_col_fact_value" name="VALUE" type="Integer"/>
  </tables>
</roma:DatabaseSchema>

```

## Query Fact

The TableQuery for the Levels and the Measure.


```xmi
<roma:TableQuery  id="_query" table="#_tab_fact"/>

```

## Level

The level of the Town used the `column` attribute to define the column that holds the name, wich is also the key Column.


```xmi
<roma:Level  id="_level_town" name="Town" column="#_col_fact_key"/>

```

## Level

The level  of the Country used the `column` attribute to define the column that holds the name, wich is also the key Column.


```xmi
<roma:Level  id="_level_country" name="Country" column="#_col_fact_country"/>

```

## Hierarchy

This Hierarchy contains both defined levels. The `primaryKey` attribute defines the column that contains the primary key of the hierarchy. The `query` attribute references to the query that will be used to retrieve the data for the hierarchy.


```xmi
<roma:Hierarchy  id="_hierarchy_town" name="TownHierarchy" levels="#_level_town #_level_country" primaryKey="#_col_fact_key" query="#_query"/>

```

## Dimension

The Dimension has only one hierarchy.


```xmi
<roma:StandardDimension  id="_dim_town" name="Town" hierarchies="#_hierarchy_town"/>

```

## Cube and DimensionConnector and Measure

The cube contains only one Measure in a unnamed MeasureGroup and references to the Dimension.

To connect the dimension to the cube, a DimensionConnector is used. The dimension has set the attribute `foreignKey` to define the column that contains the foreign key of the dimension in the fact table.


```xmi
<roma:PhysicalCube  id="_cube" name="Cube Query linked Tables" query="#_query">
  <dimensionConnectors foreignKey="#_col_fact_country" dimension="#_dim_town"/>
  <measureGroups>
    <measures id="_measure" name="theMeasure" column="#_col_fact_value" aggregator="sum"/>
  </measureGroups>
</roma:PhysicalCube>

```


## Definition

This files represent the complete definition of the catalog.

```xmi
<?xml version="1.0" encoding="UTF-8"?>
<xmi:XMI xmi:version="2.0" xmlns:xmi="http://www.omg.org/XMI" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:roma="https://www.daanse.org/spec/org.eclipse.daanse.rolap.mapping">
  <roma:Catalog name="Hierarchy - Query based on all in one Table" cubes="_cube" dbschemas="_dbschema"/>
  <roma:DatabaseSchema id="_dbschema">
    <tables xsi:type="roma:PhysicalTable" id="_tab_fact" name="Fact">
      <columns xsi:type="roma:PhysicalColumn" id="_col_fact_country" name="KEY"/>
      <columns xsi:type="roma:PhysicalColumn" id="_col_fact_value" name="VALUE" type="Integer"/>
    </tables>
  </roma:DatabaseSchema>
  <roma:PhysicalColumn id="_col_fact_key" name="KEY"/>
  <roma:TableQuery id="_query" table="_tab_fact"/>
  <roma:Level id="_level_country" name="Country" column="_col_fact_country"/>
  <roma:Level id="_level_town" name="Town" column="_col_fact_key"/>
  <roma:Hierarchy id="_hierarchy_town" name="TownHierarchy" levels="_level_town _level_country" primaryKey="_col_fact_key" query="_query"/>
  <roma:StandardDimension id="_dim_town" name="Town" hierarchies="_hierarchy_town"/>
  <roma:PhysicalCube id="_cube" name="Cube Query linked Tables" query="_query">
    <dimensionConnectors foreignKey="_col_fact_country" dimension="_dim_town"/>
    <measureGroups>
      <measures id="_measure" name="theMeasure" column="_col_fact_value" aggregator="sum"/>
    </measureGroups>
  </roma:PhysicalCube>
</xmi:XMI>

```
## Documentation

More information and visualisations about this Catalog you can find in the [Documentation](./DOCUMENTATION.MD).

## csv data


This files represent the data in the tables.

- [Fact](./data/Fact.csv)

