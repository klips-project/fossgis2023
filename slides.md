---
# try also 'default' to start simple
theme: default
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: https://source.unsplash.com/collection/94734566/1920x1080
# apply any windi css classes to the current slide
class: 'text-center'
# https://sli.dev/custom/highlighters.html
highlighter: shiki
# show line numbers in code blocks
lineNumbers: false
# some information about the slides, markdown enabled
info: |
  ## Slidev Starter Template
  Presentation slides for developers.

  Learn more at [Sli.dev](https://sli.dev)
# persist drawings in exports and build
drawings:
  persist: false
# page transition
transition: slide-left
# use UnoCSS
css: unocss
layout: start
fonts:
  # basically the text
  sans: 'Open Sans'
  # use with `font-serif` css class from windicss
  serif: 'Robot Slab'
  # for code blocks, inline code, etc.
  mono: 'Fira Code'
---

## Geodatenanalyse in der Cloud
# OGC API Processes und pygeoapi


---
layout: two-cols-custom
---


<img src="/chris-mayer.jpg" style="width: 200px !important"/>

  - chris@meggsimum.de
  - twitter: @meggsimum
  - [github/terrestris.de](https://github.com/meggsimum)


::right::
### Christian Mayer
- Geoinformatiker
- Anwendungsentwickler
- OSGeo Foundation Charter Member

<img src="/meggsimum-logo.png" style="width: 200px !important" class="py-6" />

<div class="klips-footer">
  <SlideCurrentNo className="pageNumber" /> / <SlidesTotal />
</div>


---
layout: two-cols-custom
---

<img src="/hannes-blitza.jpg" style="width: 200px !important"/>

  - blitza@terrestris.de
  - twitter: @terrestrisde
  - [github/terrestris.de](https://github.com/terrestris)


::right::
### Hannes Blitza
- Geographie M.Sc.
- Anwendungsentwickler
- Training für OS Geo Software

<img src="/terrestris-logo-normal.svg" style="width: 200px !important" class="py-6" />

<div class="klips-footer">
  <SlideCurrentNo className="pageNumber" />
</div>

---
layout: main
class:
---

<img src="/klips_logo.png" style="width:20vw" class="self-center" />

[www.klips-projekt.de](https://www.klips-projekt.de)

### KI-basierte Informationsplattform für die Lokalisierung und Simulation von Hitzeinseln für eine innovative Stadt- und Verkehrsplanung

<div class="flex justify-center">
  <img src="/bmdv.png" style="height:40%" />
  <img src="/mfund.jpg" style="height:40%" />
</div>

<div class="klips-footer">
  <SlideCurrentNo className="pageNumber" />
</div>

---
layout: two-cols
class: 
---


*Digitale Informationsplattform zur 
Lokalisierung, Prognose und Simulation 
von Hitzeinseln*

- **Echtzeitanalyse**: Lokalisierung der aktuell auftretenden Hitzeinseln im Stadtgebiet
- **Prognose**: Mithilfe von Verfahren des Maschinellen Lernens werden historische Daten ausgewertet und Wirkungszusammenhänge für die nächsten 48 Stunden abgeleitet.
- **Simulation**: Auswirkungen baulicher oder planerischer Maßnahmen aufs Stadtklima im Vorhinein durchspielen

::right::

<img src="/klips_overview.png" />

<div class="klips-footer">
  <SlideCurrentNo className="pageNumber" />
</div>

---
layout: main
---

# "Unsere Arbeitspakete"

TODO herausarbeiten
Was genau machen meggsimum und terrestris
--> 1,2 prägnante Sätze

<div class="klips-footer">
  <SlideCurrentNo className="pageNumber" />
</div>
---
layout: main
---

# KLIPS GDI Übersicht

<img src="/klips_architecture1.png" style="width:90%"/>
<div class="klips-footer">
  <SlideCurrentNo className="pageNumber" />
</div>

---
layout: main
---

# Message Queue

<img src="/rabbitmq.svg" style="width:90%"/>
<div class="klips-footer">
  <SlideCurrentNo className="pageNumber" />
</div>

---
layout: main
---

# OGC API Processes

- Nachfolger von WPS (Web Processing Service)
- JSON-basiert
- REST-Schnittstelle
- stabile Version veröffentlicht Ende 2021
- [Implementierungen](https://github.com/opengeospatial/ogcapi-processes/blob/master/implementations.adoc)

<div class="klips-footer">
  <SlideCurrentNo className="pageNumber" />
</div>

---
layout: main
class: 
---

<div class="flex justify-center">
  <img src="/pygeoapi-logo.png" style="width:20vw" class="self-center" />
</div>

- in Python
- Server Software für OGC API Diensten
- unterstütze Standards
  - OGC API Features
  - OGC API Processes
  - OGC API Coverages
  - ...
- OSGeo Projekt

<div class="klips-footer">
  <SlideCurrentNo className="pageNumber" />
</div>

---
layout: main
class: 
---

# Zonale Statistiken

- Fasst die Werte eines Rasters innerhalb der Zonen eines anderen Datasets zusammen.
- Beschreibung der Input Daten
- Use Case beschreiben
- TODO: Abbildung!

<div class="klips-footer">
  <SlideCurrentNo className="pageNumber" />
</div>

---
layout: main
class: 
---


<img src="/cog.png" style="width: 300px"/>

- Cloud-Optimized GeoTIFF (COG)
- Vollstens kompatibel zu allem was GeoTIFF lesen kann
- Räumliche Ausschnitte auslesbar durch HTTP Range Requests
- Viele Tools und Libraries, u.a. GDAL, GeoServer, QGIS, GRASS GIS
- TODO example (OL oder GDAL)


<div class="klips-footer">
  <SlideCurrentNo className="pageNumber" />
</div>

---
layout: main
class: 
---


<img src="/gdal-logo.png" style="width: 200px"/>

- Bibliothek zur Prozessierung und Umwandlung von Geodaten
- darauf aufbauene Python-Bibliotheken
  - fiona (Vektordaten)
  - rasterio (Rasterdaten)
  - rio-cogeo (Plugin von rasterio für Rasterdaten)
  - rasterstats (Zonale Statistiken)
- OSGeo Projekt


<div class="klips-footer">
  <SlideCurrentNo className="pageNumber" />
</div>

---
layout: main
class: 
---

<img src="/grassgis_logo.png" style="width: 200px"/>

- Funktionsreiches, performantes, modulares GIS (C und Python)
- > 500 Module + ~ 360 Addons
- Python Bindings 
- TODO actinia, openeo erläutern

<div class="klips-footer">
  <SlideCurrentNo className="pageNumber" />
</div>

---
layout: main
class: 
---

# Übersicht Prozesse

<img src="/process_overview.png" alt="Übersicht Prozesse" style="width: 30vw">

<div class="klips-footer">
  <SlideCurrentNo className="pageNumber" />
</div>


---
layout: main
class: 
---

# Detailansicht Prozesse

<img src="/process_detail.png" alt="Übersicht Prozesse" style="width: 40vw">

<div class="klips-footer">
  <SlideCurrentNo className="pageNumber" />
</div>

---
layout: main
class: 
---

# Example request
```json
{
  "inputs": {
    "x": 1525303,
    "y": 6636103,
    "cogDirUrl": "http://nginx/cog/",
    "inputCrs": "EPSG:3857",
    "startTimeStamp": "2000-01-01T12:32:00Z",
    "endTimeStamp": "2024-12-31T12:32:00Z"
  }
}
```
<div class="klips-footer">
  <SlideCurrentNo className="pageNumber" />
</div>

---
layout: main
class: 
---

# Example response

  ```json
  {
    "values": [
      {
        "band_0": 276.52368756798535,
        "timestamp": "2022-02-16T00:00:00Z"
      },
      {
        "band_0": 22.25165738512104,
        "timestamp": "2022-02-17T00:00:00Z"
      }
    ]
  }
  ```
<div class="klips-footer">
  <SlideCurrentNo className="pageNumber" />
</div>


---
layout: main
class: 
---

# Web Demonstrator

<img src="/web-demo.png" alt="Web Demonstrator" />

<div class="klips-footer">
  <SlideCurrentNo className="pageNumber" />
</div>

---
layout: main
class: 
---

# Links

- Source Code: https://github.com/klips-project/klips-sdi
- Demonstrator Rasterstatistiken: https://klips-dev.terrestris.de/demonstrator
- Vortrag in FOSSGIS: https://pretalx.com/fossgis2023/talk/BTSUDS
- pygeoapi: https://pygeoapi.io
- OGC API Processes: https://ogcapi.ogc.org/processes
- KLIPS Projekt: https://www.klips-projekt.de
- meggsimum: https://meggsimum.de
- terrestris: https://www.terrestris.de

<div class="klips-footer">
  <SlideCurrentNo className="pageNumber" />
</div>