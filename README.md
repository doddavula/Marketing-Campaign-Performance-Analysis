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




