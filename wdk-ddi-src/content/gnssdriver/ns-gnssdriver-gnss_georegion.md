---
UID: NS:gnssdriver.GNSS_GEOREGION
title: GNSS_GEOREGION (gnssdriver.h)
description: The GNSS_GEOREGION structure defines the geographical shape of a geofence.
tech.root: gnss
ms.date: 06/17/2022
keywords: ["GNSS_GEOREGION structure"]
ms.keywords: "*PGNSS_GEOREGION, GNSS_GEOREGION, GNSS_GEOREGION structure [Sensor Devices], PGNSS_GEOREGION, PGNSS_GEOREGION structure pointer [Sensor Devices], gnss.gnss_georegion, gnssdriver/GNSS_GEOREGION, gnssdriver/PGNSS_GEOREGION"
req.header: gnssdriver.h
req.include-header: Gnssdriver.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: GNSS_GEOREGION, *PGNSS_GEOREGION
f1_keywords:
 - PGNSS_GEOREGION
 - gnssdriver/PGNSS_GEOREGION
 - GNSS_GEOREGION
 - gnssdriver/GNSS_GEOREGION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - gnssdriver.h
api_name:
 - PGNSS_GEOREGION
 - GNSS_GEOREGION
---

## -description

The **GNSS_GEOREGION** structure defines the geographical shape of a geofence.

## -struct-fields

### -field Size

Structure size.

### -field Version

Version number.

### -field GeoRegionType

[GNSS_GEOREGIONTYPE](./ne-gnssdriver-gnss_georegiontype.md) enumeration that defines the georegion type of a geofence.

### -field Circle

[GNSS_GEOREGION_CIRCLE](./ns-gnssdriver-gnss_georegion_circle.md) structure that defines a circular geofence.

### -field Unused

Padding buffer reserved for future use.

## -remarks

A geographical shape is used to define a geofence.  Windows 10 currently supports only circular geofences.

