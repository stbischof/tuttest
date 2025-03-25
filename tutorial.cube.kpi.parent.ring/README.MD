# Cube - KPI Introduction

This tutorial is an introduction to the concept of KPIs in data cubes with parent KPI.


Kpi1 is parent for Kpi2. Kpi2 is parent for Kpi3. Kpi3 is again parent for Kpi1.

Be carefull to not do that. Excel not able to find parent and show empty KPI tree


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

This KPI is defined solely by its value expression, which in this example references the following measure: `[Measures].[Measure1-Sum]`
This KPI is additionally using a Kpi3 as parent. We have cyrcle link here"


```xmi
<roma:Kpi  id="_kpi_1" name="Kpi1" value="[Measures].[Measure1-Sum]" parentKpi="#_kpi_3"/>

```

## KPI - DisplayFolder

This KPI is additionally using a Kpi1 as parent.


```xmi
<roma:Kpi  id="_kpi_2" name="Kpi2" value="[Measures].[Measure1-Sum]" parentKpi="#_kpi_1"/>

```

## KPI - Parent

This KPI is additionally using a Kpi2 as parent. And this KPI is parent for Kpi1.


```xmi
<roma:Kpi  id="_kpi_3" name="Kpi3" value="[Measures].[Measure1-Sum]" parentKpi="#_kpi_1"/>

```

## Cube and Measure and KPI parent ring

This cube holds references to the KPI, and does not use any dimensions.


```xmi
<roma:PhysicalCube  id="_cube" name="Cube Kpi" query="#_query">
  <kpis id="_kpi_1" name="Kpi1" value="[Measures].[Measure1-Sum]" parentKpi="_kpi_3"/>
  <kpis id="_kpi_2" name="Kpi2" value="[Measures].[Measure1-Sum]" parentKpi="_kpi_1"/>
  <kpis id="_kpi_3" name="Kpi3" value="[Measures].[Measure1-Sum]" parentKpi="_kpi_1"/>
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
  <roma:Catalog name="Cube - KPI parent ring" cubes="_cube" dbschemas="_databaseSchema"/>
  <roma:DatabaseSchema id="_databaseSchema">
    <tables xsi:type="roma:PhysicalTable" id="_tab" name="Fact">
      <columns xsi:type="roma:PhysicalColumn" id="_col_fact_value" name="VALUE" type="Integer"/>
    </tables>
  </roma:DatabaseSchema>
  <roma:TableQuery id="_query" table="_tab"/>
  <roma:PhysicalCube id="_cube" name="Cube Kpi" query="_query">
    <kpis id="_kpi_1" name="Kpi1" value="[Measures].[Measure1-Sum]" parentKpi="_kpi_3"/>
    <kpis id="_kpi_2" name="Kpi2" value="[Measures].[Measure1-Sum]" parentKpi="_kpi_1"/>
    <kpis id="_kpi_3" name="Kpi3" value="[Measures].[Measure1-Sum]" parentKpi="_kpi_1"/>
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

