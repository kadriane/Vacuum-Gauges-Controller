# Vacuum Gauges Controller (VGC) 2017 - 2018

<img width="80%" height="80%" src="img/vgc_front.png" />

The master thesis presents the design and the prototype of the new Vacuum Gauges Controller for high and ultra-high vacuum measurements for the Large Hadron Collider at CERN.

## Table of Contents
* [General Info](#general-info)
* [CERN Offical Document](#cern-official-document)
* [Hardware](#hardware)
  * [Electronics components](#electronics-components)
  * [Architecture](#architecture)
  * [Electronics Schematics](#electronics-schematics)
  * [PCB designs and 3D models](#PCB-designs-and-3D-models)
    * [Motherboard](#motherboard)
    * [Backplane board](#backplane-board)
* [Prototype](#prototype)
  * [Motherboard](#motherboard)
  * [Backplane board](#backplane-board)
  * [Final version](#final-version)
* [Software](#software)
  * [GUI templates](#gui-templates-(selected))
* [Author](#author)
* [Copyrights](#Copyrights)

## General Info

The graduate thesis has been performed in collaboration with CERN and AGH.

The aims of this master project were to design and prototype the new controller, which will be used to replaced the out-of-date and obsoleted controllers (the TPG300 and the VGC1000) still in use at CERN.

Author of this project was responsible for tasks like:
- designing, prototyping and soldering the motherboard and backplane PCBs,
- designing and prototyping firmware implementation for a STM32 microcontroller,
- designing and implementing GUI (Graphical User Interface),
- designing and implementing PC console application in C++.

The practical part of this graduate project has been conducted from September 2017 up to September 2018 at CERN. The aims of this thesis were fulfiled successfully and the controller has been psychically made. 

The VGC prototype is operational and can serve the vacuum gauges such as Helmer, Bayard-Alpert, Pirani, Penning and Piezo-resistive.

## CERN Official Document
The master thesis document is available to see on the CERN Documents Server under [this link](https://edms.cern.ch/document/2082555/1).

## Hardware
The motherboard and backplane schematics, 3D models and PCBs have been designed with the use of Altium Designer 2017.

More details can be found in chapters 3 and 4 of this [master thesis](./MasterThesis_Rev20_0__24_09_18_Final.pdf).

### Electronics components
- **`STM32F429BIT6`**: ARM Cortex-M4 main microcontroller
- **`5' TFT LCD MCT050TC12W800480LML`**: 800x480 
- **`256Mbit Micron SDRAM MT48LC16M16A2P`**: TFT LCD active data buffer
- **`64Mbit NOR FLASH S29GL064N90TFI040`**: non-volatile data buffer for GUI templates
- **`512Kbit EEPROM 24FC512`**: non-volatile data buffer for events' timestamps, configuration and settings parameters
- **`L5972D`**: main power supply buck converter 24V/3.3V with 2A current limiter
- **`LT3466EDD`**: TFT LCD Backlight driver and boost converter
- **`TPS2500DRCR`**: USB power boost converter
- **`STF202-22T1G & NZF220TT1`**: USB OTG 2.0 ESD&EMI protection chips
- **`MAX6816`**: user buttons debouncer 
- **`SN74LVC2T45D & SN74LVC2G17D`**: Schmitt-trigger buffers for SPI buses

### Electronics Schematics
- [Motherboard](./schematics/vgc_motherbrd_schema.pdf) 
- [Backplane board](./schematics/vgc_backplanebrd_schema.pdf)

### PCB designs and 3D models

The motherboard is the four-layer PCB, where two layers are the power supply layers (the ground and +3.3VDC, placed onto the internal layers of the PCB), and next two are signal layers (placed on the external layers of the PCB).

The backplane board is a standard two-layer board with a boosted thickness of 3mm (due to requirements for high stiffness and more equalled distribution of mechanical stress).

#### Motherboard

Top layers:

<img width="70%" height="70%" src="pcb/motherbrd_desing_top.png" />

Bottom layers:

<img width="70%" height="70%" src="pcb/motherbrd_desing_bottom.png" />

3D Model:

<img width="70%" height="70%" src="pcb/motherbrd_3d_top.png" />
<img width="70%" height="70%" src="pcb/motherbrd_3d_bottom.png" />

#### Backplane board

Design:

<img width="70%" height="70%" src="pcb/backplanebrd_design.png" />

3D Model:

<img width="70%" height="70%" src="pcb/backplanebrd_3d.png" />

## Prototype

The PCB boards have been done with the use of a solder oven and standard soldering tools.

The design of the front panel has been designed in the AutoCAD 2017 program. The front panel of the prototype has been done with the use of a CNC milling machine.

The motherboard and the backplane boards are mounted to the mechanical chassis through the M3 screws and standoffs.

More detailed photos of prototype can be found in attachments of this [master thesis](./MasterThesis_Rev20_0__24_09_18_Final.pdf).

### Motherboard

<img width="70%" height="70%" src="img/motherbrd_soldered_top.png" />
<img width="70%" height="70%" src="img/motherbrd_soldered_bottom.png" />
<img width="70%" height="70%" src="img/motherbrd_assembled_top.jpg" />

### Backplane board

<img width="70%" height="70%" src="img/backplanebrd_soldered_top.png" />
<img width="70%" height="70%" src="img/backplanebrd_soldered_bottom.png" />

### Final VGC Controller

<img width="70%" height="70%" src="img/vgc_cross_top.jpg"/>
<img width="70%" height="70%" src="img/vgc_cross_back.jpg" />
<img width="70%" height="70%" src="img/vgc_back.jpg" />


## Software
 
Firmware implementation for the STM32 main microcontroller has been written in **`C language`** in the **`Atolic TrueStudio`** IDE.

Console control application has been written in **`C++11`** in the **`Visual Studio Community 2017`** IDE.

Author of project has been not granted with a permission for publishing source codes of firmware and console application.

More details about software can be found in chapter 6 of the [master thesis](./MasterThesis_Rev20_0__24_09_18_Final.pdf).

### GUI templates (selected)
Graphical User Interface (GUI) effects are generated using designed GUI templates, saved as standard image formats and loaded to the external NOR and SDRAM memories. 

More details about GUI can be found in chapter 6.4 of the [master thesis](./MasterThesis_Rev20_0__24_09_18_Final.pdf).

<p float="left">
  <img width="25%" height="25%" src="img_gui/screen00_welcome.jpg" />
  <img width="25%" height="25%" src="img_gui/screen01_pc_load_menu.jpg" />
  <img width="25%" height="25%" src="img_gui/screen03_sys_menu.jpg" />
</p>

<p float="left">
  <img width="25%" height="25%" src="img_gui/screen04_sys_menu_info.jpg" />
  <img width="25%" height="25%" src="img_gui/screen05_helmer_menu.jpg" />
  <img width="25%" height="25%" src="img_gui/screen09_card_menu.jpg" />
</p>

<p float="left">
  <img width="25%" height="25%" src="img_gui/screen10_card_zoom.jpg" />
  <img width="25%" height="25%" src="img_gui/screen12_warn_menu.jpg" />
  <img width="25%" height="25%" src="img_gui/screen13_err_menu.jpg" />
</p>


## Author
- **Karol Adrianek**

## Copyrights
- The European Organization for Nuclear Research (CERN) in Geneve, Switzerland
- AGH University of Science and Technology in Cracow, Poland