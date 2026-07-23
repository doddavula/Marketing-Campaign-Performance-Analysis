# 📊 Marketing Campaign Analytics

## 📌 Projektübersicht

Dieses Projekt ist eine End-to-End-Analyse von Marketingkampagnendaten mit **Python, Pandas, NumPy, Power BI und DAX**.

Ziel des Projekts ist die Analyse der Kampagnenperformance nach:

- Marketingkanal
- Region
- Produkt
- Kampagne
- Zeitraum

Der gesamte Analyseprozess umfasst die Datenaufbereitung in Python, die Datenqualitätsprüfung, die Modellierung in Power BI, die Erstellung dynamischer DAX-Kennzahlen und die Entwicklung interaktiver Dashboards.

---

## 🔄 End-to-End-Workflow

```text
Rohdaten
   ↓
Python / Pandas
   ↓
Datenbereinigung
   ↓
Datenqualitätsprüfung
   ↓
Aufbereitete CSV-Dateien
   ↓
Power-BI-Datenmodell
   ↓
Star-Schema
   ↓
DAX-Kennzahlen
   ↓
Interaktives Dashboard
   ↓
Business Insights
________________________________________
🎯 Business Problem
Marketingteams investieren Budgets in verschiedene Kampagnen und Marketingkanäle. Rohdaten zeigen jedoch nicht immer direkt:
•	Welcher Marketingkanal den höchsten Umsatz erzielt 
•	Welcher Kanal die beste CTR aufweist 
•	Welche Kampagnen die meisten Conversions generieren 
•	Welche Regionen die beste Performance zeigen 
•	Welche Produkte den höchsten Umsatz erzielen 
•	Wie effizient das Marketingbudget eingesetzt wird 
•	Wie hoch der Return on Investment ist 
Dieses Projekt beantwortet diese Fragen mithilfe von Datenanalyse und Business Intelligence.
________________________________________
🐍 Python-Datenaufbereitung
Python und Pandas wurden verwendet für:
•	Einlesen der Rohdaten 
•	Untersuchung des Datensatzes 
•	Prüfung der Datentypen 
•	Behandlung fehlender Werte 
•	Entfernung von Duplikaten 
•	Bereinigung von Textfeldern 
•	Datenqualitätsprüfung 
•	Vorbereitung der Daten für Power BI 
Verwendete Technologien
Python
Pandas
NumPy
Jupyter Notebook
________________________________________
✅ Datenqualitätsprüfung
Es wurden verschiedene Business Rules überprüft.
Klicks dürfen nicht größer als Impressions sein
invalid_clicks = df[
    df["Clicks"] > df["Impressions"]
]
Business Rule:
Clicks ≤ Impressions
Conversions dürfen nicht größer als Klicks sein
invalid_conversions = df[
    df["Conversions"] > df["Clicks"]
]
Business Rule:
Conversions ≤ Clicks
Negative Ausgaben prüfen
invalid_spend = df[
    df["Spend"] < 0
]
Business Rule:
Spend ≥ 0
Negative Umsätze prüfen
invalid_revenue = df[
    df["Revenue"] < 0
]
Business Rule:
Revenue ≥ 0
________________________________________
⭐ Power-BI-Datenmodell
Das Datenmodell wurde als Star Schema aufgebaut.
                 Dim_Date
                    │
                    │
Dim_Channel ─── Fact_Marketing ─── Dim_Product
                    │
                    │
                Dim_Region
Faktentabelle
Fact_Marketing
Enthält messbare Marketingkennzahlen:
•	Campaign_ID 
•	Date 
•	Impressions 
•	Clicks 
•	Conversions 
•	Spend 
•	Revenue 
Dimensionstabellen
Dim_Date
•	Date 
•	Year 
•	Month 
•	Month Name 
•	Year Month 
Dim_Channel
•	Marketing Channel 
Dim_Region
•	Region 
Dim_Product
•	Product 
________________________________________
🧮 DAX-Kennzahlen
Total Impressions
Total Impressions =
SUM(
    Fact_Marketing[Impressions]
)
Total Clicks
Total Clicks =
SUM(
    Fact_Marketing[Clicks]
)
Total Conversions
Total Conversions =
SUM(
    Fact_Marketing[Conversions]
)
Total Spend
Total Spend =
SUM(
    Fact_Marketing[Spend]
)
Total Revenue
Total Revenue =
SUM(
    Fact_Marketing[Revenue]
)
________________________________________
📈 CTR – Click-Through-Rate
Formel
CTR = Clicks ÷ Impressions
DAX
CTR =
DIVIDE(
    [Total Clicks],
    [Total Impressions],
    0
)
Die CTR zeigt den prozentualen Anteil der Impressions, die zu einem Klick geführt haben.
________________________________________
🔄 Conversion Rate
Formel
Conversion Rate =
Conversions ÷ Clicks
DAX
Conversion Rate =
DIVIDE(
    [Total Conversions],
    [Total Clicks],
    0
)
Die Conversion Rate zeigt, wie viele Klicks zu einer Conversion geführt haben.
________________________________________
💰 ROI – Return on Investment
Formel
ROI =
(Revenue - Spend) ÷ Spend
DAX
ROI =
DIVIDE(
    [Total Revenue] - [Total Spend],
    [Total Spend],
    0
)
Der ROI zeigt den erzielten Ertrag im Verhältnis zur Marketinginvestition.
________________________________________
📊 Power-BI-Dashboard
1️⃣ Executive Overview
Die erste Seite bietet einen Überblick über die gesamte Marketingperformance.
KPIs
•	Total Spend 
•	Total Revenue 
•	Total Conversions 
•	CTR 
•	ROI 
Visualisierungen
•	Monthly Revenue Trend 
•	Revenue by Marketing Channel 
•	Conversions by Region 
Filter
•	Year 
•	Region 
•	Product 
•	Marketing Channel 
________________________________________
📸 Dashboard – Executive Overview
________________________________________
2️⃣ Channel & Campaign Performance
Diese Seite analysiert die Performance nach Marketingkanal und Kampagne.
Analysen
•	Marketing Spend by Channel 
•	Revenue by Channel 
•	CTR by Channel 
•	Conversion Rate by Channel 
•	Campaign Performance 
________________________________________
📸 Dashboard – Channel & Campaign Performance
________________________________________
3️⃣ Regional & Product Performance
Diese Seite analysiert die Performance nach Region und Produkt.
Visualisierungen
•	Revenue by Region 
•	Revenue by Product 
•	Conversions by Region 
•	Conversions by Product 
•	Product and Region Matrix 
Filter
•	Year 
•	Region 
•	Product 
•	Marketing Channel 
________________________________________
📸 Dashboard – Regional & Product Performance
________________________________________
💡 Business Insights
Das Dashboard unterstützt die Beantwortung folgender Fragen:
•	Welcher Marketingkanal erzielt den höchsten Umsatz? 
•	Welcher Kanal hat die beste CTR? 
•	Welche Kampagne generiert die meisten Conversions? 
•	Welche Region erzielt die beste Performance? 
•	Welches Produkt erzielt den höchsten Umsatz? 
•	Welche Kanäle haben den besten ROI? 
•	Welche Kampagnen sollten optimiert werden? 
________________________________________
💼 Interview-Zusammenfassung
Ich habe ein End-to-End-Projekt zur Analyse von Marketingkampagnen mit Python, Pandas, Power BI und DAX entwickelt.
Zunächst habe ich die Marketingdaten mit Python und Pandas aufbereitet und Datenqualitätsprüfungen durchgeführt. Dabei wurden unter anderem Business Rules überprüft, beispielsweise dass die Anzahl der Klicks nicht größer als die Anzahl der Impressions und die Anzahl der Conversions nicht größer als die Anzahl der Klicks sein darf.
Anschließend habe ich in Power BI ein Star-Schema mit einer zentralen Faktentabelle und Dimensionstabellen für Datum, Marketingkanal, Region und Produkt erstellt.
Mit DAX habe ich dynamische Kennzahlen wie Total Spend, Total Revenue, CTR, Conversion Rate, CPC, CPA und ROI erstellt.
Abschließend habe ich ein interaktives Power-BI-Dashboard mit drei Seiten entwickelt:
1.	Executive Overview 
2.	Channel & Campaign Performance 
3.	Regional & Product Performance 
Die interaktiven Filter ermöglichen eine dynamische Analyse der Kampagnenperformance und unterstützen datenbasierte Entscheidungen zur Optimierung von Marketingkampagnen.
________________________________________
🛠️ Technologien
Technologie	Verwendung
Python	Datenaufbereitung
Pandas	Datenbereinigung und Transformation
NumPy	Numerische Berechnungen
Power BI	Datenvisualisierung
DAX	Dynamische Kennzahlen
Excel	Quelldaten
CSV	Datenaustausch
________________________________________
🎓 Gezeigte Kompetenzen
•	Datenbereinigung 
•	Datenqualitätsprüfung 
•	Explorative Datenanalyse 
•	Python 
•	Pandas 
•	NumPy 
•	Power BI 
•	DAX 
•	Datenmodellierung 
•	Star Schema 
•	KPI-Entwicklung 
•	Datenvisualisierung 
•	Business Analysis 
•	Marketing Analytics 
________________________________________
📁 Projektdateien
•	Python-Skript zur Datenaufbereitung 
•	Jupyter Notebook 
•	Aufbereitete CSV-Dateien 
•	Power-BI-Datenmodell 
•	DAX-Kennzahlen 
•	Interaktives Power-BI-Dashboard 
•	Dashboard-Screenshots 
•	Projektdokumentation 

### Wichtig für GitHub

Deine Ordnerstruktur sollte so aussehen:

```text
Marketing-Campaign-Analytics/
│
├── README.md
│
├── python/
│   └── marketing_campaign_analysis.py
│
├── notebooks/
│   └── marketing_campaign_analysis.ipynb
│
├── data/
│   └── processed/
│       ├── Fact_Marketing.csv
│       ├── Dim_Date.csv
│       ├── Dim_Channel.csv
│       ├── Dim_Region.csv
│       └── Dim_Product.csv
│
├── powerbi/
│   └── Marketing_Campaign_Analytics.pbix
│
└── screenshots/
    ├── page1_executive_overview.png
    ├── page2_channel_campaign_performance.png
    └── page3_regional_product_analysis.png

