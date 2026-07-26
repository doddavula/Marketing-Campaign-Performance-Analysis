# Marketing Campaign Analytics
## Projektübersicht
Dieses Projekt ist eine End-to-End-Analyse von Marketingkampagnendaten mit Python, Pandas, NumPy, Power BI und DAX.
Ziel des Projekts ist es, die Performance von Marketingkampagnen zu analysieren und datenbasierte Erkenntnisse für die Optimierung von Marketingmaßnahmen zu gewinnen.
Die Analyse umfasst:
-	Marketingkanäle
-	Regionen
-	Produkte
-	Zeitperioden
-	Impressions
-	Clicks
- Conversions
-	Marketingausgaben
-	Revenue
- CTR
-	Conversion Rate
-	ROI
  
 Der gesamte Workflow reicht von der Datenaufbereitung mit Python bis zur Entwicklung interaktiver Power-BI-Dashboards.

 ---

 ## End-to-End-Workflow

 **Rohdaten**<br>
       ↓<br>       
 **Python / Pandas / NumPy**<br>
       ↓<br> 
 **Datenbereinigung**<br>
       ↓<br>      
 **Datenqualitätsprüfung**<br>
       ↓<br>   
 **Aufbereitete CSV-Dateien**<br>
       ↓<br>  
 **Power-BI-Datenmodell**<br>
       ↓<br>
 **Star Schema**<br>
       ↓<br>    
 **DAX-Kennzahlen**<br>
       ↓<br>   
 **Interaktive Dashboards**<br>
       ↓<br>   
 **Business Insights**

 ---

 ## Business Problem

 Marketingteams investieren Budgets in verschiedene Marketingkanäle und Kampagnen.
Die Rohdaten zeigen jedoch nicht direkt:

- Welcher Marketingkanal den höchsten Umsatz erzielt
-	Welcher Kanal die beste CTR aufweist
-	Welche Kampagnen die meisten Conversions generieren
-	Welche Regionen die beste Performance zeigen
-	Welche Produkte den höchsten Umsatz erzielen
-	Wie effizient das Marketingbudget eingesetzt wird
-	Wie hoch der Return on Investment ist

Dieses Projekt analysiert diese Fragestellungen mit Python und Power BI.

---

## Datenaufbereitung mit Python

Die Daten wurden mit Python und Pandas aufbereitet und für die Analyse vorbereitet.
Durchgeführte Schritte

-	Einlesen der Rohdaten
-	Untersuchung der Datenstruktur
-	Prüfung der Datentypen
-	Überprüfung fehlender Werte
-	Entfernung von Duplikaten
-	Bereinigung von Textfeldern
-	Erstellung und Prüfung berechneter Kennzahlen
-	Datenqualitätsprüfung
-	Vorbereitung der CSV-Dateien für Power BI

NumPy
NumPy wurde für numerische Berechnungen und die Generierung realistischer synthetischer Marketingdaten verwendet.
Beispiel:
df["Revenue"] = df["Spend"] * np.random.uniform(2.0, 5.0)

Dadurch wird für jede Zeile ein realistischer Umsatzmultiplikator zwischen 2,0 und 5,0 generiert.

## Datensatz

Für das Projekt wurde ein synthetischer Marketingdatensatz mit ungefähr 100.000 Datensätzen verwendet.

Der Datensatz enthält unter anderem:

Datum
Marketingkanal
Region
Produkt
Impressions
Clicks
Conversions
Spend
Revenue

Die Daten wurden so vorbereitet, dass sie realistische Marketingkennzahlen und Business-Szenarien abbilden.

✅ Datenqualitätsprüfung

Vor der Analyse wurden verschiedene Business Rules überprüft.

Clicks dürfen nicht größer als Impressions sein

Business Rule:

Clicks ≤ Impressions

Conversions dürfen nicht größer als Clicks sein

Business Rule:

Conversions ≤ Clicks

Marketingausgaben dürfen nicht negativ sein

Business Rule:

Spend ≥ 0

Umsatz darf nicht negativ sein

Business Rule:

Revenue ≥ 0

Diese Prüfungen stellen sicher, dass die Daten logisch und analytisch verwendbar sind.

⭐ Power-BI-Datenmodell

Das Datenmodell wurde als Star Schema aufgebaut.

Faktentabelle
Fact_Marketing

Die zentrale Faktentabelle enthält die messbaren Marketingkennzahlen:

Date
Impressions
Clicks
Conversions
Spend
Revenue
Dimensionstabellen
Dim_Date
Date
Year
Month
Month Name
Year Month
Dim_Channel
Marketing Channel
Dim_Region
Region
Dim_Product
Product

Das Star Schema ermöglicht eine strukturierte und flexible Analyse der Marketingperformance.

🧮 DAX-Kennzahlen
Total Spend
Total Spend =
SUM(Fact_Marketing[Spend])
Total Revenue
Total Revenue =
SUM(Fact_Marketing[Revenue])
Total Clicks
Total Clicks =
SUM(Fact_Marketing[Clicks])
Total Conversions
Total Conversions =
SUM(Fact_Marketing[Conversions])
📈 CTR – Click-Through Rate
Formel

CTR = Clicks ÷ Impressions

CTR =
DIVIDE(
    [Total Clicks],
    [Total Impressions],
    0
)

Die CTR zeigt den Anteil der Impressions, die zu einem Klick geführt haben.

🔄 Conversion Rate
Formel

Conversion Rate = Conversions ÷ Clicks

Conversion Rate =
DIVIDE(
    [Total Conversions],
    [Total Clicks],
    0
)

Die Conversion Rate zeigt, wie viele Klicks zu einer Conversion geführt haben.

💰 ROI – Return on Investment
Formel

ROI = (Revenue − Spend) ÷ Spend

ROI =
DIVIDE(
    [Total Revenue] - [Total Spend],
    [Total Spend],
    0
)

Der ROI zeigt die Effizienz der Marketinginvestitionen.

Die Kennzahl wird im Dashboard als Prozentwert dargestellt.

💵 CPC – Cost per Click
Formel

CPC = Spend ÷ Clicks

CPC =
DIVIDE(
    [Total Spend],
    [Total Clicks],
    0
)

Der CPC zeigt die durchschnittlichen Kosten pro Klick.

💳 CPA – Cost per Acquisition
Formel

CPA = Spend ÷ Conversions

CPA =
DIVIDE(
    [Total Spend],
    [Total Conversions],
    0
)

Der CPA zeigt die durchschnittlichen Kosten pro Conversion.

📊 Power-BI-Dashboard

Das Power-BI-Reporting besteht aus drei Seiten.

## 1️⃣ Marketing Campaign Performance Overview

Die erste Seite bietet einen Überblick über die gesamte Marketingperformance.

- KPIs
- Total Spend
- Total Revenue
- Total Conversions
- CTR
- ROI
- Visualisierungen
- Monthly Revenue Trend
- Total Revenue by Marketing Channel
- Conversions by Region
### Filter
- Year
- Product
- Region
- Marketing Channel


## 2️⃣ Channel & Campaign Performance

Die zweite Seite analysiert die Performance der Marketingkanäle.

### KPIs

- Total Spend
- Total Revenue
- Total Clicks
- Total Conversions
- CTR

### Visualisierungen

- Marketing Spend by Channel
- Total Revenue by Marketing Channel
- CTR by Marketing Channel
- Conversion Rate by Marketing Channel

### Zusätzliche Analyse

Eine Performance-Tabelle ermöglicht die Analyse von:

- Total Spend
- Total Revenue
- Total Clicks
- Total Conversions
- CTR
- Conversion Rate
- ROI


## 3️⃣ Regional & Product Performance Overview

Die dritte Seite analysiert die Performance nach Region und Produkt.

### KPIs

- Total Revenue
- Total Conversions
- ROI

### Visualisierungen

- Revenue by Region
- Revenue by Product
- Conversions by Region
- Conversions by Product

### Performance Matrix

Die Matrix ermöglicht einen detaillierten Vergleich von:

- Region
- Produkt
- Total Revenue
- Total Conversions
- ROI


## Interaktive Filter

Die Dashboards ermöglichen eine interaktive Analyse der Daten.

Verwendete Filter:

Year
Region
Product
Marketing Channel

Die Filter ermöglichen es, die KPIs und Visualisierungen dynamisch nach verschiedenen Dimensionen zu analysieren.

## Business Insights

Das Dashboard unterstützt die Beantwortung folgender Fragen:

- Welcher Marketingkanal erzielt den höchsten Umsatz?
- Welcher Kanal erzielt die höchsten Marketingausgaben?
- Welcher Kanal hat die beste CTR?
- Welcher Kanal erzielt die beste Conversion Rate?
- Welche Region generiert die meisten Conversions?
- Welches Produkt erzielt den höchsten Umsatz?
- Welche Kombination aus Region und Produkt ist besonders erfolgreich?
- Welche Marketinginvestitionen erzielen den höchsten ROI?
## Verwendete Technologien

- Technologie	Verwendung
- Python	Datenaufbereitung
- Pandas	Datenbereinigung und Transformation
- NumPy	Numerische Berechnungen und synthetische Datengenerierung
- Jupyter Notebook	Analyse und Entwicklung
- Power BI	Datenmodellierung und Visualisierung
- DAX	Erstellung dynamischer KPIs
- CSV	Datenaustausch
## Gezeigte Kompetenzen
- Datenbereinigung
- Datenqualitätsprüfung
- Explorative Datenanalyse
- Python
- Pandas
- NumPy
- Power BI
- DAX
- Datenmodellierung
- Star Schema
- KPI-Entwicklung
- Datenvisualisierung
- Marketing Analytics
- Business Intelligence
- Datenbasierte Entscheidungsunterstützung






