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

Business Rule:

Clicks ≤ Impressions

Conversions dürfen nicht größer als Klicks sein

Business Rule:

Conversions ≤ Clicks

Negative Ausgaben prüfen

Business Rule:

Spend ≥ 0

Negative Umsätze prüfen

Business Rule:

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

💵 CPC – Cost Per Click
Formel

CPC = Spend ÷ Clicks

DAX
CPC =
DIVIDE(
    [Total Spend],
    [Total Clicks],
    0
)

CPC zeigt die durchschnittlichen Kosten für einen Klick.

💳 CPA – Cost Per Acquisition
Formel

CPA = Spend ÷ Conversions

DAX
CPA =
DIVIDE(
    [Total Spend],
    [Total Conversions],
    0
)

CPA zeigt die durchschnittlichen Kosten für eine Conversion.

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
📸 Dashboard-Screenshot

2️⃣ Channel & Campaign Performance

Diese Seite analysiert die Performance nach Marketingkanal und Kampagne.

Analysen
Marketing Spend by Channel
Revenue by Channel
CTR by Channel
Conversion Rate by Channel
Campaign Performance
📸 Dashboard-Screenshot

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
📸 Dashboard-Screenshot

💡 Business Insights

Das Dashboard unterstützt die Beantwortung folgender Fragen:

Welcher Marketingkanal erzielt den höchsten Umsatz?
Welcher Kanal hat die beste CTR?
Welche Kampagne generiert die meisten Conversions?
Welche Region erzielt die beste Performance?
Welches Produkt erzielt den höchsten Umsatz?
Welche Kanäle haben den besten ROI?
Welche Kampagnen sollten optimiert werden?
