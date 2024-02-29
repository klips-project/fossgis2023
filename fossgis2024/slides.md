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
<img src="/svdo.jpg" style="width: 12rem !important; margin-top: 3rem !important; margin-left: 1rem !important"/>

<div class="social">

- <mdi-email-edit-outline /> dobbert@terrestris.de
- <mdi-twitter /> terrestris.de
- <mdi-Github /> github.com/terrestris
</div>

::right::
<div style="margin-top: 3rem !important;">

- Geographie PhD
- Anwendungsentwicklerin @terrestris

<img src="/terrestris-logo-bw.png" style="width: 200px !important" class="py-6" />

</div>


---
layout: main
class: null
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

<!--
KLIPS-Projekt in 2021 gestartet

Forschungsprojekt
Aktuell kurz vor Projektende, Nachfolgeprojekt im Gespräch, aber noch nicht konkret geplant

Verarbeitung von Temperaturdaten vor dem konkreten Hintergrund von städtischer Wärmebelastung (Auswirkung auf Gesundheit, bauliche Maßnahmen)
ZweiPilotstädte: Dresden&Langenfeld
-->

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

<img src="/pygeoapi-logo.png" style="float: right; max-width: 12rem !important;  margin-top: 6rem !important;"/> 

::right::

<img src="/statistics-process-input.png" class="img-shadow" style="width: 30rem !important; margin-left: 1rem !important;  margin-top: 11rem !important;" />

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

---
layout: two-cols-header
class:
---
<img src="/klips_logo.svg" style="max-width: 12rem !important" class="flex justify-right" />

# Anwendungen

<img src="/applications.png" style="margin-left: 8rem; !important"/>

---
layout: two-cols-header
class:
---
<img src="/klips_logo.svg" style="max-width: 12rem !important" class="flex justify-right" />

# Anwendungen

https://klips-dev.terrestris.de/easy-to-use-api/chart/?region=dresden&geom=POINT(13.761238060503882%2051.04731292751711)&threshold=25&band=perceived

**Input wird durch den Nutzer über die URL im Browser mitgegeben.** 

<img src="/chart-api.png" style="width: 27rem !important" class="img-shadow"/>

---
layout: two-cols-header
class:
---
<img src="/klips_logo.svg" style="max-width: 12rem !important" class="flex justify-right" />

# Anwendungen

https://klips-dev.terrestris.de/easy-to-use-api/url-generator/

<img src="/url-generator.png" style="width: 35rem !important" class="img-shadow"/>

---
layout: two-cols-header
class:
---
<img src="/klips_logo.svg" style="max-width: 12rem !important" class="flex justify-right" />

# Fazit

- 
- Sehr flexible Struktur

---
layout: main
class:
---

<img src="/klips_logo.svg" style="max-width: 30% !important" class="self-center" />

#
# Hilfreiche Links
#
#

- <mdi-Github /> https://github.com/klips-project
- **KLIPS pygeoapi**: https://klips-dev.terrestris.de/pygeoapi
- **Dokumentation**: https://klips-dev.terrestris.de/easy-to-use-api/dashboard
- **KLIPS Projekt**: https://www.klips-projekt.de
