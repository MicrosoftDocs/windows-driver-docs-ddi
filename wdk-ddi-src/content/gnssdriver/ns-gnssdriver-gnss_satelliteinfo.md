---
UID: NS:gnssdriver.__unnamed_struct_13
title: GNSS_SATELLITEINFO (gnssdriver.h)
description: This structure defines satellite-related information of a fix.
old-location: gnss\gnss_satelliteinfo.htm
tech.root: gnss
ms.date: 02/15/2018
keywords: ["GNSS_SATELLITEINFO structure"]
ms.keywords: "*PGNSS_SATELLITEINFO, GNSS_SATELLITEINFO, GNSS_SATELLITEINFO structure [Sensor Devices], PGNSS_SATELLITEINFO, PGNSS_SATELLITEINFO structure pointer [Sensor Devices], gnss.gnss_satelliteinfo, gnssdriver/GNSS_SATELLITEINFO, gnssdriver/PGNSS_SATELLITEINFO"
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
req.typenames: GNSS_SATELLITEINFO, *PGNSS_SATELLITEINFO
f1_keywords:
 - PGNSS_SATELLITEINFO
 - gnssdriver/PGNSS_SATELLITEINFO
 - GNSS_SATELLITEINFO
 - gnssdriver/GNSS_SATELLITEINFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - gnssdriver.h
api_name:
 - PGNSS_SATELLITEINFO
 - GNSS_SATELLITEINFO
---

# GNSS_SATELLITEINFO structure


## -description

This structure defines satellite-related information of a fix.

## -struct-fields

### -field SatelliteId

Pseudorandom noise (PRN) code or other identification for the satellite.

### -field UsedInPositiong

Indicates whether this was simply a visible satellite or actually used in the positioning.

### -field Elevation

Elevation value

### -field Azimuth

Azimuth value.

### -field SignalToNoiseRatio

Signal to noise ratio.

