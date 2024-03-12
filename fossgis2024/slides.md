---
theme: default
class: 'text-center'
highlighter: shiki
# show line numbers in code blocks
lineNumbers: true
# persist drawings in exports and build
drawings:
  persist: false
# page transition
transition: slide-left
# use UnoCSS
css: unocss
layout: cover_custom
fonts:
  # basically the text
  sans: 'Lato'
favicon: https://fossgis-konferenz.de/favicon.ico
---

## Verarbeitung und Darstellung hochaufgelöster Umweltdaten auf Basis von OGC API Processes
<img src="/klips_logo.svg" style="max-width: 100%; height: auto; max-height: 120px; padding-left: 35vh; padding-top: 4vh"/>
::logos::
<img src="/terrestris-logo-bw.png" style="max-width: 100%; height: auto; max-height: 100px; padding-bottom: 2vh" />
<img src="/meggsimum-logo-bw.png" style="max-width: 100%; height: auto; max-height: 50px; padding-bottom: 2vh"  />

::authors::

Svenja Dobbert

---
layout: two-cols-header
---

<img src="/klips_logo.svg" style="max-width: 12rem !important" class="flex justify-right" />

# Svenja Dobbert

::left::
<img src="/svdo.jpg" style="width: 12rem !important; margin-top: 2rem !important; margin-left: 4rem !important"/>

<div class="social">

- **Email**: dobbert@terrestris.de
</div>

::right::
<div style="margin-top: 3rem !important;">

- Geographie PhD
- Anwendungsentwicklerin @terrestris

<img src="/terrestris-logo-bw.png" style="margin-top: 2rem !important; margin-left: 4rem !important; width: 30% !important" class="py-6" />

</div>


---
layout: main
class: null
---

<img src="/klips_logo.svg" style="max-width: 30% !important" class="self-center" />

[www.klips-projekt.de](https://www.klips-projekt.de)

<img src="/project.svg" style="max-width: 100vw !important" class="self-center" />

<div id="columns" class="flex justify-center">

**Echtzeitanalyse**:\
Lokalisierung der aktuell auftretenden Hitzeinseln im Stadtgebiert

**Prognose**:\
Maschinelles Lernen zur Auswertung historischer Daten und Ableitung von Temperaturprognosen für 48 Stunden.

**Simulation**:\
Auswirkungen baulicher oder planerischer Maßnahmen aufs Stadtklima im Vorhinein durchspielen
</div>

<!--
KLIPS-Projekt in 2021 gestartet

Forschungsprojekt
Aktuell kurz vor Projektende, Nachfolgeprojekt im Gespräch, aber noch nicht konkret geplant

KI-basierte Verarbeitung von Temperaturdaten vor dem konkreten Hintergrund von städtischer Wärmebelastung (Auswirkung auf Gesundheit, bauliche Maßnahmen)
Zwei Pilotstädte: Dresden & Langenfeld

Es sollen aktuelle Temperaturdaten genutzt werden, um städtische Hitzeinseln zu frühzeitig zu erkennen 
Relevant zum Beispiel für Städte und  Gesundheitsämter, vulnerable Infrastruktur,...

Ziel des Projektes ist es auch, Simulationen rechnen und darstellen zu können, z.B. bei baulichen Maßnahmen
Auswirkungen auf das Stadtklima
Dazu erste Beispiele, nicht abschließend umgesetzt, im Gespräch für Folgeprojekt
-->

---
layout: two-cols-header
class: null
---

<img src="/klips_logo.svg" style="max-width: 12rem !important" class="flex justify-right" />

# Projektkomponenten & -partner

<img src="/klips-projektpatner.svg" class="py-6" />

<!--
Ausgedehntes Sensornetzwerk in Dresden und Langenfeld, über 300 Temperatursensoren im Stadtgebiet
Fraunhofer HHI hat KI-basiertes Modell erstellt
Aus diesen Daten werden flächendeckend (10 m) Temperaturwerte errechnet
Unsere Rolle im Projekt: Verarbeitung dieser Daten und Bereitstellung für die Anwender, Entwicklung von kleineren Demonstratoren
-->

---
layout: two-cols-header
class:
---
<img src="/klips_logo.svg" style="max-width: 12rem !important" class="flex justify-right" />

# Daten

::left::

<div class="text-box">

**Statische Daten**\
(einmalige Bereitstellung, 24 Stunden, Auflösung ~ 10 m)\
*Hitzeindex*: Wärmebelastung - Kombination von Luftfeuchte & Lufttemperatur in °C\
*Urban Heat Islands (UHI)*: Wärmebelastung städtischer Bereiche im Vergleich zum Umland in °C

</div>

<div class="text-box">

**Prognosedaten**\
(48h Vergangenheit + Jetztzeitpunkt + 47h Prognose, Auflösung ~ 10 m)\
Stündlich neue Lieferung\
*Physikalische Temperatur*: Temperaturwerte aus den gemessenen Temperaturen auf das Stadtgebiet interpoliert in °C\
*Hitzeindex*: Wärmebelastung - Kombination von Luftfeuchte & Lufttemperatur in °C\
*Temperaturdifferenz*: Temperaturdifferenz zum Umland in °C

</div>

::right::

<img src="/langenfeld-hi.png" class="img-shadow"/>

<div style="margin-left: 12rem !important;  margin-top: 1rem !important;">
= Stündliche Verarbeitung       von ~ 2 x 96 GeoTIFFs 
</div>

<!--
Unterschiedliche Daten im Projekt
Einmal "statische" Daten, die für einen fiktiven Tag zur Verfügung stehen
Wurden einmalig geliefert und in unsere Dienste eingebunden
HI und UHI
UHI ist Differenz zum Umland, zeigt also auch Infos, wie das Stadtgebiet langsamer abkühlt

Spannender: Stündliche Datenlieferung, 96 Geotiffs, Prognose, Jetztzeitpunkt 
Werden jeweils mit Timestamp und 3 Bändern geliefert und von uns verarbeitet

Beispiel: Hitzeindex Langenfeld
-->
---
layout: main
class:
---

<img src="/klips_logo.svg" style="max-width: 30% !important" class="self-center" />

#
# Beispiel: UHI für Dresden

<img src="/dresden-uhi.png" style="max-width: 45% !important" class="self-center" />

<!--
Beispiel: UHI 18:00 Uhr Dresden
Unterschiede im Stadtgebiet werden deutlich, langsame Abkühlung
-->

---
layout: two-cols-header
class:
---
<img src="/klips_logo.svg" style="max-width: 12rem !important" class="flex justify-right" />

# Geodateninfrastruktur

<img src="/klips-overview.png" class="py-6" />

<!--
relativ komplexe Gedateninfrastruktur zur stündlichen Verarbeitung und Veröffentlichung der Daten
Darauf ausgelegt, große Datenmengen (in Echtzeit) zu verarbeiten, für die Nutzer aufzubereiten und in verschiedener Form zur Verfügung zu stellen
Daten kommen über Schnittstelle zum HHI an und werden auf dem Server abgelegt und verarbeitet
Am Ende stehen sie u.a. als OGC-konforme Dienste bereit, um in unsere eigenen Anwendungsbeispiele und den Demonstrator der Software AG eingebunden zu werden
Stündlich werden Daten in ein externes Archiv (IÖR) überführt
Unter anderem kommt der Geoserver und eine Postgres Datenbank zum Einsatz
Die einzelnen Komponenten sind als Microservices aufgebaut und laufen unabhängig voneinander
Vorteil: Viele sind projektunabhängig wiederverwendbar
-->

---
layout: two-cols-header
class:
---
<img src="/klips_logo.svg" style="max-width: 12rem !important" class="flex justify-right" />

# Message Broker: RabbitMQ

::left::

<div class="bullet-points">

- Kommunikation zwischen den einzelnen, unabhängigen Komponenten
- nach dem **AMQP 0-9-1 Standard** aufgebaut (Advanced Message Queuing Protocol)
- Im KLIPS-Projekt wird stündlich ein vordefinierter Job an RabbitMQ geschickt, der den gesamten Workflow als Liste von Einzeljobs darstellt
  
</div>

<img src="/rabbitmq.svg" style="margin-left: 4rem !important; margin-top: 3rem !important; max-width: 35rem !important"/>

::right::

<img src="/example-job.png" style="max-width: 9rem !important; margin-left: 17rem !important;"/>

<!--
Nachrichten zwischen einzelnen Komponenten werden über RabbitMQ ausgetauscht
Weit verbreitet
Einzelne Komponenten (Worker) können ausfallen, ohne dass die anderen direkt betroffen sind
Idee: Jeder Worker ist für eine spezifische, nicht projektgebundene Aufgabe zuständig und kann so leicht in anderem Kontext nachgebaut werden
Worker alle mit node.js und typescript implementiert, andere Sprachen theoretisch möglich
Im KLIPS-Projekt gibt es eine Workerkette, die einen "Job", der aus einer Reihe von Einzeljobs besteht, als Nachricht an RabbitMQ weitergibt. Zurückgegeben wird dann jeweils der Status des aktuellen, relevanten Einzeljobs an die results Queue, woraufhin der Gesamtstatus ergänzt wird.
Das erlaubt, dass eine Reihe von Einzelkomponenten mit spezifischen Input nacheinander ausgeführt werden können und auch der Output eines Workers als Input an einen anderen Worker weitergegeben werden kann.
-->

---
layout: two-cols-header
class:
---

<img src="/worker-overview.svg" class="upper-right"/>

::left::

<img src="/klips_logo.svg" style="max-width: 12rem !important" class="flex justify-right" />

# Datenverarbeitung

<img src="/worker.svg" style="max-width: 60rem !important"/>

<!--
Die aktuelle Workerkette des Projekts (am Ende einige Verarbeitungsschritte weggelassen)
-->

---
layout: two-cols-header
class:
---
<img src="/klips_logo.svg" style="max-width: 12rem !important" class="flex justify-right" />

# Dateninfrastruktur

<img src="/data-infrastructure.svg"/>

<!--
Diese Art der Datenablage im Projekt erlaubt den Nutzern auf drei unterschiedliche Weisen auf die Daten zuzugreifen.
Daten stehen als WMS-Time Dienst zur Verfügung
Es kann direkt via HTTP auf die Daten zugegriffen werden
Über OGC-API-Processes können z.B. Statistiken zu den Daten abgerufen werden
-->

---
layout: two-cols-header
class:
---
<img src="/klips_logo.svg" style="max-width: 12rem !important" class="flex justify-right" />

::left::

# OGC API Processes

- WPS (Web Prozessing Service)-Nachfolger
- (Zonale) Statistiken auf Basis der Daten im Webspace
- Implementierung: **pygeoapi**

<img src="/gdal-logo.png" style="float: right; max-width: 3rem !important"/> 

::right::

<img src="/pygeoapi-processes.png" class="img-shadow" style="width: 21rem !important; margin-left: 3rem !important;" />

<!--
Der Standard OGC-API Prozesses erlaubt, ausführbare Prozesse, z.B. Berechnungen, anzubieten
Wir nutzen für die Implementierung die Software pygeoapi
Stellen verschiedene, in python geschriebene, Prozesse zur Verfügung, die z.B. erlauben ber gdal-Funktionen Statistiken für einzelne Punkte oder Polygone auszugeben
-->

---
layout: two-cols-header
class:
---
<img src="/klips_logo.svg" style="max-width: 12rem !important" class="flex justify-right" />

::left::

# Pygeoapi

- Python-Server-Software
- Unterstützt (u.a.) OGC API Processes
- RESTful
- Plugin-framework
- Einfacher workflow

<img src="/pygeoapi-logo.png" style="float: right; max-width: 12rem !important;  margin-top: 6rem !important;"/> 

::right::

<img src="/statistics-process-input.png" class="img-shadow" style="width: 30rem !important; margin-left: 1rem !important;  margin-top: 11rem !important;" />

<!--
Entscheidung für pygeoapi, da zu dem Zeitpunkt relativ weit verbreitet
Python Server Implementierung verschiedener OGC API Standards
Bisher werden im Projekt aber nur OGC API Processes verwendet
Existiert seit 2018, hat eine Plugin-Architektur
Pygeoapi hört auf HTTP requests und gibt responses aus
Eignet sich dadurch besonders gut für die Anforderungen im KLIPS-Projekt
Beispiel: Zeitbasierte zonale Statistiken, z.B. mean, median, maximum, minimum, für ein beliebiges Polygon auf Basis eines COGS
Input: COG URL (des Ordners), Timestamps (Timestamp über Dateinamen), Bänder, Methode
-->

---
layout: two-cols-header
class:
---
<img src="/klips_logo.svg" style="max-width: 12rem !important" class="flex justify-right" />

##### HTTP POST: https://klips-dev.terrestris.de/processes/zonal-statistics-time-rasterstats/execution

::left::

```javascript
{
   "inputs":{
      "polygonGeoJson":{
         "type":"Polygon",
         "coordinates":[[
               [ 6.94460357153714, 51.11378414303675 ],
               [ 6.947834186694324, 51.11377441300601 ],
               [ 6.947958143292145, 51.111993792443116 ],
               [ 6.944588077027431,  51.111891623590765 ],
               [ 6.94460357153714,  51.11378414303675 ]
            ]]},
      "cogDirUrl":"http://nginx/cog/langenfeld/langenfeld_temperature/",
      "statisticMethods":["max"],
      "inputCrs":"EPSG:4326",
      "startTimeStamp":"2024-02-15T15:00:00+00:00",
      "endTimeStamp":"2024-02-15T17:00:00+00:00",
      "bands":[1]
   }
}
```
::right::

```javascript
{
   "values": [
    {
      "max": 12.280603408813477,
      "band": 1,
      "timestamp": "2024-02-07T15:00:00Z"
    },
     {
      "max": 12.291133880615234,
      "band": 1,
      "timestamp": "2024-02-07T16:00:00Z"
    },
     {
      "max": 12.31892204284668,
      "band": 1,
      "timestamp": "2024-02-07T17:00:00Z"
    },
   ]
}
```

<!--
Beispiel: HTTP POST Request and URL mit dem Input,
Koordinaten eines Polygons in Langenfeld (z.B. Schulhof)
Maximum wird berechnet für 15-17 Uhr
1. Band, also physikalische Temperatur
Ausgabe: 3 Werte (15 Uhr, 16 Uhr, 17 Uhr)
Keine große Spanne, da kaum Temperaturunterschiede zu der Zeit
-->

---
layout: two-cols-header
class:
---
<img src="/klips_logo.svg" style="max-width: 12rem !important" class="flex justify-right" />

# Anwendungen

<img src="/applications.svg" style="margin-left: 9rem !important; width: 70% !important"/>

<!--
Teilweise wird das von den Anwendern (z.B. Stadt Dresden) so verwendet, aber doch noch relativ komplex
Deshalb: Reihe von Anwendungsbeispielen, bei denen der Input durch den Nutzer nicht direkt weitergegeben wird, sondern unsere Anwendung "dazwischen" liegt
-->

---
layout: two-cols-header
class:
---
<img src="/klips_logo.svg" style="max-width: 12rem !important" class="flex justify-right" />

# Anwendungen

https://klips-dev.terrestris.de/easy-to-use-api/chart/?region=dresden&geom=POINT(13.761238060503882%2051.04731292751711)&threshold=25&band=perceived

**Input wird durch den Nutzer über die URL im Browser mitgegeben.** 

<img src="/chart-api.png" style="width: 27rem !important" class="img-shadow"/>

<!--
Beispiel: Chart: Input, z.B. Koordinaten für Polygon, etc. Schwellenwert für die Anzeige
Timestamp: Immer vergangene und folgende 48 Stunden, also alle Daten, die im Projekt vorliegen
Chart ist mit Apache eCharts erstellt
Kann z.B. als iframe in eine Website eingebunden werden
-->

---
layout: two-cols-header
class:
---
<img src="/klips_logo.svg" style="max-width: 12rem !important" class="flex justify-right" />

# Anwendungen

https://klips-dev.terrestris.de/easy-to-use-api/warning/?region=dresden&geom=POINT(13.731467023031588%2051.04039265124143)&thresholdgreen=10&thresholdorange=23&thresholdred=28&band=physical&format=info-board

**Input wird durch den Nutzer über die URL im Browser mitgegeben.** 

<img src="/warning.svg" style="width: 27rem !important" class="img-shadow"/>

<!--
Weiteres Beispiel: Hitzeinformationswidget
Hier werden drei Schwellenwerte mitgegeben, anhand derer dann verschiedene Informationen und Farben angezeigt werden
z.B. Grün, ab 10 Grad, darunter blau für kalte Temperaturen, Hitzewarnung ab 28 Grad
Sehr dynamisch, da Schwellenwerte durch den Nutzer festgelegt werden können
Gilt ebenfalls für die kommenden 48 Stunden
Kann ebenfalls als iFrame eingebunden werden
Use-Case: z.B. Hitzeinformation für Schulen, Pflegeeinrichtungen, etc.
-->
---
layout: two-cols-header
class:
---
<img src="/klips_logo.svg" style="max-width: 12rem !important" class="flex justify-right" />

# Anwendungen

https://klips-dev.terrestris.de/easy-to-use-api/url-generator/

<img src="/url-generator.png" style="width: 35rem !important" class="img-shadow"/>

<!--
Immer noch sehr komplex: Koordinaten müssen mitgegeben werden
Deshalt: URL-Generator, der Nutzern erlaubt, die URL zusammenzustellen
-->

---
layout: main
class:
---

<img src="/klips_logo.svg" style="max-width: 12rem !important" class="flex justify-right" />

#
# Fazit
#
#
- Sehr flexible Struktur
- Beliebig erweiterbar
- Einfache und flexible Nutzung

---
layout: main
class:
---

<img src="/klips_logo.svg" style="max-width: 30% !important" class="self-center" />

#
# Hilfreiche Links
#
#

- **Github**: https://github.com/klips-project
- **KLIPS pygeoapi**: https://klips-dev.terrestris.de/pygeoapi
- **Dokumentation**: https://klips-dev.terrestris.de/easy-to-use-api/dashboard
- **KLIPS Projekt**: https://www.klips-projekt.de
