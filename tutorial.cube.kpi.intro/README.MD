# Cube - KPI Introduction

This tutorial is an introduction to the concept of KPIs in data cubes.

A KPI has four important properties: value, goal, status, and trend. The most crucial (and mandatory) property is value. All four properties are defined as MDX expressions, which allows you to create an expression within the cube, give it a name, and associate a value with it.

To keep things simple in this example, we will use an existing measure in our expression.


## Database Schema

A table `Fact` with a Column `VALUE` to have a reference for the Measure.


```xmi
<roma:DatabaseSchema   id="_databaseSchema">
  <tables xsi:type="roma:PhysicalTable" id="_tab" name="Fact">
    <columns xsi:type="roma:PhysicalColumn" id="_col_fact_value" name="VALUE" type="Integer"/>
  </tables>
</roma:DatabaseSchema>

```

## KPI - value only

This KPI is defined solely by its value expression, which in this example references the following measure: `[Measures].[Measure1-Sum]`"


```xmi
<roma:Kpi  id="_kpi_1" name="Kpi1" value="[Measures].[Measure1-Sum]"/>

```

## KPI - DisplayFolder

This KPI is additionally using a ParentKpiID.


```xmi
<roma:Kpi  id="_kpi_2" name="Kpi2" value="[Measures].[Measure1-Sum]" parentKpiID="Kpi1"/>

```

## KPI - Parent

In addition to its value, this KPI has a display folder defined, which includes a folder hierarchy with folder and subfolder.


```xmi
<roma:Kpi  id="_kpi_4" name="Kpi3" displayFolder="theDisplayFolder\otherDisplayFolder" value="[Measures].[Measure1-Sum]"/>

```

## Cube and DimensionConnector and Measure

This cube holds references to the KPI, and does not use any dimensions.


```xmi
<roma:PhysicalCube  id="_cube" name="Cube Kpi" query="#_query">
  <kpis id="_kpi_1" name="Kpi1" value="[Measures].[Measure1-Sum]"/>
  <kpis id="_kpi_2" name="Kpi2" value="[Measures].[Measure1-Sum]" parentKpiID="Kpi1"/>
  <kpis id="_kpi_4" name="Kpi3" displayFolder="theDisplayFolder\otherDisplayFolder" value="[Measures].[Measure1-Sum]"/>
  <measureGroups>
    <measures id="Measure1-Sum" name="Measure1-Sum" column="#_col_fact_value" aggregator="sum"/>
  </measureGroups>
</roma:PhysicalCube>

```


## Definition

This files represent the complete definition of the catalog.

```xmi
<?xml version="1.0" encoding="UTF-8"?>
<xmi:XMI xmi:version="2.0" xmlns:xmi="http://www.omg.org/XMI" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:roma="https://www.daanse.org/spec/org.eclipse.daanse.rolap.mapping">
  <roma:Catalog name="Cube - KPI Introduction" cubes="_cube" dbschemas="_databaseSchema"/>
  <roma:DatabaseSchema id="_databaseSchema">
    <tables xsi:type="roma:PhysicalTable" id="_tab" name="Fact">
      <columns xsi:type="roma:PhysicalColumn" id="_col_fact_value" name="VALUE" type="Integer"/>
    </tables>
  </roma:DatabaseSchema>
  <roma:TableQuery id="_query" table="_tab"/>
  <roma:PhysicalCube id="_cube" name="Cube Kpi" query="_query">
    <kpis id="_kpi_1" name="Kpi1" value="[Measures].[Measure1-Sum]"/>
    <kpis id="_kpi_2" name="Kpi2" value="[Measures].[Measure1-Sum]" parentKpiID="Kpi1"/>
    <kpis id="_kpi_4" name="Kpi3" displayFolder="theDisplayFolder\otherDisplayFolder" value="[Measures].[Measure1-Sum]"/>
    <measureGroups>
      <measures id="Measure1-Sum" name="Measure1-Sum" column="_col_fact_value" aggregator="sum"/>
    </measureGroups>
  </roma:PhysicalCube>
</xmi:XMI>

```
## Documentation

More information and visualisations about this Catalog you can find in the [Documentation](./DOCUMENTATION.MD).

## csv data


This files represent the data in the tables.

- [Fact](./data/Fact.csv)

