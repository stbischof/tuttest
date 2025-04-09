# Eclipse Daanse – Die neue Generation datengetriebener Dashboards

Eclipse Daanse ist ein vollständig clientseitiger Dashboard-Editor und Viewer, der speziell für die moderne Verwaltung, Analyse und Visualisierung heterogener Datenquellen entwickelt wurde. Im Gegensatz zu klassischen Lösungen wie **Grafana** oder **Apache Superset** verfolgt Daanse einen konsequenten *No-Server-Ansatz*, was insbesondere im Bereich *Open Data* und *Smart City* neue Maßstäbe setzt.

---

## 🆚 Vergleich Eclipse Daanse vs. Grafana vs. Apache Superset

| Merkmal | Eclipse Daanse | Grafana | Apache Superset |
|--------|----------------|---------|------------------|
| **Open Source** | ✅ | ✅ | ✅ |
| **Server notwendig** | ❌ | ✅ | ✅ |
| **Datenverarbeitung im Browser (Client only)** | ✅ | ❌ | ❌ |
| **Granulare Widgetgestaltung | ✅ pixelgenau & responsive | ⚠️ begrenzt | ⚠️ begrenzt |
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
| **Direkte Nutzung offener Schnittstellen | ✅ | ⚠️ oft nur mit eigenem Backend | ⚠️ teilweise |
| **SensorThings API (Live, Historie, Stammdaten)** | ✅ | ⚠️ experimentell | ❌ |
| **REST (CSV/JSON/XML)** | ✅ | ✅ | ✅ |
| **SPARQL / RDF / Linked Open Data** | ✅ | ❌ | ⚠️ experimentell |
| **GraphQL (inkl. Subscription geplant)** | ✅ | ⚠️ | ⚠️ |
| **XMLA für OLAP-Cubes** | ✅ | ⚠️ Plugin-abhängig | ⚠️ experimentell |
| **SQL über XMLA mit Rechtemanagement** | ✅ | ❌ | ❌ |
| **Integration von Open Data Registries (DCAT)** | ✅ | ❌ | ❌ |
| **Git-Versionierung für Dashboards** | ✅ | ❌ | ❌ |
| **Datenschutz ohne doppeltes Rechtemanagement** | ✅ | ❌ | ❌ |
| *Open Data Registry Integration (DCAT)* | ✅ | ❌ | ❌ |

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
- Beliebige SVGs können verwendet werden, nicht nur Icons.
- einfache Darstellung von Mengeverhältnissen oder Skalen (Bewertung 3 von 5 Sternen)

### RichText
- Formatierter Text mit Einbettung von Variablen
- Freie Platzierung im Dashboard
- *Einsatz für Überschriften, erklärende Texte oder interaktive Labels.*

### Text
- Schlichter Text ohne Formatierung
- Integration von Variablen (z. B. dynamische Messwerte)
- Nützlich für einfache Beschriftungen

### Video
- Darstellung von Videos mit oder ohne Steuerungsbuttons
- Einbettung von Livestreams möglich

### Karten (Map)
- Darstellung georeferenzierter Daten
- Integration von:
  - OGC Maps (gerenderte Kartenbilder)
  - OGC Features (Geo-Objekte mit Attributen)
  - SensorThings-Standorten
  - CSV- und CML-Datenquellen
- Individuelles Styling für alle Layer (Färbung, Transpartenz, Icons, Linien, Flächen, Sensorwerte)
- alle Layer gemeinsam darstellbar

### SampleWidget
- Platzhalter für zukünftige experimentelle Widgets

---

## 🔌 Datenverbindungen (Connections)

### OGC Maps
- Einbindung gerenderter Karten (z. B. WMS-Dienste)
- Anzeige in Kartenwidgets

### OGC Features
- Anzeige von Geo-Objekten wie Haltestellen, Gullideckeln, Bäumen etc.
- JSON-basiert
- Mit Geometrie, Name und Stammdaten

### SensorThings API
- Historische Zeitreihen (z. B. Temperaturverlauf)
- Sensorstammdaten (Typ, Standort, Einheit)
- Live-Daten über REST oder MQTT/Websocket
- *Perfekt für Smart-City-Anwendungen.*

### XMLA für Datacubes
- Zugriff auf Datenwürfel über XMLA-Schnittstelle
- Unterstützt Microsoft Analysis Services, Daanse OLAP Server u. a.
- Kompatibel mit PowerBI und Excel Pivot.

### SQL über XMLA
- Ausführung von SQL-Statements über XMLA-Protokoll
- Rollenbasiertes Rechtemanagement
- Sicherheitsfunktionen gegen Missbrauch


### REST CSV
- REST-Schnittstelle zum Import von CSV-Dateien
- Auswahl von Delimiter
- Teilweises Einlesen großer Dateien möglich (Bereiche)

### REST JSON & XML
- Einfache REST-Anbindung für gängige APIs
- Unterstützt JSON und XML
- Kompatibel mit Open Government APIs, z. B. Mängelmelder, Verkehrsdaten.

### Semantic Web / SPARQL / RDF
- Zugriff auf Wikidata, DCAT, GovData, Open Energy Platform etc.
- Nutzung semantischer Abfragen über SPARQL
- Verknüpfung mit Linked Open Data.

### MQTT (plain)
- Direkte Verbindung zu MQTT-Brokern
- Empfängt Nachrichten bei Wertänderung
- Unterstützt Last-Will-Nachrichten

### WebSocket (plain)
- Direkter Empfang von Nachrichten via WebSocket-Protokoll
- Verbindung zu Webservern möglich, z. B. bei Custom Events.

### RSS
- Einbindung strukturierter RSS-Feeds
- Darstellung von Datum, Kurztext, Langtext, Link
- Ideal für Veranstaltungskalender, Fahrplanänderungen etc.

### GraphQL
- Moderne, webbasierte Abfragesprache
- Selektives Abfragen und Filtern von Feldern
- Subscriptions (Live-Daten)

---

## 🔁 Variablen

- **Konstanten** (z. B. ID eines Sensors)
- **Berechnete Variablen** (Formeln auf andere Variablen)
- **Zeitbasierte Variablen** (z. B. Sonnenstand, Uhrzeit)
- **Ergebnisse aus Abfragen** (z. B. aktuelle Temperatur)

Alle Eigenschaften von Widgets und Dashboards sind variablenfähig.

Beispiel: Eine Schaltfläche wechselt zwischen verschiedenen Objekten, indem eine Variable aktualisiert wird. Alle Datenquellen passen sich automatisch an.

---

## ✨ Besonderheiten

### Kein Server nötig
- Läuft direkt im Browser
- Kann als PWA oder native Desktop-App (macOS, Windows, Linux) genutzt werden ()
- Kein Backend, keine Serverkosten, volle Datensouveränität

### Datenschutz & Rechte
- Keine Speicherung oder Vorhaltung von Daten
- Kein zweites Rechtemanagement notwendig
- Vermeidung von Superuser-Konfigurationen wie in Grafana/Superset
- Abfragen sind transparent, ideal für offene Plattformen.

Die Daten werden direkt im Browser geladen und dargestellt. Es ist kein zusätzlicher Server notwendig, der die Daten liest oder zwischen­speichert.
Das ist besonders vorteilhaft bei Open-Data- oder Urban-Data-Plattformen, die ihre Daten über dedizierte Schnittstellen (APIs) bereitstellen. Durch den direkten Zugriff entfällt eine doppelte Speicherung, und es wird kein zusätzliches Rechtemanagement eingeführt.
Bei serverbasierten Anwendungen wie Superset oder Grafana wird häufig ein Nutzer angelegt, der über die API mit vollen Rechten auf alle Daten zugreift. Um anschließend die Sicht auf die Daten einzuschränken, wird ein separates Rechtemanagement innerhalb der Anwendung aufgebaut.
Dieses Rechtemanagement unterscheidet sich jedoch vom ursprünglichen der API. Dadurch entsteht ein erhebliches Risiko: Der Nutzer, der die serverbetriebene Dashboard-Lösung verwendet, hat unter Umständen mehr Rechte, als er bei einem direkten Zugriff auf die API hätte.


### DCAT/OpenData-Integration
- Direkte Abfrage von Datensätzen & Diensten aus [data.europa.eu](https://data.europa.eu), [GovData.de](https://www.govdata.de)
- Sofortige Visualisierung ohne technische Konfiguration
- Empfohlene Widgets werden vorgeschlagen

### Datenfusion in Dashboard & Widgets
- Kombination unterschiedlicher Datenquellen in einem Dashboard (z. B. Live-Sensorik + Geodaten + Statistik)
- Kombination in einem Widget (z. B. Karte mit Live- & historischen Daten, Tabelle mit CSV + SQL + GraphQL)

### Git-Integration
- Dashboards versionierbar und nachvollziehbar
- Unterschiedliche Varianten möglich (z. B. Fraktionen im Stadtrat)
- *Änderungen sind dokumentiert und auditierbar*


Alle Daten können transparent angezeigt werden, während Dashboards zum selben Thema und mit denselben Datenquellen individuell gestaltet werden können.
So kann beispielsweise jede Fraktion eines Stadtrats ihr eigenes Dashboard erstellen und dabei eine eigene inhaltliche Perspektive („Framing“) wählen – ohne dass sich die zugrundeliegenden Daten unterscheiden. Für die Nutzer bleibt stets nachvollziehbar, was die originalen Daten sind und worin sich die verschiedenen Darstellungen der Fraktionen unterscheiden.

Änderungen an Dashboards sind stets nachvollziehbar und auditierbar: Es lässt sich jederzeit nachvollziehen, wer wann was geändert hat. Zudem können Änderungen begründet und dokumentiert werden.

---

## 🔧 Geplante Erweiterungen

- Prometheus/PromQL-Support
- Elasticsearch/OpenSearch Integration
- KPI-Widgets
- Template-System für vordefinierte Dashboards
- Modellbasierter Editor mit Drag-and-Drop
- Bericht-Generierung

---

## 🚀 Fazit

**Eclipse Daanse** ist keine bloße Dashboard-Alternative, sondern ein **komplett neu gedachtes Visualisierungs-Framework**, das alle Anforderungen moderner Datenplattformen – insbesondere im Open- und Urban-Data-Kontext – erfüllt:

- **Datenschutzkonform**, **granular**, **hochflexibel**, **vollständig clientbasiert**.
- Kein Vendor-Lock-In, keine Serverkosten, volle Kontrolle.

> *Wer Open Data wirklich offen nutzen will, braucht eine Lösung wie Daanse.*

----

