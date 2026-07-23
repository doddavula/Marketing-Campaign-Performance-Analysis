📊 Marketing Campaign Analytics
📌 Projektübersicht

Dieses Projekt ist eine End-to-End-Analyse von Marketingkampagnendaten mit Python, Pandas, NumPy, Power BI und DAX.

Ziel des Projekts ist die Analyse der Kampagnenperformance nach:

Marketingkanal
Region
Produkt
Kampagne
Zeitraum

Der gesamte Analyseprozess umfasst die Datenaufbereitung in Python, die Datenqualitätsprüfung, die Modellierung in Power BI, die Erstellung dynamischer DAX-Kennzahlen und die Entwicklung interaktiver Dashboards.

🔄 End-to-End-Workflow

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

🎯 Business Problem

Marketingteams investieren Budgets in verschiedene Kampagnen und Marketingkanäle. Rohdaten zeigen jedoch nicht immer direkt:

Welcher Marketingkanal den höchsten Umsatz erzielt
Welcher Kanal die beste CTR aufweist
Welche Kampagnen die meisten Conversions generieren
Welche Regionen die beste Performance zeigen
Welche Produkte den höchsten Umsatz erzielen
Wie effizient das Marketingbudget eingesetzt wird
Wie hoch der Return on Investment ist

Dieses Projekt beantwortet diese Fragen mithilfe von Datenanalyse und Business Intelligence.

🐍 Python-Datenaufbereitung

Python und Pandas wurden verwendet für:

Einlesen der Rohdaten
Untersuchung des Datensatzes
Prüfung der Datentypen
Behandlung fehlender Werte
Entfernung von Duplikaten
Bereinigung von Textfeldern
Datenqualitätsprüfung
Vorbereitung der Daten für Power BI
Verwendete Technologien
Python
Pandas
NumPy
Jupyter Notebook
✅ Datenqualitätsprüfung

Es wurden verschiedene Business Rules überprüft.

Klicks dürfen nicht größer als Impressions sein

Clicks ≤ Impressions

Conversions dürfen nicht größer als Klicks sein

Conversions ≤ Clicks

Negative Ausgaben prüfen

Spend ≥ 0

Negative Umsätze prüfen

Revenue ≥ 0

⭐ Power-BI-Datenmodell

Das Datenmodell wurde als Star Schema aufgebaut.

Faktentabelle

Fact_Marketing

Enthält messbare Marketingkennzahlen:

Campaign_ID
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
🧮 DAX-Kennzahlen
Total Impressions
Total Impressions =
SUM(Fact_Marketing[Impressions])
Total Clicks
Total Clicks =
SUM(Fact_Marketing[Clicks])
Total Conversions
Total Conversions =
SUM(Fact_Marketing[Conversions])
Total Spend
Total Spend =
SUM(Fact_Marketing[Spend])
Total Revenue
Total Revenue =
SUM(Fact_Marketing[Revenue])
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

🔄 Conversion Rate
Formel

Conversion Rate = Conversions ÷ Clicks

DAX
Conversion Rate =
DIVIDE(
    [Total Conversions],
    [Total Clicks],
    0
)

Die Conversion Rate zeigt, wie viele Klicks zu einer Conversion geführt haben.

💰 ROI – Return on Investment
Formel

ROI = (Revenue - Spend) ÷ Spend

DAX
ROI =
DIVIDE(
    [Total Revenue] - [Total Spend],
    [Total Spend],
    0
)

Der ROI zeigt den erzielten Ertrag im Verhältnis zur Marketinginvestition.

📊 Power-BI-Dashboard
1️⃣ Executive Overview

Die erste Seite bietet einen Überblick über die gesamte Marketingperformance.

KPIs
Total Spend
Total Revenue
Total Conversions
CTR
ROI
Visualisierungen
Monthly Revenue Trend
Revenue by Marketing Channel
Conversions by Region
Filter
Year
Region
Product
Marketing Channel
Dashboard-Screenshot

2️⃣ Channel & Campaign Performance

Diese Seite analysiert die Performance nach Marketingkanal und Kampagne.

Analysen
Marketing Spend by Channel
Revenue by Channel
CTR by Channel
Conversion Rate by Channel
Campaign Performance
Dashboard-Screenshot

3️⃣ Regional & Product Performance

Diese Seite analysiert die Performance nach Region und Produkt.

Visualisierungen
Revenue by Region
Revenue by Product
Conversions by Region
Conversions by Product
Product and Region Matrix
Filter
Year
Region
Product
Marketing Channel
Dashboard-Screenshot

💡 Business Insights

Das Dashboard unterstützt die Beantwortung folgender Fragen:

Welcher Marketingkanal erzielt den höchsten Umsatz?
Welcher Kanal hat die beste CTR?
Welche Kampagne generiert die meisten Conversions?
Welche Region erzielt die beste Performance?
Welches Produkt erzielt den höchsten Umsatz?
Welche Kanäle haben den besten ROI?
Welche Kampagnen sollten optimiert werden?
💼 Interview-Zusammenfassung

Ich habe ein End-to-End-Projekt zur Analyse von Marketingkampagnen mit Python, Pandas, Power BI und DAX entwickelt.

Zunächst habe ich die Marketingdaten mit Python und Pandas aufbereitet und Datenqualitätsprüfungen durchgeführt. Dabei wurden unter anderem Business Rules überprüft, beispielsweise dass die Anzahl der Klicks nicht größer als die Anzahl der Impressions und die Anzahl der Conversions nicht größer als die Anzahl der Klicks sein darf.

Anschließend habe ich in Power BI ein Star-Schema mit einer zentralen Faktentabelle und Dimensionstabellen für Datum, Marketingkanal, Region und Produkt erstellt.

Mit DAX habe ich dynamische Kennzahlen wie Total Spend, Total Revenue, CTR, Conversion Rate, CPC, CPA und ROI erstellt.

Abschließend habe ich ein interaktives Power-BI-Dashboard mit drei Seiten entwickelt:

Executive Overview
Channel & Campaign Performance
Regional & Product Performance

Die interaktiven Filter ermöglichen eine dynamische Analyse der Kampagnenperformance und unterstützen datenbasierte Entscheidungen zur Optimierung von Marketingkampagnen.

🛠️ Technologien
Technologie	Verwendung
Python	Datenaufbereitung
Pandas	Datenbereinigung und Transformation
NumPy	Numerische Berechnungen
Power BI	Datenvisualisierung
DAX	Dynamische Kennzahlen
Excel	Quelldaten
CSV	Datenaustausch
🎓 Gezeigte Kompetenzen
Datenbereinigung
Datenqualitätsprüfung
Explorative Datenanalyse
Python
Pandas
NumPy
Power BI
DAX
Datenmodellierung
Star Schema
KPI-Entwicklung
Datenvisualisierung
Business Analysis
Marketing Analytics
📁 Projektdateien
Python-Skript zur Datenaufbereitung
Jupyter Notebook
Aufbereitete CSV-Dateien
Power-BI-Datenmodell
DAX-Kennzahlen
Interaktives Power-BI-Dashboard
Dashboard-Screenshots
Projektdokumentation
