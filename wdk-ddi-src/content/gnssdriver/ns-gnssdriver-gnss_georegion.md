---
UID: NS:gnssdriver.__unnamed_struct_21
title: GNSS_GEOREGION (gnssdriver.h)
description: This structure defines the geographical shape of a geofence.
old-location: gnss\gnss_georegion.htm
tech.root: gnss
ms.date: 02/15/2018
keywords: ["GNSS_GEOREGION structure"]
ms.keywords: "*PGNSS_GEOREGION, GNSS_GEOREGION, GNSS_GEOREGION structure [Sensor Devices], PGNSS_GEOREGION, PGNSS_GEOREGION structure pointer [Sensor Devices], gnss.gnss_georegion, gnssdriver/GNSS_GEOREGION, gnssdriver/PGNSS_GEOREGION"
req.header: gnssdriver.h
req.include-header: 
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

# GNSS_GEOREGION structure


## -description

This structure defines the geographical shape of  a geofence.

## -struct-fields

### -field Size

Structure size.

### -field Version

Version number.

### -field GeoRegionType

<a href="/windows-hardware/drivers/ddi/gnssdriver/ne-gnssdriver-gnss_georegiontype">GNSS_GEOREGIONTYP</a>E enumeration that defines the georegion type of a geofence.

### -field Circle

<a href="/windows-hardware/drivers/ddi/gnssdriver/ns-gnssdriver-gnss_georegion_circle">GNSS_GEOREGION_CIRCLE</a> structure that defines a circular geofence.

### -field Unused

 




#### - Unused[512]

Padding buffer.

## -remarks

A geographical shape is used to define a geofence.  Windows 10 currently supports only circular geofences.

