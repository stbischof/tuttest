# Dimension - Introduction

beside the Measures a cube can contain dimensions. Dimensions are used to slice, dice and piveaut the data in the cube. They can be used group the data, filter the data,or to provide additional context for the data. Dimensions consist of one or multiple Hierarchies. Hierarchies consist of one or multiple Levels. Each level can have one or multiple Properties. Properties are used to provide additional context for the data. They can be used to display additional information about the data in the cube, such as descriptions, labels, or other attributes.

In this example we will create the most simple version, a cube with one dimension. The dimension will have one hierarchy, which will have one level.


## Database Schema

The cube defined in this example is based on a single table that stores all the data. The table, named `Fact`, contains two columns: `KEY` and `VALUE`. The `KEY` column acts as a discriminator, while the `VALUE` column holds the measurements to be aggregated.


```xmi
<roma:DatabaseSchema   id="_dbschema">
  <tables xsi:type="roma:PhysicalTable" id="_tab" name="Fact">
    <columns xsi:type="roma:PhysicalColumn" id="_col_key" name="KEY"/>
    <columns xsi:type="roma:PhysicalColumn" id="_col_value" name="VALUE" type="Integer"/>
  </tables>
</roma:DatabaseSchema>

```

## Query

This example uses a TableQuery, as it directly references the physical table `Fact`.


```xmi
<roma:TableQuery  id="_query" table="_tab"/>

```

## Level

The level is the most basic element of a hierarchy. It defines the granularity of the data in the hierarchy. To create a Level we need do set the key column, which is the column that uniquely identifies the Level in the table. In this example we use the `KEY` column of the `Fact` table as the key column of the level.


```xmi
<roma:Level  id="_level" name="theLevel" column="_col_key"/>

```

## Hierarchy

A hierarchy is a collection of levels that defines the structure of data within a dimension. It provides a name for the group the contained Level elements.

To define a hierarchy, a query is required. This query is used to retrieve the data for the hierarchy. In this example, we use the same query as for the cube, but this is only for simplicity.

Additionally, a primary key column can be specified for the hierarchy. The primary key column uniquely identifies members and is referenced by rows in the fact table. However, setting a primary key column is not mandatory. If it is not defined, the server will automatically use the key of the lowest level in the hierarchy.


```xmi
<roma:Hierarchy  id="_hierarchy" name="theHierarchy" levels="_level" primaryKey="_col_key" query="_query"/>

```

## Dimension

The Dimension is the main element of the cube. It defines the structure of the data in the cube. The dimension can contain one or multiple hierarchies. In this example we use one hierarchy, which contains one level.


```xmi
<roma:StandardDimension  id="_dimension" name="theDimension" hierarchies="_hierarchy"/>

```

## Cube and DimensionConnector and Measure

The cube contains only one Measure in a unnamed MeasureGroup and references to the Dimension.

To connect the dimension to the cube, a DimensionConnector is used. The DimensionConnector defines the connection between the cube and the dimension. It can also be used to override the name of the dimension in the cube, this is relevant if you want to use the same dimension multiple times in one cube. But one Dimension also could be used in multiple cubes.


```xmi
<roma:PhysicalCube  id="_cube" name="CubeWithSimpleDimension" query="_query">
  <dimensionConnectors dimension="_dimension"/>
  <measureGroups>
    <measures id="_measure" name="theMeasure" column="_col_value" aggregator="sum"/>
  </measureGroups>
</roma:PhysicalCube>

```


## Definition

This files represent the complete definition of the catalog.

```xmi
<?xml version="1.0" encoding="UTF-8"?>
<xmi:XMI xmi:version="2.0" xmlns:xmi="http://www.omg.org/XMI" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:roma="https://www.daanse.org/spec/org.eclipse.daanse.rolap.mapping">
  <roma:Catalog id="_catalog" name="Dimension - Introduction" cubes="_cube" dbschemas="_dbschema"/>
  <roma:DatabaseSchema id="_dbschema">
    <tables xsi:type="roma:PhysicalTable" id="_tab" name="Fact">
      <columns xsi:type="roma:PhysicalColumn" id="_col_key" name="KEY"/>
      <columns xsi:type="roma:PhysicalColumn" id="_col_value" name="VALUE" type="Integer"/>
    </tables>
  </roma:DatabaseSchema>
  <roma:TableQuery id="_query" table="_tab"/>
  <roma:Level id="_level" name="theLevel" column="_col_key"/>
  <roma:Hierarchy id="_hierarchy" name="theHierarchy" levels="_level" primaryKey="_col_key" query="_query"/>
  <roma:StandardDimension id="_dimension" name="theDimension" hierarchies="_hierarchy"/>
  <roma:PhysicalCube id="_cube" name="CubeWithSimpleDimension" query="_query">
    <dimensionConnectors dimension="_dimension"/>
    <measureGroups>
      <measures id="_measure" name="theMeasure" column="_col_value" aggregator="sum"/>
    </measureGroups>
  </roma:PhysicalCube>
</xmi:XMI>

```
## Documentation

More information and visualisations about this Catalog you can find in the [Documentation](./DOCUMENTATION.MD).

## csv data


This files represent the data in the tables.

- [Fact](./data/Fact.csv)

