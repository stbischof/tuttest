# Eclipse Daanse – Die neue Generation datengetriebener Dashboards

Eclipse Daanse ist ein vollständig clientseitiger Dashboard-Editor und Viewer, der speziell für die moderne Verwaltung, Analyse und Visualisierung heterogener Datenquellen entwickelt wurde. Im Gegensatz zu klassischen Lösungen wie **Grafana** oder **Apache Superset** verfolgt Daanse einen konsequenten *No-Server-Ansatz*, was insbesondere im Bereich *Open Data* und *Smart City* neue Maßstäbe setzt.

---

## 🆚 Vergleich Eclipse Daanse vs. Grafana vs. Apache Superset

| Merkmal | Eclipse Daanse | Grafana | Apache Superset |
|--------|----------------|---------|------------------|
| **Open Source** | ✅ | ✅ | ✅ |
| **Server notwendig** | ❌ | ✅ | ✅ |
| **Datenverarbeitung im Browser (Client only)** | ✅ | ❌ | ❌ |
| **Responsive & pixelgenaue Dashboards** | ✅ | ⚠️ begrenzt | ⚠️ begrenzt |
| **Komplexe Layouts & Templates** | ✅ | ⚠️ Plugin-basiert | ⚠️ beschränkt |
| **Datenquellen kombinierbar (live, historisch, statisch)** | ✅ | ⚠️ nur über Plugins | ⚠️ mit SQL |
| **Offlinefähig / Desktop App (PWA, Flatpak, etc.)** | ✅ | ⚠️ begrenzt | ❌ |
| **Visualisierung von SVGs (auch repeatable)** | ✅ | ❌ | ❌ |
| **Text-Widgets mit Variablen (Text & RichText)** | ✅ | ⚠️ beschränkt | ⚠️ beschränkt |
| **Diagramme (Bar, Line, Pie)** | ✅ | ✅ | ✅ |
| **Interaktive Tabellen mit Filter/Sortierung/Export** | ✅ | ⚠️ | ✅ |
| **PivotTables (OLAP Cube Visualisierung)** | ✅ | ⚠️ (via Plugin) | ⚠️ (teilweise) |
| **Icons, Bilder & Videos als Widgets** | ✅ | ⚠️ eingeschränkt | ⚠️ |
| **Progressbars & KPI-Gauges** | ✅ | ⚠️ mit Plugin | ⚠️ |
| **Kartenintegration (OGC Maps & Features)** | ✅ | ⚠️ Plugin-abhängig | ⚠️ kaum |
| **MQTT/WebSocket Unterstützung (nativ)** | ✅ | ⚠️ (nur Plugins) | ❌ |
| **SensorThings API (Live, Historie, Stammdaten)** | ✅ | ⚠️ experimentell | ❌ |
| **REST (CSV/JSON/XML)** | ✅ | ✅ | ✅ |
| **SPARQL / RDF / Linked Open Data** | ✅ | ❌ | ⚠️ experimentell |
| **GraphQL (inkl. Subscription geplant)** | ✅ | ⚠️ | ⚠️ |
| **XMLA für OLAP-Cubes** | ✅ | ⚠️ Plugin-abhängig | ⚠️ experimentell |
| **SQL über XMLA mit Rechtemanagement** | ✅ | ❌ | ❌ |
| **Integration von Open Data Registries (DCAT)** | ✅ | ❌ | ❌ |
| **Git-Versionierung für Dashboards** | ✅ | ❌ | ❌ |
| **Datenschutz ohne doppeltes Rechtemanagement** | ✅ | ❌ | ❌ |

------

## 🖼️ Dashboards

- **Pixelgenaue Platzierung**: Jedes Widget kann absolut positioniert werden.
- **Responsives Layout**: Widget-Größen sind fix, aber die Positionierung passt sich an das jeweilige Endgerät an.
- *Komplexe Layouts wie Infografiken oder mehrseitige Reports möglich.*

---

## 🧩 Verfügbare Widgets

### Chart-Widgets
- **Balkendiagramme** (Bar Chart)
- **Liniendiagramme** (Line Chart)
- **Kreisdiagramme** (Pie Chart)
- *Farben, Schatten und Transparenz dynamisch nach Uhrzeit und Variablen steuerbar.*

### Datentabellen
- Sortierung und Filterung pro Spalte
- Paginierung
- Spalten- und Zeilenformatierung
- Hervorhebung (Highlighting)
- Exportfunktionen (z. B. CSV)
- *Flexible Größenanpassung, auch bei vielen Spalten.*

### PivotTable (Excel-ähnlich)
- Auswahl eines OLAP-Cubes
- Frei konfigurierbare Dimensionen (Spalten, Zeilen, Filter)
- Measures (Kennzahlen) dynamisch einsetzbar
- Export der erzeugten Aggregationen
- *Ideal für interaktive BI-Analysen.*

### Icons
- Auswahl aus vordefinierten Symbolkatalogen
- Anpassung von Vorder- und Hintergrundfarben
- *Nutzen von Icons zur semantischen Codierung von Zuständen.*

### Image
- Darstellung von Bildern
- Anwendung von *Bildfiltern wie Kontrast, Helligkeit, Unschärfe etc.*
- *Skalierung und Rahmung frei wählbar.*

### Progress Bars & Gauges
- Visualisierung einfacher Messwerte
- *Darstellung als Tacho, Fortschrittsbalken oder Zahl.*
- *Ideal für KPIs wie Geschwindigkeit, Temperatur, Auslastung.*

### SVG
- Einbettung und Darstellung von SVG-Grafiken
- Farbmanipulation über Variablen
- *Perfekt für stilisierte Icons und Vektorformen.*

### Repeatable SVG
- Wiederholte Darstellung von SVGs anhand numerischer Werte
- Beispiel: 10 Personen als Symbol für einen Zählerstand
- *Beliebige SVGs können verwendet werden, nicht nur Icons.*

### RichText
- Formatierter Text mit Einbettung von Variablen
- Freie Platzierung im Dashboard
- *Einsatz für Überschriften, erklärende Texte oder interaktive Labels.*

### Text
- Schlichter Text ohne Formatierung
- Integration von Variablen (z. B. dynamische Messwerte)
- *Nützlich für einfache Beschriftungen oder Tooltips.*

### Video
- Darstellung von Videos mit oder ohne Steuerungsbuttons
- *Einbettung von Livestreams möglich.*

### Karten (Map)
- Darstellung georeferenzierter Daten
- Integration von:
  - OGC Maps (gerenderte Kartenbilder)
  - OGC Features (Geo-Objekte mit Attributen)
  - SensorThings-Standorten
  - CSV- und CML-Datenquellen
- *Individuelles Styling für verschiedene Sensorarten möglich.*

### SampleWidget
- Platzhalter für zukünftige experimentelle Widgets
- *Erweiterbar durch eigene Definitionen im Code.*

---

## 🔌 Datenverbindungen (Connections)

### OGC Maps
- Einbindung gerenderter Karten (z. B. WMS-Dienste)
- Anzeige in Kartenwidgets

### OGC Features
- Anzeige von Geo-Objekten wie Haltestellen, Gullideckeln, Bäumen etc.
- JSON-basiert
- Mit Geometrie, Name und Stammdaten

### XMLA für Datacubes
- Zugriff auf Datenwürfel über XMLA-Schnittstelle
- Unterstützt Microsoft Analysis Services, Daanse OLAP Server u. a.
- *Kompatibel mit PowerBI und Excel Pivot.*

### SQL über XMLA
- Ausführung von SQL-Statements über XMLA-Protokoll
- Rollenbasiertes Rechtemanagement
- Sicherheitsfunktionen gegen Missbrauch
- *Abfragen sind auditierbar, ideal für offene Plattformen.*

### REST CSV
- REST-Schnittstelle zum Import von CSV-Dateien
- Auswahl von Delimiter
- *Teilweises Einlesen großer Dateien möglich.*

### REST JSON & XML
- Einfache REST-Anbindung für gängige APIs
- Unterstützt JSON und XML
- *Kompatibel mit Open Government APIs, z. B. Mängelmelder, Verkehrsdaten.*

### Semantic Web / SPARQL / RDF
- Zugriff auf Wikidata, DCAT, GovData, Open Energy Platform etc.
- Nutzung semantischer Abfragen über SPARQL
- *Verknüpfung mit Linked Open Data.*

### SensorThings API
- Historische Zeitreihen (z. B. Temperaturverlauf)
- Sensorstammdaten (Typ, Standort, Einheit)
- Live-Daten über REST oder MQTT/Websocket
- *Perfekt für Smart-City-Anwendungen.*

### MQTT (plain)
- Direkte Verbindung zu MQTT-Brokern
- Empfängt Nachrichten bei Wertänderung
- Unterstützt Last-Will-Nachrichten

### WebSocket (plain)
- Direkter Empfang von Nachrichten via WebSocket-Protokoll
- *Verbindung zu Webservern möglich, z. B. bei Custom Events.*

### RSS
- Einbindung strukturierter RSS-Feeds
- Darstellung von Datum, Kurztext, Langtext, Link
- *Ideal für Veranstaltungskalender, Linienänderungen etc.*

### GraphQL
- Moderne, webbasierte Abfragesprache
- Selektives Abfragen und Filtern von Feldern
- *Subscriptions (Live-Daten) in Planung*

---

## 🔁 Variablen

- **Konstanten** (z. B. ID eines Sensors)
- **Berechnete Variablen** (Formeln auf andere Variablen)
- **Zeitbasierte Variablen** (z. B. Sonnenstand, Uhrzeit)
- **Ergebnisse aus Abfragen** (z. B. aktuelle Temperatur)

*Alle Eigenschaften von Widgets und Dashboards sind variablenfähig.*

Beispiel: Eine Schaltfläche wechselt zwischen verschiedenen Objekten, indem eine Variable aktualisiert wird. Alle Datenquellen passen sich automatisch an.

---

## ✨ Besonderheiten

### Kein Server nötig
- Läuft direkt im Browser
- Kann als PWA oder native Desktop-App (macOS, Windows, Linux) genutzt werden
- *Kein Backend, keine Serverkosten, volle Datensouveränität*

### Datenschutz & Rechte
- Keine Speicherung oder Vorhaltung von Daten
- Kein zweites Rechtemanagement notwendig
- *Vermeidung von Superuser-Konfigurationen wie in Grafana/Superset*

### DCAT/OpenData-Integration
- Direkte Abfrage von Datensätzen & Diensten aus [data.europa.eu](https://data.europa.eu), [GovData.de](https://www.govdata.de)
- *Sofortige Visualisierung ohne technische Konfiguration*
- *Empfohlene Widgets werden vorgeschlagen*

### Datenfusion in Dashboard & Widgets
- Kombination unterschiedlicher Datenquellen in einem Dashboard (z. B. Live-Sensorik + Geodaten + Statistik)
- Kombination in einem Widget (z. B. Karte mit Live- & historischen Daten, Tabelle mit CSV + SQL + GraphQL)

### Git-Integration
- Dashboards versionierbar und nachvollziehbar
- Unterschiedliche Varianten möglich (z. B. Fraktionen im Stadtrat)
- *Änderungen sind dokumentiert und auditierbar*

---

## 🔧 Geplante Erweiterungen

- Prometheus/PromQL-Support
- Elasticsearch/OpenSearch Integration
- KPI-Widgets
- *Template-System für vordefinierte Dashboards*
- *Modellbasierter Editor mit Drag-and-Drop*


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

## 🖼️ Dashboards

- **Pixelgenaue Platzierung**: Jedes Widget kann absolut positioniert werden.
- **Responsives Layout**: Widget-Größen sind fix, aber die Positionierung passt sich an das jeweilige Endgerät an.
- *Komplexe Layouts wie Infografiken oder mehrseitige Reports möglich.*

---

## 🧩 Verfügbare Widgets

### Chart-Widgets
- **Balkendiagramme** (Bar Chart)
- **Liniendiagramme** (Line Chart)
- **Kreisdiagramme** (Pie Chart)
- *Farben, Schatten und Transparenz dynamisch nach Uhrzeit und Variablen steuerbar.*

### Datentabellen
- Sortierung und Filterung pro Spalte
- Paginierung
- Spalten- und Zeilenformatierung
- Hervorhebung (Highlighting)
- Exportfunktionen (z. B. CSV)
- *Flexible Größenanpassung, auch bei vielen Spalten.*

### PivotTable (Excel-ähnlich)
- Auswahl eines OLAP-Cubes
- Frei konfigurierbare Dimensionen (Spalten, Zeilen, Filter)
- Measures (Kennzahlen) dynamisch einsetzbar
- Export der erzeugten Aggregationen
- *Ideal für interaktive BI-Analysen.*

### Icons
- Auswahl aus vordefinierten Symbolkatalogen
- Anpassung von Vorder- und Hintergrundfarben
- *Nutzen von Icons zur semantischen Codierung von Zuständen.*

### Image
- Darstellung von Bildern
- Anwendung von *Bildfiltern wie Kontrast, Helligkeit, Unschärfe etc.*
- *Skalierung und Rahmung frei wählbar.*

### Progress Bars & Gauges
- Visualisierung einfacher Messwerte
- *Darstellung als Tacho, Fortschrittsbalken oder Zahl.*
- *Ideal für KPIs wie Geschwindigkeit, Temperatur, Auslastung.*

### SVG
- Einbettung und Darstellung von SVG-Grafiken
- Farbmanipulation über Variablen
- *Perfekt für stilisierte Icons und Vektorformen.*

### Repeatable SVG
- Wiederholte Darstellung von SVGs anhand numerischer Werte
- Beispiel: 10 Personen als Symbol für einen Zählerstand
- *Beliebige SVGs können verwendet werden, nicht nur Icons.*

### RichText
- Formatierter Text mit Einbettung von Variablen
- Freie Platzierung im Dashboard
- *Einsatz für Überschriften, erklärende Texte oder interaktive Labels.*

### Text
- Schlichter Text ohne Formatierung
- Integration von Variablen (z. B. dynamische Messwerte)
- *Nützlich für einfache Beschriftungen oder Tooltips.*

### Video
- Darstellung von Videos mit oder ohne Steuerungsbuttons
- *Einbettung von Livestreams möglich.*

### Karten (Map)
- Darstellung georeferenzierter Daten
- Integration von:
  - OGC Maps (gerenderte Kartenbilder)
  - OGC Features (Geo-Objekte mit Attributen)
  - SensorThings-Standorten
  - CSV- und CML-Datenquellen
- *Individuelles Styling für verschiedene Sensorarten möglich.*

### SampleWidget
- Platzhalter für zukünftige experimentelle Widgets
- *Erweiterbar durch eigene Definitionen im Code.*

---

## 🔌 Datenverbindungen (Connections)

### OGC Maps
- Einbindung gerenderter Karten (z. B. WMS-Dienste)
- Anzeige in Kartenwidgets

### OGC Features
- Anzeige von Geo-Objekten wie Haltestellen, Gullideckeln, Bäumen etc.
- JSON-basiert
- Mit Geometrie, Name und Stammdaten

### XMLA für Datacubes
- Zugriff auf Datenwürfel über XMLA-Schnittstelle
- Unterstützt Microsoft Analysis Services, Daanse OLAP Server u. a.
- *Kompatibel mit PowerBI und Excel Pivot.*

### SQL über XMLA
- Ausführung von SQL-Statements über XMLA-Protokoll
- Rollenbasiertes Rechtemanagement
- Sicherheitsfunktionen gegen Missbrauch
- *Abfragen sind auditierbar, ideal für offene Plattformen.*

### REST CSV
- REST-Schnittstelle zum Import von CSV-Dateien
- Auswahl von Delimiter
- *Teilweises Einlesen großer Dateien möglich.*

### REST JSON & XML
- Einfache REST-Anbindung für gängige APIs
- Unterstützt JSON und XML
- *Kompatibel mit Open Government APIs, z. B. Mängelmelder, Verkehrsdaten.*

### Semantic Web / SPARQL / RDF
- Zugriff auf Wikidata, DCAT, GovData, Open Energy Platform etc.
- Nutzung semantischer Abfragen über SPARQL
- *Verknüpfung mit Linked Open Data.*

### SensorThings API
- Historische Zeitreihen (z. B. Temperaturverlauf)
- Sensorstammdaten (Typ, Standort, Einheit)
- Live-Daten über REST oder MQTT/Websocket
- *Perfekt für Smart-City-Anwendungen.*

### MQTT (plain)
- Direkte Verbindung zu MQTT-Brokern
- Empfängt Nachrichten bei Wertänderung
- Unterstützt Last-Will-Nachrichten

### WebSocket (plain)
- Direkter Empfang von Nachrichten via WebSocket-Protokoll
- *Verbindung zu Webservern möglich, z. B. bei Custom Events.*

### RSS
- Einbindung strukturierter RSS-Feeds
- Darstellung von Datum, Kurztext, Langtext, Link
- *Ideal für Veranstaltungskalender, Linienänderungen etc.*

### GraphQL
- Moderne, webbasierte Abfragesprache
- Selektives Abfragen und Filtern von Feldern
- *Subscriptions (Live-Daten) in Planung*

---

## 🔁 Variablen

- **Konstanten** (z. B. ID eines Sensors)
- **Berechnete Variablen** (Formeln auf andere Variablen)
- **Zeitbasierte Variablen** (z. B. Sonnenstand, Uhrzeit)
- **Ergebnisse aus Abfragen** (z. B. aktuelle Temperatur)

*Alle Eigenschaften von Widgets und Dashboards sind variablenfähig.*

Beispiel: Eine Schaltfläche wechselt zwischen verschiedenen Objekten, indem eine Variable aktualisiert wird. Alle Datenquellen passen sich automatisch an.

---

## ✨ Besonderheiten

### Kein Server nötig
- Läuft direkt im Browser
- Kann als PWA oder native Desktop-App (macOS, Windows, Linux) genutzt werden
- *Kein Backend, keine Serverkosten, volle Datensouveränität*

### Datenschutz & Rechte
- Keine Speicherung oder Vorhaltung von Daten
- Kein zweites Rechtemanagement notwendig
- *Vermeidung von Superuser-Konfigurationen wie in Grafana/Superset*

### DCAT/OpenData-Integration
- Direkte Abfrage von Datensätzen & Diensten aus [data.europa.eu](https://data.europa.eu), [GovData.de](https://www.govdata.de)
- *Sofortige Visualisierung ohne technische Konfiguration*
- *Empfohlene Widgets werden vorgeschlagen*

### Datenfusion in Dashboard & Widgets
- Kombination unterschiedlicher Datenquellen in einem Dashboard (z. B. Live-Sensorik + Geodaten + Statistik)
- Kombination in einem Widget (z. B. Karte mit Live- & historischen Daten, Tabelle mit CSV + SQL + GraphQL)

### Git-Integration
- Dashboards versionierbar und nachvollziehbar
- Unterschiedliche Varianten möglich (z. B. Fraktionen im Stadtrat)
- *Änderungen sind dokumentiert und auditierbar*

---

## 🔧 Geplante Erweiterungen

- Prometheus/PromQL-Support
- Elasticsearch/OpenSearch Integration
- KPI-Widgets
- *Template-System für vordefinierte Dashboards*
- *Modellbasierter Editor mit Drag-and-Drop*

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
