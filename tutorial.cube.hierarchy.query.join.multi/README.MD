# Hierarchy - Query based on a 2 Joind with 3 Levels

If the database structure follows the Third Normal Form (3NF), hierarchies in a cube are not stored in a single table but are distributed across multiple tables.

For example, consider a Geographical hierarchy with the levels Town and Country and Continent. If each entity is stored in a separate table, with a primary-foreign key relationship linking them, a query must be defined that incorporates both tables and specifies how the levels are joined.
In This case, the query must include a join between the Town and Country tables, as well as a join between the Country Join and Continent tables.
The following example demonstrates how to define such a query.


## Database Schema

The cube defined in this example is based on three tables: Fact, Town, and Country.

- The Fact table contains measures and a reference to the Town table.
- The Fact table is linked to the Town table through the TOWN_ID column, which corresponds to the ID column in the Town table.
- The Town table includes a column that references the primary key of the Country table.
- The Country table consists of two columns: ID (primary key) and Name as well as  referenct to the Continent.
- The Continent table consists of two columns: ID (primary key) and Name.

This structure ensures that the hierarchy is properly normalized, following the Third Normal Form (3NF).


```xmi
<roma:DatabaseSchema   id="_dbschema">
  <tables xsi:type="roma:PhysicalTable" id="_tab_fact" name="Fact">
    <columns xsi:type="roma:PhysicalColumn" id="_col_fact_townId" name="TOWN_ID" type="Integer"/>
    <columns xsi:type="roma:PhysicalColumn" id="_col_fact_value" name="VALUE" type="Integer"/>
  </tables>
  <tables xsi:type="roma:PhysicalTable" id="_tab_town" name="Town">
    <columns xsi:type="roma:PhysicalColumn" id="_col_town_id" name="ID" type="Integer"/>
    <columns xsi:type="roma:PhysicalColumn" id="_col_town_name" name="NAME"/>
    <columns xsi:type="roma:PhysicalColumn" id="_col_town_countryid" name="COUNTRY_ID" type="Integer"/>
  </tables>
  <tables xsi:type="roma:PhysicalTable" id="_tab_country" name="Country">
    <columns xsi:type="roma:PhysicalColumn" id="_col_country_id" name="ID" type="Integer"/>
    <columns xsi:type="roma:PhysicalColumn" id="_col_country_name" name="NAME"/>
    <columns xsi:type="roma:PhysicalColumn" id="_col_country_continentid" name="CONTINENT_ID" type="Integer"/>
  </tables>
  <tables xsi:type="roma:PhysicalTable" id="_tab_continent" name="Continent">
    <columns xsi:type="roma:PhysicalColumn" id="_col_continent_id" name="ID" type="Integer"/>
    <columns xsi:type="roma:PhysicalColumn" id="_col_continent_name" name="NAME"/>
  </tables>
</roma:DatabaseSchema>

```

## Query - Level Town

The TableQuery for the Town level directly references the physical Town table.


```xmi
<roma:TableQuery  id="_query_town" table="#_tab_town"/>

```

## Query - Level Country

The TableQuery for the Country level directly references the physical Country table.


```xmi
<roma:TableQuery  id="_query_country" table="#_tab_country"/>

```

## Query - Join Town to Country

The JoinQuery specifies which TableQueries should be joined. It also defines the columns in each table that are used for the join:

- In the lower-level table (Town), the join uses the foreign key.
- In the upper-level table (Country), the join uses the primary key.


```xmi
<roma:JoinQuery  id="_query_TownToCountry">
  <left key="#_col_town_countryid" query="#_query_town"/>
  <right key="#_col_country_id" query="#_query_CountryToContinent"/>
</roma:JoinQuery>

```

## Query - Level Country

The TableQuery for the Continent level directly references the physical Continent table.


```xmi
<roma:TableQuery  id="_query_continent" table="#_tab_continent"/>

```

## Query - Join Town-Country-Join to Continent

The JoinQuery specifies which Queries should be joined. It also defines the columns in each table that are used for the join:

In this vase we join a TableQuery with a JoinQuery.
- In the lower-level it is the JoinQuery (Town-Country), the join uses the foreign key.
- In the upper-level it is the TableQuery (Continent), the join uses the primary key.


```xmi
<roma:JoinQuery  id="_query_TownToCountry">
  <left key="#_col_town_countryid" query="#_query_town"/>
  <right key="#_col_country_id" query="#_query_CountryToContinent"/>
</roma:JoinQuery>

```

## Query Fact

The TableQuery for the Level, as it directly references the physical table `Fact`.


```xmi
<roma:TableQuery  id="_query_fact" table="#_tab_fact"/>

```

## Level - Town

The Level uses the column attribute to specify the primary key column. Additionally, it defines the nameColumn attribute to specify the column that contains the name of the level.


```xmi
<roma:Level  id="_level_town" name="Town" column="#_col_town_id" nameColumn="#_col_town_name"/>

```

## Level - Country

The Country level follows the same pattern as the Town level.


```xmi
<roma:Level  id="_level_country" name="County" column="#_col_country_id" nameColumn="#_col_country_name"/>

```

## Level - Continent

The Continent level follows the same pattern as the Town ans Country level.


```xmi
<roma:Level  id="_level_continent" name="Continent" column="#_col_continent_id" nameColumn="#_col_continent_name"/>

```

## Hierarchy

This hierarchy consists of three levels: Town, Country and  Continent.
- The primaryKey attribute specifies the column that contains the primary key of the hierarchy.
- The query attribute references the Join-query used to retrieve the data for the hierarchy.

The order of the Levels in the hierarchy is important, as it determines the drill-down path for the hierarchy.


```xmi
<roma:Hierarchy  id="_hierarchy_town" name="TownHierarchy" levels="#_level_continent #_level_country #_level_town" primaryKey="#_col_town_id" query="#_query_TownToCountry"/>

```

## Dimension

The Dimension has only one hierarchy.


```xmi
<roma:StandardDimension  id="_dim" name="Continent - Country - Town" hierarchies="#_hierarchy_town"/>

```

## Cube and DimensionConnector and Measure

The cube contains only one Measure in a unnamed MeasureGroup and references to the Dimension.

To connect the dimension to the cube, a DimensionConnector is used. The dimension has set the attribute `foreignKey` to define the column that contains the foreign key of the dimension in the fact table.


```xmi
<roma:PhysicalCube  id="_cube" name="Cube Query linked Tables" query="#_query_fact">
  <dimensionConnectors foreignKey="#_col_fact_townId" dimension="#_dim"/>
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
  <roma:Catalog name="Hierarchy - Query based on a 2 Joind with 3 Levels" cubes="_cube" dbschemas="_dbschema"/>
  <roma:DatabaseSchema id="_dbschema">
    <tables xsi:type="roma:PhysicalTable" id="_tab_fact" name="Fact">
      <columns xsi:type="roma:PhysicalColumn" id="_col_fact_townId" name="TOWN_ID" type="Integer"/>
      <columns xsi:type="roma:PhysicalColumn" id="_col_fact_value" name="VALUE" type="Integer"/>
    </tables>
    <tables xsi:type="roma:PhysicalTable" id="_tab_town" name="Town">
      <columns xsi:type="roma:PhysicalColumn" id="_col_town_id" name="ID" type="Integer"/>
      <columns xsi:type="roma:PhysicalColumn" id="_col_town_name" name="NAME"/>
      <columns xsi:type="roma:PhysicalColumn" id="_col_town_countryid" name="COUNTRY_ID" type="Integer"/>
    </tables>
    <tables xsi:type="roma:PhysicalTable" id="_tab_country" name="Country">
      <columns xsi:type="roma:PhysicalColumn" id="_col_country_id" name="ID" type="Integer"/>
      <columns xsi:type="roma:PhysicalColumn" id="_col_country_name" name="NAME"/>
      <columns xsi:type="roma:PhysicalColumn" id="_col_country_continentid" name="CONTINENT_ID" type="Integer"/>
    </tables>
    <tables xsi:type="roma:PhysicalTable" id="_tab_continent" name="Continent">
      <columns xsi:type="roma:PhysicalColumn" id="_col_continent_id" name="ID" type="Integer"/>
      <columns xsi:type="roma:PhysicalColumn" id="_col_continent_name" name="NAME"/>
    </tables>
  </roma:DatabaseSchema>
  <roma:TableQuery id="_query_continent" table="_tab_continent"/>
  <roma:TableQuery id="_query_town" table="_tab_town"/>
  <roma:TableQuery id="_query_country" table="_tab_country"/>
  <roma:TableQuery id="_query_fact" table="_tab_fact"/>
  <roma:JoinQuery id="_query_CountryToContinent">
    <left key="_col_country_continentid" query="_query_country"/>
    <right key="_col_continent_id" query="_query_continent"/>
  </roma:JoinQuery>
  <roma:JoinQuery id="_query_TownToCountry">
    <left key="_col_town_countryid" query="_query_town"/>
    <right key="_col_country_id" query="_query_CountryToContinent"/>
  </roma:JoinQuery>
  <roma:Level id="_level_town" name="Town" column="_col_town_id" nameColumn="_col_town_name"/>
  <roma:Level id="_level_country" name="County" column="_col_country_id" nameColumn="_col_country_name"/>
  <roma:Level id="_level_continent" name="Continent" column="_col_continent_id" nameColumn="_col_continent_name"/>
  <roma:Hierarchy id="_hierarchy_town" name="TownHierarchy" levels="_level_continent _level_country _level_town" primaryKey="_col_town_id" query="_query_TownToCountry"/>
  <roma:StandardDimension id="_dim" name="Continent - Country - Town" hierarchies="_hierarchy_town"/>
  <roma:PhysicalCube id="_cube" name="Cube Query linked Tables" query="_query_fact">
    <dimensionConnectors foreignKey="_col_fact_townId" dimension="_dim"/>
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

- [Continent](./data/Continent.csv)

- [Country](./data/Country.csv)

- [Fact](./data/Fact.csv)

- [Town](./data/Town.csv)

