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
layout: two-cols-custom
---

<img src="/klips_logo.svg" style="max-width: 50px !important, "/>
<img src="/svdo.jpg" style="width: 160px !important"/>

<div class="social">

- <mdi-email-edit-outline /> dobbert@terrestris.de
- <mdi-twitter /> terrestris.de
- <mdi-Github /> github.com/terrestris
</div>

::right::
### Svenja Dobbert

- Geographie PhD
- Anwendungsentwicklerin @terrestris

<img src="/terrestris-logo-bw.png" style="width: 200px !important" class="py-6" />

---
layout: main
class:
---

<img src="/klips_logo.svg" style="max-width: 30% !important" class="self-center" />

[www.klips-projekt.de](https://www.klips-projekt.de)

<img src="/project.svg" style="max-width: 100vw !important" class="self-center" />

<!-- <div class="flex justify-center">
  <img src="/bmdv.png" style="height:20%" />
  <img src="/mfund.jpg" style="height:20%" />
</div> -->
<div id="columns" class="flex justify-center">

**Echtzeitanalyse**:\
Lokalisierung der aktuell auftretenden Hitzeinseln im Stadtgebiert

**Prognose**:\
Maschinelles Lernen zur Auswertung historischer Daten und Ableitung von Temperaturprognosen für 48 Stunden.

**Simulation**:\
Auswirkungen baulicher oder planerischer Maßnahmen aufs Stadtklima im Vorhinein durchspielen
</div>

---
layout: two-cols-header
class:
---
<img src="/klips_logo.svg" style="max-width: 12rem !important" class="flex justify-right" />

# Projektkomponenten & -partner

<img src="/klips-projektpatner.svg" class="py-6" />

---
layout: two-cols-header
class:
---
<img src="/klips_logo.svg" style="max-width: 12rem !important" class="flex justify-right" />

# Geodateninfrastruktur

<img src="/klips-overview.png" class="py-6" />

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
- Im KLIPS-Projekt wird ein vordefinierter "Job" an RabbitMQ geschickt, der den gesamten Workflow als Liste von Einzeljobs darstellt
  
</div>

<img src="/rabbitmq.svg" style="max-width: 60rem !important"/>

::right::

<img src="/example-job.png" style="max-width: 9rem !important; margin-left: 17rem !important;"/>

---
layout: two-cols-header
class:
---

<img src="/worker-overview.svg" class="upper-right"/>

::left::

<img src="/klips_logo.svg" style="max-width: 12rem !important" class="flex justify-right" />

# Datenverarbeitung

<img src="/worker.svg" style="max-width: 60rem !important"/>

---
layout: two-cols-header
class:
---
<img src="/klips_logo.svg" style="max-width: 12rem !important" class="flex justify-right" />

# Dateninfrastruktur

<img src="/data-infrastructure.png"/>

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

<img src="/gdal-logo.png" style="float: right; max-width: 3rem !important"/> 

::right::

<img src="/pygeoapi-processes.png" class="img-shadow" style="width: 21rem !important; margin-left: 3rem !important;" />







---
layout: two-cols-header
class:
---


# KLIPS

::left::

*Digitale Informationsplattform zur
Lokalisierung, Prognose und Simulation
von Hitzeinseln*

- **Echtzeitanalyse**: Lokalisierung der aktuell auftretenden Hitzeinseln im Stadtgebiet
- **Prognose**: Mithilfe von Verfahren des Maschinellen Lernens werden historische Daten ausgewertet und Wirkungszusammenhänge für die nächsten 48 Stunden abgeleitet.
- **Simulation**: Auswirkungen baulicher oder planerischer Maßnahmen aufs Stadtklima im Vorhinein durchspielen

::right::

<img src="/klips_overview.png" />

---
layout: main
---

# "Unsere" Arbeitspakete

- Aufbau GDI
- Automatische Prozessierung und Veröffentlichung von Ergebnisdaten über APIs
- Demonstratoren für einzelne APIs

<div style="margin-top: 20px;"></div>
<img src="/klips_architecture1.png" style="width:90%"/>

---
layout: two-cols
class:
---

# KLIPS Daten

- Zeitreihen (Machine Learning + Sensorik) für Modellregionen
  - Temperaturvorhersagen (+48 Std) aus Modell
  - Echtzeit Temperaturen aus Modell
  - Räumliche Auflösung: ~10m
- Cloud-Optimized GeoTIFF (COG)
  - Vollständig kompatibel zu allem was GeoTIFF lesen kann
  - Räumliche Ausschnitte auslesbar durch HTTP Range Requests
  - Viele Tools und Libraries, u.a. GDAL, GeoServer, QGIS, GRASS GIS, OpenLayers

::right::

<div style="float: right">
  <img src="/cog.png" style="width: 300px; float: right;"/>
</div>

---
layout: main
class:
---

# Rasterstatistiken für KLIPS

- Fasst die Werte eines Rasters basierend auf Vektorgeometrien zusammen
- Input:
  - Vorhersage-Raster (COG)
  - Geometrie (Punkt oder Polygon)
- Output: Statistiken (als JSON)
- Exemplarische Use-Cases
  - Altersheim möchte wissen, ob Gelände von Hitzeinsel betroffen ist
  - Stadtplaner wollen wissen, in welchen Gebieten Maßnahmen getroffen werden müssen

<img src="/rasterstats.svg" class="py-4" style="width: 50%">

---
layout: main
---

# OGC API Processes

- Nachfolger von WPS (Web Processing Service)
- **Core Part 1** veröffentlicht in 12/2021
- RESTful
- JSON encodings
- Asynchron und Synchron
- [Implementierungen](https://github.com/opengeospatial/ogcapi-processes/blob/master/implementations.adoc)
  - pygeoapi
  - ZOO-Project
  - u.w.

---
layout: main
class:
---

<div class="flex justify-center">
  <img src="/pygeoapi-logo.png" style="width:15vw" class="self-center py-8" />
</div>

- Python Server Software für OGC API Services
- Plugin-Architektur
- Synchroner und asynchroner Modus
- OpenAPI
- Unterstütze Standards: OGC API Features, OGC API Processes, OGC API Coverages, OGC API Tiles, etc.
- [OSGeo Projekt](https://www.osgeo.org/projects/pygeoapi/)
- Einfacher Workflow um etablierte GDAL oder GRASS Prozesse als OGC API Process zu veröffentlichen


---
layout: two-cols-header
---

# Übersicht Prozesse

::left::

maschinenlesbar

<img src="/process_overview_json.png" alt="Übersicht Prozesse" style="width: 30vw">

::right::

menschenexplorierbar

<img src="/process_overview_html.png" alt="Übersicht Prozesse" style="width: 30vw">

---
layout: two-cols-header
class:
---

# Detailansicht Prozesse

::left::

<img src="/process_detail_point_json.png" alt="Übersicht Prozesse" style="width: 40vw">

::right::

<img src="/process_detail_point_html.png" alt="Übersicht Prozesse" style="width: 40vw">

---
layout: two-cols-header
class: request-response
---

::left::

# Example Request

<!-- nebeneinander packen  -->

HTTP POST https://klips-dev.terrestris.de/processes/location-info-rasterstats/execution

Payload:

```json
{
  "inputs": {
    "x": 1525303.0,
    "y": 6636103.0,
    "cogDirUrl": "http://nginx/cog/",
    "inputCrs": "EPSG:3857",
    "startTimeStamp": "2000-01-01T12:32:00Z",
    "endTimeStamp": "2024-12-31T12:32:00Z"
  }
}
```

::right::

# Example Response

  ```json
  {
    "values": [
      {
        "band_0": 27.52368756798535,
        "timestamp": "2022-02-16T00:00:00Z"
      },
      {
        "band_0": 22.25165738512104,
        "timestamp": "2022-02-17T00:00:00Z"
      },
      {
        "band_0": 27.88457518896883,
        "timestamp": "2022-02-18T00:00:00Z"
      }
    ]
  }
  ```

---
layout: main
class:
---

# Web Demonstrator

<img src="/web-demo.png" alt="Web Demonstrator" style="height: 80%"/>

<!-- <div class="klips-footer">
  <SlideCurrentNo className="pageNumber" />
</div> -->

https://klips-dev.terrestris.de/demonstrator/

---
layout: main
class:
---

# Ausblick

- Top-Level-API
  - mit Hilfe oder basierend auf OGC API Processes
  - Direkte Chart Generierung für Zeitreihen
  - Videos für "Timelapse"
  - API für Hitze-Warnungen für bestimmte Position / Adressen

## <!-- this adds an empty h2 as spacer -->

# Fazit

- Sehr einfach nutzbar, für Webanwendungen aber auch für den Menschen
- Raus aus der XML-Hölle
- Sehr flexibel in Einrichtung / Implementierung


---
layout: main
class:
---


# Hilfreiche Links

- Source Code: https://github.com/klips-project/klips-sdi
- KLIPS pygeoapi: https://klips-dev.terrestris.de/pygeoapi
  - OpenAPI: https://klips-dev.terrestris.de/pygeoapi/openapi
- Demonstrator Rasterstatistiken: https://klips-dev.terrestris.de/demonstrator
- pygeoapi: https://pygeoapi.io
- OGC API Processes: https://ogcapi.ogc.org/processes
- KLIPS Projekt: https://www.klips-projekt.de


---
layout: main
---

# Kontakt / Impressum

<div style="width: 45%; float: left;">
  <address style="text-align: left">
    <strong>Hannes Blitza</strong><br />
    <span style="font-size: smaller;">
      terrestris GmbH &amp; Co. KG<br />
      Kölnstr. 99<br />
      53111 Bonn<br />
      blitza@terrestris.de
    </span>
  </address>
</div>

<div style="width: 45%; float: right; margin-top: 25px;">
  <address style="text-align: right">
    <strong>Christian Mayer</strong><br />
    <span style="font-size: smaller;">
      meggsimum - Büro für Geoinformatik<br />
      Schillerstraße 2a<br />
      67112 Mutterstadt<br />
      chris@meggsimum.de
    </span>
  </address>
</div>

<p id="license" style="margin-top: 25px;">
  Diese Folien sind unter <a href="http://creativecommons.org/licenses/by-sa/2.0/">CC BY-SA</a>
  veröffentlicht.
</p>
