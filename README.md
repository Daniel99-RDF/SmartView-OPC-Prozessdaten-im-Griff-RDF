# SmartView-OPC-Prozessdaten-im-Griff-RDF
Ein kleines SCADA-ähnliches System zur Visualisierung von Prozessdaten aus einer SPS über OPC UA.

Das Projekt demonstriert zentrale Konzepte der Industrie 4.0: Vernetzte Maschinen, Echtzeit-Daten und Edge-Computing.

Ein Raspberry Pi 4B liest Prozessdaten von einer Siemens S7-1516 über OPC UA aus und stellt diese über eine Weboberfläche dar.

SCADA Edge Projekt
 
Mini-SCADA-System auf Basis eines Raspberry Pi als Edge Device.  
Prozesswerte werden per **OPC UA** aus einer **Siemens S7-1500** gelesen, über eine **REST-API** bereitgestellt und in einer **Web-Oberfläche** visualisiert.  
Zusätzlich können ausgewählte Werte **in die SPS zurückgeschrieben** und **Grenzwert-Alarme** angezeigt werden.
 
---
 
## Projektziel (Industrie-4.0-Bezug)
 
Ziel ist es, ein leichtgewichtiges SCADA-ähnliches System zu realisieren, das:
- Prozessdaten standardisiert (OPC UA) erfasst
- IT-nah (REST, Web-UI) bereitstellt
- als **Edge-Lösung** zwischen Anlage (OT) und IT dient
 
Das Projekt ist auf **ISA-95 Level 2 (Monitoring & Supervisory Control)** einzuordnen.
 
---
 
## Architektur (vereinfacht)
