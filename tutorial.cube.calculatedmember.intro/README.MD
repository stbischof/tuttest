# Cube - CalculatedMembers Intro

This tutorial discusses Calculated Members, which allow you to define members in the measure or dimension area of a cube without storing them directly in the database. Instead, these members are computed on the fly, often based on the values of other members or measures. This is particularly useful for creating derived measures or dimension members that are not present in the underlying data source.



## Database Schema

The Database Schema contains the Fact table with three columns: KEY and VALUE and VALUE_NUMERIC. The KEY column is used as the discriminator in the the Level and Hierarchy definitions.


```xmi
<roma:DatabaseSchema   id="_databaseschema">
  <tables xsi:type="roma:PhysicalTable" id="_table_fact" name="Fact">
    <columns xsi:type="roma:PhysicalColumn" id="_col_fact_key" name="KEY"/>
    <columns xsi:type="roma:PhysicalColumn" id="_col_fact_value" name="VALUE" type="Integer"/>
  </tables>
</roma:DatabaseSchema>

```

## Query

The Query is a simple TableQuery that selects all columns from the Fact table to use in in the hierarchy and in the cube for the measures.


```xmi
<roma:TableQuery  id="_query" table="_table_fact"/>

```

## Level

This Example uses one simple Level bases on the KEY column.


```xmi
<roma:Level  id="_level" name="theLevel" column="_col_fact_key"/>

```

## Hierarchy without hasAll Level

The Hierarchy is defined with the hasAll property set to true and the one level.


```xmi
<roma:Hierarchy  id="_hierarchy" name="theHierarchy" levels="_level" hasAll="true" primaryKey="_col_fact_key" query="_query"/>

```

## Dimension

The dimension is defined with the one hierarchy. The hierarchy is used in the cube and in the calculated member.


```xmi
<roma:StandardDimension  id="_dimension" name="theDimension" hierarchies="_hierarchy"/>

```

## Calculated Member in Measure

This calculated member only coes a calculation with both of the existing Measures. The Forula holds the calculation instruction. The Formula Expression is a MDX expression.


```xmi
<roma:CalculatedMember  id="_cm1" name="Calculated Member 1" formula="[Measures].[Measure1-Sum] / [Measures].[Measure2-Count]"/>

```

## Calculated Member in Dimension

This calculated member has also a Formula. Additionaly it references the Hierarchy where it should be addes and a Parent Expression that defins unter wich Element it should be added. The Parent Expression is a MDX expression.



```xmi
<roma:CalculatedMember  id="_cm2" name="Calculated Member 2" formula="[Measures].[Measure1-Sum] / [Measures].[Measure2-Count]" parent="[theDimension].[theHierarchy].[All theHierarchys]" hierarchy="_hierarchy"/>

```

## Cube and DimensionConnector and Measure

The cube is defines by the DimensionConnector and the MeasureGroup and most importantly the calculated members.


```xmi
<roma:PhysicalCube  id="_cube" name="Cube CalculatedMember" query="_query">
  <calculatedMembers id="_cm1" name="Calculated Member 1" formula="[Measures].[Measure1-Sum] / [Measures].[Measure2-Count]"/>
  <calculatedMembers id="_cm2" name="Calculated Member 2" formula="[Measures].[Measure1-Sum] / [Measures].[Measure2-Count]" parent="[theDimension].[theHierarchy].[All theHierarchys]" hierarchy="_hierarchy"/>
  <dimensionConnectors foreignKey="_col_fact_key" dimension="_dimension"/>
  <measureGroups>
    <measures id="Measure1-Sum" name="Measure1-Sum" column="_col_fact_value" aggregator="sum"/>
    <measures id="Measure2-Count" name="Measure2-Count" column="_col_fact_value" aggregator="count"/>
  </measureGroups>
</roma:PhysicalCube>

```


## Definition

This files represent the complete definition of the catalog.

```xmi
<?xml version="1.0" encoding="UTF-8"?>
<xmi:XMI xmi:version="2.0" xmlns:xmi="http://www.omg.org/XMI" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:roma="https://www.daanse.org/spec/org.eclipse.daanse.rolap.mapping">
  <roma:Catalog name="Cube - CalculatedMembers Intro" cubes="_cube" dbschemas="_databaseschema"/>
  <roma:DatabaseSchema id="_databaseschema">
    <tables xsi:type="roma:PhysicalTable" id="_table_fact" name="Fact">
      <columns xsi:type="roma:PhysicalColumn" id="_col_fact_key" name="KEY"/>
      <columns xsi:type="roma:PhysicalColumn" id="_col_fact_value" name="VALUE" type="Integer"/>
    </tables>
  </roma:DatabaseSchema>
  <roma:TableQuery id="_query" table="_table_fact"/>
  <roma:Level id="_level" name="theLevel" column="_col_fact_key"/>
  <roma:Hierarchy id="_hierarchy" name="theHierarchy" levels="_level" hasAll="true" primaryKey="_col_fact_key" query="_query"/>
  <roma:StandardDimension id="_dimension" name="theDimension" hierarchies="_hierarchy"/>
  <roma:PhysicalCube id="_cube" name="Cube CalculatedMember" query="_query">
    <calculatedMembers id="_cm1" name="Calculated Member 1" formula="[Measures].[Measure1-Sum] / [Measures].[Measure2-Count]"/>
    <calculatedMembers id="_cm2" name="Calculated Member 2" formula="[Measures].[Measure1-Sum] / [Measures].[Measure2-Count]" parent="[theDimension].[theHierarchy].[All theHierarchys]" hierarchy="_hierarchy"/>
    <dimensionConnectors foreignKey="_col_fact_key" dimension="_dimension"/>
    <measureGroups>
      <measures id="Measure1-Sum" name="Measure1-Sum" column="_col_fact_value" aggregator="sum"/>
      <measures id="Measure2-Count" name="Measure2-Count" column="_col_fact_value" aggregator="count"/>
    </measureGroups>
  </roma:PhysicalCube>
</xmi:XMI>

```
## Documentation

More information and visualisations about this Catalog you can find in the [Documentation](./DOCUMENTATION.MD).

## csv data


This files represent the data in the tables.

- [Fact](./data/Fact.csv)

