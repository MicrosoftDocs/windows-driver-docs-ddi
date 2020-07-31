---
UID: NS:gnssdriver.__unnamed_struct_20
title: GNSS_GEOREGION_CIRCLE (gnssdriver.h)
description: This structure is used for defining a circular geofence.
old-location: gnss\gnss_georegion_circle.htm
tech.root: gnss
ms.assetid: 498F8325-C887-4FDE-8BCF-A713639E3B35
ms.date: 02/15/2018
keywords: ["GNSS_GEOREGION_CIRCLE structure"]
ms.keywords: "*PGNSS_GEOREGION_CIRCLE, GNSS_GEOREGION_CIRCLE, GNSS_GEOREGION_CIRCLE structure [Sensor Devices], PGNSS_GEOREGION_CIRCLE, PGNSS_GEOREGION_CIRCLE structure pointer [Sensor Devices], gnss.gnss_georegion_circle, gnssdriver/GNSS_GEOREGION_CIRCLE, gnssdriver/PGNSS_GEOREGION_CIRCLE"
f1_keywords:
 - "gnssdriver/GNSS_GEOREGION_CIRCLE"
 - "GNSS_GEOREGION_CIRCLE"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- gnssdriver.h
api_name:
- GNSS_GEOREGION_CIRCLE
targetos: Windows
req.typenames: GNSS_GEOREGION_CIRCLE, *PGNSS_GEOREGION_CIRCLE
---

# GNSS_GEOREGION_CIRCLE structure


## -description


This structure is used for defining a circular geofence.


## -struct-fields




### -field Latitude

Latitude of the center of the circle.


### -field Longitude

Longitude of the center of the circle.


### -field RadiusInMeters

Radius of the circle in meters.


## -remarks



A geographical shape is used to define a geofence.  Windows 10 currently supports only circular geofences.



