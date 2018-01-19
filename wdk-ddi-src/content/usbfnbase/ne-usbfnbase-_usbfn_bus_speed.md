---
UID: NE:usbfnbase._USBFN_BUS_SPEED
title: _USBFN_BUS_SPEED
author: windows-driver-content
description: The USBFN_BUS_SPEED enumeration defines possible bus speeds.
old-location: buses\usbfn_bus_speed.htm
old-project: usbref
ms.assetid: B97E27A1-0D95-41AA-8FF6-A92F70FBAD28
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: _USBFN_BUS_SPEED, *PUSBFN_BUS_SPEED, USBFN_BUS_SPEED
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: usbfnbase.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: USBFN_BUS_SPEED
req.alt-loc: usbfnbase.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: *PUSBFN_BUS_SPEED, USBFN_BUS_SPEED
req.product: Windows 10 or later.
---

# _USBFN_BUS_SPEED enumeration



## -description
The <b>USBFN_BUS_SPEED</b> enumeration defines possible bus speeds.



## -syntax

````
typedef enum _USBFN_BUS_SPEED { 
  UsbfnBusSpeedLow,
  UsbfnBusSpeedFull,
  UsbfnBusSpeedHigh,
  UsbfnBusSpeedSuper,
  UsbfnBusSpeedMaximum
} USBFN_BUS_SPEED;
````


## -enum-fields

### -field UsbfnBusSpeedLow

A low bandwidth bus speed of 1.5 Mbit per second.


### -field UsbfnBusSpeedFull

A full bandwidth bus speed of 12 MBit per second.


### -field UsbfnBusSpeedHigh

A high bus speed of 480 Mbit per second.


### -field UsbfnBusSpeedSuper

A SuperSpeed mode bus speed of 5 Gbit per second.


### -field UsbfnBusSpeedMaximum

The maximum value of the enumeration.


## -remarks
