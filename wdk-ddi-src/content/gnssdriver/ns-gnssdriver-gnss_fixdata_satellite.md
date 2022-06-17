---
UID: NS:gnssdriver.__unnamed_struct_16
title: GNSS_FIXDATA_SATELLITE (gnssdriver.h)
description: The GNSS_FIXDATA_SATELLITE structure in gnssdriver.h defines satellite-related information of a fix.
tech.root: gnss
ms.date: 06/17/2022
keywords: ["GNSS_FIXDATA_SATELLITE structure"]
ms.keywords: "*PGNSS_FIXDATA_SATELLITE, GNSS_FIXDATA_SATELLITE, GNSS_FIXDATA_SATELLITE structure [Sensor Devices], PGNSS_FIXDATA_SATELLITE, PGNSS_FIXDATA_SATELLITE structure pointer [Sensor Devices], gnss.gnss_fixdata_satellite, gnssdriver/GNSS_FIXDATA_SATELLITE, gnssdriver/PGNSS_FIXDATA_SATELLITE"
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
req.typenames: GNSS_FIXDATA_SATELLITE, *PGNSS_FIXDATA_SATELLITE
f1_keywords:
 - PGNSS_FIXDATA_SATELLITE
 - gnssdriver/PGNSS_FIXDATA_SATELLITE
 - GNSS_FIXDATA_SATELLITE
 - gnssdriver/GNSS_FIXDATA_SATELLITE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - gnssdriver.h
api_name:
 - PGNSS_FIXDATA_SATELLITE
 - GNSS_FIXDATA_SATELLITE
---

## -description

This structure defines satellite-related information of a fix.

## -struct-fields

### -field Size

Structure size.

### -field Version

Version number.

### -field SatelliteCount

Number of satellites in this structure. Not all satellites are actually used for positioning.

### -field SatelliteArray

An array of satellites with each array element representing information about a specific satellite.
