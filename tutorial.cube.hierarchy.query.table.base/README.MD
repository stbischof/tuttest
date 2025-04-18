# Hierarchy - Query based on seperate Tables for Fact and Dimension

Very often, the data of a cube is not stored in a single table, but in multiple tables. In this case, it must be defined one query for the Facts to store the values that be aggregated for the measures and one for the Levels. This example shows how this must be defined.


## Database Schema

The cube defined in this example is based on two tables. Fact and Town. The Fact table contains a measures and a reference to the Town table. The Fact table is linked with its ID column to the Town table by the TOWN_ID column.            .


```xmi
<roma:DatabaseSchema   id="_dbschema">
  <tables xsi:type="roma:PhysicalTable" id="_tab_fact" name="Fact">
    <columns xsi:type="roma:PhysicalColumn" id="_col_fact_townId" name="TOWN_ID" type="Integer"/>
    <columns xsi:type="roma:PhysicalColumn" id="_col_fact_value" name="VALUE" type="Integer"/>
  </tables>
  <tables xsi:type="roma:PhysicalTable" id="_tab_town" name="Town">
    <columns xsi:type="roma:PhysicalColumn" id="_col_town_id" name="ID" type="Integer"/>
    <columns xsi:type="roma:PhysicalColumn" id="_col_town_name" name="NAME"/>
  </tables>
</roma:DatabaseSchema>

```

## Query Level

The TableQuery for the Level, as it directly references the physical table `Town`.


```xmi
<roma:TableQuery  id="_Query_LevelTown" table="_tab_town"/>

```

## Query Fact

The TableQuery for the Level, as it directly references the physical table `Fact`.


```xmi
<roma:TableQuery  id="_query_Fact" table="_tab_fact"/>

```

## Level

The level used the `column` attribute to define the primary key column. It also defines the `nameColumn` attribute to define the column that contains the name of the level. The `nameColumn` attribute is optional, if it is not defined, the server will use the column defined in the `column` attribute as name column.


```xmi
<roma:Level  id="_level_town" name="Town" column="_col_town_id" nameColumn="_col_town_name"/>

```

## Hierarchy

This Hierarchy contains only one level. The `primaryKey` attribute defines the column that contains the primary key of the hierarchy. The `query` attribute references to the query that will be used to retrieve the data for the hierarchy.


```xmi
<roma:Hierarchy  id="_hierarchy_town" name="TownHierarchy" levels="_level_town" primaryKey="_col_town_id" query="_Query_LevelTown"/>

```

## Dimension

The Dimension has only one hierarchy.


```xmi
<roma:StandardDimension  id="_dim_town" name="Town" hierarchies="_hierarchy_town"/>

```

## Cube and DimensionConnector and Measure

The cube contains only one Measure in a unnamed MeasureGroup and references to the Dimension.

To connect the dimension to the cube, a DimensionConnector is used. The dimension has set the attribute `foreignKey` to define the column that contains the foreign key of the dimension in the fact table.


```xmi
<roma:PhysicalCube  id="_cube" name="Cube Query linked Tables" query="_query_Fact">
  <dimensionConnectors foreignKey="_col_fact_townId" dimension="_dim_town"/>
  <measureGroups>
    <measures id="_measure" name="theMeasure" column="_col_fact_value" aggregator="sum"/>
  </measureGroups>
</roma:PhysicalCube>

```


## Definition

This files represent the complete definition of the catalog.

```xmi
<?xml version="1.0" encoding="UTF-8"?>
<xmi:XMI xmi:version="2.0" xmlns:xmi="http://www.omg.org/XMI" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:roma="https://www.daanse.org/spec/org.eclipse.daanse.rolap.mapping">
  <roma:Catalog name="Hierarchy - Query based on seperate Tables for Fact and Dimension" cubes="_cube" dbschemas="_dbschema"/>
  <roma:DatabaseSchema id="_dbschema">
    <tables xsi:type="roma:PhysicalTable" id="_tab_fact" name="Fact">
      <columns xsi:type="roma:PhysicalColumn" id="_col_fact_townId" name="TOWN_ID" type="Integer"/>
      <columns xsi:type="roma:PhysicalColumn" id="_col_fact_value" name="VALUE" type="Integer"/>
    </tables>
    <tables xsi:type="roma:PhysicalTable" id="_tab_town" name="Town">
      <columns xsi:type="roma:PhysicalColumn" id="_col_town_id" name="ID" type="Integer"/>
      <columns xsi:type="roma:PhysicalColumn" id="_col_town_name" name="NAME"/>
    </tables>
  </roma:DatabaseSchema>
  <roma:TableQuery id="_query_Fact" table="_tab_fact"/>
  <roma:TableQuery id="_Query_LevelTown" table="_tab_town"/>
  <roma:Level id="_level_town" name="Town" column="_col_town_id" nameColumn="_col_town_name"/>
  <roma:Hierarchy id="_hierarchy_town" name="TownHierarchy" levels="_level_town" primaryKey="_col_town_id" query="_Query_LevelTown"/>
  <roma:StandardDimension id="_dim_town" name="Town" hierarchies="_hierarchy_town"/>
  <roma:PhysicalCube id="_cube" name="Cube Query linked Tables" query="_query_Fact">
    <dimensionConnectors foreignKey="_col_fact_townId" dimension="_dim_town"/>
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

- [Town](./data/Town.csv)

