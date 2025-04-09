# Eclipse Daanse – Die neue Generation datengetriebener Dashboards

Eclipse Daanse ist ein vollständig clientseitiger Dashboard-Editor und Viewer, der speziell für die moderne Verwaltung, Analyse und Visualisierung heterogener Datenquellen entwickelt wurde. Im Gegensatz zu klassischen Lösungen wie **Grafana** oder **Apache Superset** verfolgt Daanse einen konsequenten *No-Server-Ansatz*, was insbesondere im Bereich *Open Data* und *Smart City* neue Maßstäbe setzt.

---

## 🌟 Vorteile im Überblick

| Merkmal | Eclipse Daanse | Grafana | Apache Superset |
|--------|----------------|---------|------------------|
| Serverfreie Architektur | ✅ | ❌ | ❌ |
| Direkte Nutzung offener Schnittstellen | ✅ | ⚠️ oft nur mit eigenem Backend | ⚠️ teilweise |
| Granulare Widgetgestaltung | ✅ pixelgenau & responsive | ⚠️ begrenzt | ⚠️ begrenzt |
| Datenverbindungen kombinierbar | ✅ auch live + historisch + statisch | ⚠️ nur über Plugins | ⚠️ mit SQL |
| Vollständig offlinefähig | ✅ PWA/Desktop | ❌ | ❌ |
| SensorThings API (Live, Historie, Stammdaten) | ✅ nativ | ⚠️ Plugins | ❌ |
| Kartenclient (OGC Maps, Features etc.) | ✅ | ⚠️ eingeschränkt | ⚠️ kaum vorhanden |
| OLAP / BI über XMLA | ✅ | ⚠️ über Plugin | ⚠️ experimentell |
| *Git-Integration zur Nachvollziehbarkeit* | ✅ | ❌ | ❌ |
| *Open Data Registry Integration (DCAT)* | ✅ | ❌ | ❌ |

---

## 🖼️ Dashboards & Widgets

### Frei gestaltbare Dashboards

- **Pixelgenau positionierbar**: Absolute Platzierung aller Widgets.
- **Responsiv**: Automatische Anpassung an Bildschirmgrößen bei variabler Widgetgröße.

### Mächtige Widgets

#### Diagramme
- Balken-, Linien- und Kreisdiagramme.
- *Dynamische Farb- und Schattenanpassung nach Tageszeit.*

#### Tabellen
- Spaltenfilter, Sortierung, Paginierung.
- Spalten- und Zeilenhervorhebung, Export.
- *Flexible Spaltenformatierung.*

#### Pivot-Tables (wie in Excel)
- Auswahl von Datacubes, Dimensionen und Measures.
- Exportmöglichkeit.
- *Ideal für BI-Analysen.*

#### Weitere Widgets
- **Icons**: Aus wählbaren Katalogen, farblich anpassbar.
- **Bilder**: Mit *Filterfunktionen wie Unschärfe, Kontrast etc.*
- **Progressbars und Gauges**: Für KPIs und Zielwerte.
- **SVG & Repeatable SVGs**: SVGs auch dynamisch basierend auf Werten wiederholbar (z. B. 10 Personen statt einer).
- **Text & RichText**: Mit variablen Platzhaltern, formatiert oder unformatiert.
- **Video-Player**: Mit oder ohne Steuerung.
- **Karten**: Darstellung von Geo-Daten (OSG Maps, SensorThings, CSV etc.).

---

## 🔌 Datenquellen & Schnittstellen

Eclipse Daanse unterstützt eine Vielzahl moderner Datenformate und Schnittstellen – viele davon nativ:

### OGC & Geo
- OGC Maps (Kartenbilder).
- OGC Features (Geo-JSON Objekte inkl. Metadaten).

### OLAP & BI
- **XMLA**: Zugriff auf OLAP-Cubes (z. B. MS Analysis Services, Daanse OLAP Server).
- **SQL über XMLA**: Direkter, sicherer Zugriff auf Datenbanken mit Rollen- und Rechtemanagement.

### REST & CSV
- REST-basierter CSV-Import mit Delimiter-Wahl und Teilimport.
- JSON & XML REST-Schnittstellen.

### Semantisches Web & RDF
- SPARQL-Zugriffe auf Wikidata, DCAT, GovData, *Open Energy Plattform, etc.*

### SensorThings API
- Historische Zeitreihen, Sensorstammdaten, Live-Daten via REST & MQTT/Websockets.

### Echtzeit-Protokolle
- **MQTT native**: Für Ereignisgesteuerte Dashboards.
- **WebSocket**: Direkter Zugriff auf Events.
- **RSS**: Für Veranstaltungs-, Termin- und Nachrichtendaten.
- **GraphQL**: Moderne Abfragesprache mit Filtern – *Subscriptions geplant.*

---

## 🔁 Variablen

- **Konstante Werte** (z. B. Dashboardspezifisch).
- **Berechnete Variablen** (Formeln).
- **Zeitbasierte Variablen** (Dynamik nach Uhrzeit).
- **Abfrageergebnisse** als Variablen verwendbar.

Alle Eigenschaften von Widgets & Dashboards sind parametrisierbar – dadurch werden vollständig interaktive und dynamische Dashboards möglich.

Beispiel: Ein Dashboard mit Sensor-Daten kann per Button-Druck zwischen Objekten wechseln – ohne Neuladen oder Backendinteraktion.

---

## ✨ Besonderheiten & Alleinstellungsmerkmale

### 1. **Client Only – Kein Server notwendig**

- Läuft im Webbrowser, als **PWA**, **Desktop-App** (macOS, Windows, Linux), Flatpak und AppImage.
- Keine Middleware oder Datenverarbeitung auf Servern → *Ideal für Open Data*.

### 2. **Datenschutz & Rechteverwaltung**

- Daten verbleiben beim ursprünglichen Anbieter.
- Kein zweites Rechtemanagement notwendig (anders als bei Grafana/Superset).
- Keine „Super-User“-Konten mit Vollzugriff.

### 3. **Open Data Integration**

- Direkte Abfrage von DCAT-Registries wie [data.europa.eu](https://data.europa.eu) und [GovData.de](https://www.govdata.de/).
- Einfache Visualisierung ohne technische Kenntnisse.
- *Empfohlene Widgets werden automatisch vorgeschlagen.*

### 4. **Datenverschmelzung & Interoperabilität**

- **Dashboard-Ebene**: Kombination aus Geo-Daten, Live-Sensorik, Stammdaten und Statistik möglich.
- **Widget-Ebene**: Mischen mehrerer Datenquellen in einer Ansicht (z. B. Tabelle oder Karte).

### 5. **Versionierung & Transparenz mit Git**

- Dashboards versionierbar.
- Unterschiede zwischen Varianten (z. B. Fraktionsansichten in der Politik) nachvollziehbar.
- *Ideal für transparente Entscheidungsprozesse.*

---

## 🔧 Zukünftige Features *(in Planung)*

- PromQL (Prometheus).
- Elasticsearch / OpenSearch Anbindung.
- KPI-spezifische Widgets.
- *Template-Editor mit modellbasiertem Aufbau.*
- *Drag-and-Drop UI zur Dashboard-Erstellung.*

---

## 🆚 Vergleich mit Grafana & Superset

| Kriterium | Eclipse Daanse | Grafana | Superset |
|----------|----------------|---------|----------|
| Open Source | ✅ | ✅ | ✅ |
| Server notwendig | ❌ | ✅ | ✅ |
| Daten direkt im Browser verarbeitet | ✅ | ❌ | ❌ |
| DCAT/OpenData Registry | ✅ | ❌ | ❌ |
| MQTT/WebSocket Unterstützung | ✅ | ⚠️ (nur mit Plugins) | ❌ |
| SensorThings API | ✅ | ⚠️ Plugins | ❌ |
| SPARQL/RDF | ✅ | ❌ | ⚠️ experimentell |
| Visualisierung von SVGs | ✅ | ❌ | ❌ |
| Kartenclient (OGC-konform) | ✅ | ⚠️ begrenzt | ⚠️ kaum vorhanden |
| XMLA & OLAP-Datenquellen | ✅ | ⚠️ experimentell | ⚠️ experimentell |
| Git-basierte Historie | ✅ | ❌ | ❌ |
| Vollständig responsives Layout | ✅ | ⚠️ | ⚠️ |
| Desktop App möglich | ✅ | ⚠️ | ❌ |

---

## 🚀 Fazit

**Eclipse Daanse** ist keine bloße Dashboard-Alternative, sondern ein **komplett neu gedachtes Visualisierungs-Framework**, das alle Anforderungen moderner Datenplattformen – insbesondere im Open- und Urban-Data-Kontext – erfüllt:

- **Datenschutzkonform**, **granular**, **hochflexibel**, **vollständig clientbasiert**.
- Kein Vendor-Lock-In, keine Serverkosten, volle Kontrolle.

> *Wer Open Data wirklich offen nutzen will, braucht eine Lösung wie Daanse.*





----


Daanse Server Tutorials
# Tutorials 

- [Schulwesen](./complex.school/README.MD)

- [Database - Intro](./tutorial.database.intro/README.MD)

- [Database - ColumnTypes](./tutorial.database.column/README.MD)

- [Database - SQL Expression Column](./tutorial.database.expressioncolumn/README.MD)

- [Database - Schema](./tutorial.database.schema/README.MD)

- [Database - Table](./tutorial.database.table/README.MD)

- [Database - SqlView](./tutorial.database.sqlview/README.MD)

- [Database - InlineTable](./tutorial.database.inlinetable/README.MD)

- [Cube - Minimal](./tutorial.cube.minimal/README.MD)

- [Cube - Measures and Aggregators](./tutorial.cube.measure.aggregator.base/README.MD)

- [Cube - Measures Multiple](./tutorial.cube.measure.multiple/README.MD)

- [Cube - Measures and Datatypes](./tutorial.cube.measure.datatype/README.MD)

- [Cube - Measures and Formats](./tutorial.cube.measure.format/README.MD)

- [Cube - Measures and MeasureGroups](./tutorial.cube.measure.group/README.MD)

- [Dimension - Introduction](./tutorial.cube.dimension.intro/README.MD)

- [Hierarchy - Query based on seperate Tables for Fact and Dimension](./tutorial.cube.hierarchy.query.table.base/README.MD)

- [Hierarchy - Query based on a Table with 2 Levels](./tutorial.cube.hierarchy.query.table.multilevel.multitable/README.MD)

- [Hierarchy - Query based on all in one Table](./tutorial.cube.hierarchy.query.table.multilevel.singletable/README.MD)

- [Hierarchy - Query based on Join](./tutorial.cube.hierarchy.query.join.base/README.MD)

- [Hierarchy - Query based on a 2 Joind with 3 Levels](./tutorial.cube.hierarchy.query.join.multi/README.MD)

- [Hierarchy - HasAll-Level](./tutorial.cube.hierarchy.hasall/README.MD)

- [Level - MemberProperties Intro](./tutorial.cube.level.member.property.intro/README.MD)

- [Cube - CalculatedMembers Intro](./tutorial.cube.calculatedmember.intro/README.MD)

- [Cube - KPI Introduction](./tutorial.cube.kpi.intro/README.MD)

- [Cube - KPI parent ring](./tutorial.cube.kpi.parent.ring/README.MD)
