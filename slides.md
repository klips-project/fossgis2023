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

# Geodatenanalyse in der Cloud
## OGC API Processes und pygeoapi

::logos::

<img src="/terrestris-logo-normal.svg" />
<img src="/meggsimum-logo_bold.png"  />

::authors::

Hannes Blitza, Christian Mayer

---
layout: two-cols-custom
---

<img src="/profilbild-christian-mayer.jpeg" style="width: 200px !important"/>

<div class="social">

- <mdi-email-edit-outline /> chris@meggsimum.de
- <mdi-twitter /> meggsimum
- <mdi-Github /> github.com/meggsimum
</div>

::right::
### Christian Mayer

- Dipl.-Ing. Geoinformatik und Vermessung
- Gründer und CEO meggsimum
- Softwarearchitekt und -entwickler
- OSGeo Foundation Charter Member

<img src="/meggsimum-logo_bold.png" style="width: 300px !important" class="py-6" />

---
layout: two-cols-custom
---

<img src="/hbl.jpg" style="width: 160px !important"/>

<div class="social">

- <mdi-email-edit-outline /> blitza@terrestris.de
- <mdi-twitter /> terrestrisde
- <mdi-Github /> github.com/terrestris
</div>

::right::
### Hannes Blitza
- Geographie M.Sc.
- Vertrieb und Anwendungsentwickler @terrestris
- Training für OS Geo Software
  - Masterportal
  - QGIS
  - MapProxy
  - GeoServer

<img src="/terrestris-logo-normal.svg" style="width: 200px !important" class="py-6" />

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

# "Unsere Arbeitspakete"

- Aufbau GDI
- Automatische Prozessierung und Veröffentlichung von Ergebnisdaten über APIs
- Demonstratoren für einzelne APIs

<div style="margin-top: 20px;"></div>
<img src="/klips_architecture1.png" style="width:90%"/>

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
- unterstütze Standards: OGC API Features, OGC API Processes, OGC API Coverages, OGC API Tiles, etc.
- [OSGeo Projekt](https://www.osgeo.org/projects/pygeoapi/)
- Einfacher Workflow um etablierte GDAL oder GRASS Prozesse als OGC API Process zu veröffentlichen

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
- Exemplarischer Usecase: <br />
   Eine Schulleitung möchte die Vorhersage für das Schulgelände erfahren.

<img src="/rasterstats.svg" class="py-8" style="width: 50%">

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
class:
---

::left::

# Example request

<!-- nebeneinander packen  -->

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

---
layout: main
class:
---

# Web Demonstrator

<img src="/web-demo.png" alt="Web Demonstrator" />

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
- Demonstrator Rasterstatistiken: https://klips-dev.terrestris.de/demonstrator
- Vortrag in FOSSGIS: https://pretalx.com/fossgis2023/talk/BTSUDS
- pygeoapi: https://pygeoapi.io
- OGC API Processes: https://ogcapi.ogc.org/processes
- KLIPS Projekt: https://www.klips-projekt.de

---
end
---

# end