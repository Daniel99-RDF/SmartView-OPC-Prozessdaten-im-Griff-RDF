SmartViewOPC

SmartViewOPC ist ein SCADA-/HMI-Projekt zur Anbindung einer **Siemens S7-1500** über **OPC UA**.  

Die Bedienoberfläche läuft im Browser, das Backend auf einem **Raspberry Pi** mit **Flask**.  

Die SPS stellt die Prozessdaten über den OPC-UA-Server bereit.

## Projektziel

Ziel des Projekts ist es, Prozesswerte einer Anlage auszulesen und Aktoren sicher zu steuern.

Wichtige Architekturentscheidung:

- **Lesen** von Zuständen und Sensorwerten über OPC UA

- **Schreiben nicht direkt auf SPS-Ausgänge**

- Stattdessen Schreiben auf Befehlsvariablen in einem Datenbaustein DB_SCADA

- Die SPS übernimmt diese Befehle intern in die eigentliche Steuerlogik

- Rückmeldungen erfolgen über separate Statusvariablen

Dadurch entsteht eine saubere Trennung zwischen:

- Bedienbefehl

- SPS-Logik

- Rückmeldung

## Verwendete Technologien

- **Siemens TIA Portal**

- **Siemens S7-1500**

- **OPC UA**

- **Python**

- **Flask**

- **HTML / CSS / JavaScript**

- **Raspberry Pi OS**

## Systemarchitektur

### SPS

Die S7-1500 arbeitet als **OPC-UA-Server**.

### Raspberry Pi

Der Raspberry Pi arbeitet als:

- **OPC-UA-Client**

- **Flask-Webserver**

- Host für das Frontend

### Browser

Die Visualisierung wird über den Browser aufgerufen.

## Kommunikationsaufbau

### Lesen

Beispielhafte gelesene Werte:

- pressure_raw

- c1_bg4

- c1_bg5

- mb1_state

- mb2_state

- mb3_state

- mb4_state

### Schreiben

Befehle werden über folgende Variablen geschrieben:

- cmd_mb1

- cmd_mb2

- cmd_mb3

- cmd_mb4

### Rückmeldung

Zustände werden über folgende Variablen zurückgemeldet:

- mb1_state

- mb2_state

- mb3_state

- mb4_state

## Datenbaustein / SPS-Logik

Im SPS-Datenbaustein DB_SCADA wurden unter anderem folgende Variablen verwendet:

### Befehle

- cmd_mb1

- cmd_mb2

- cmd_mb3

- cmd_mb4

### Rückmeldungen

- mb1_state

- mb2_state

- mb3_state

- mb4_state

Die SPS übernimmt die Kommandobits in der Programmlogik und bildet daraus die reale Aktorsteuerung.

## Projektstruktur

backend/

├─ app.py

├─ opcua_client.py

├─ config.yml

├─ browse_opcua.py

├─ read_one_tag.py

├─ write_cmd_test.py

├─ test_opcua.py

├─ templates/

│  └─ index.html

└─ static/

   ├─ app.js

   └─ styles.css
 
