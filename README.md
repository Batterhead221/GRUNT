# GRUNT
USB-powered ESP32-S3 sender node for HIVE outlet/circuit heartbeat monitoring

GRUNT is a small plug-in sender board built around a Seeed Studio XIAO ESP32-S3. It plugs into a USB wall adapter through a USB-A male connector and sends periodic ESP-NOW heartbeat packets to the HIVE gateway.

If the outlet has power, GRUNT sends heartbeats.  
If the outlet loses power, GRUNT shuts off and HIVE marks that node as missing/offline.

## Project Status

Prototype hardware designed. Firmware proof-of-concept working on XIAO ESP32-S3.

## System Role

```text
Wall outlet
    ↓
USB wall adapter
    ↓
GRUNT sender board
    ↓ ESP-NOW heartbeat
HIVE gateway


Hardware

Main parts:

* Seeed Studio XIAO ESP32-S3
* USB-A male plug for wall adapter power
* Power indicator LED
* Current-limiting resistor
* Mounting holes
* Simple 2-layer carrier PCB

Power

GRUNT is powered from USB 5V.

The XIAO ESP32-S3 is programmed through its onboard USB-C connector.
GRUNT sends a heartbeat packet over ESP-NOW at a fixed interval.

GRUNT does not connect directly to mains voltage. It is powered only by a standard USB wall adapter.

* The XIAO ESP32-S3 external antenna must be installed for reliable ESP-NOW range.
* The USB-A connector is power-only.
* HIVE is the receiver/gateway board.
* GRUNT is the sender/outlet node.