---
UID: NS:gnssdriver.GNSS_GEOREGION
title: GNSS_GEOREGION
author: windows-driver-content
description: This structure defines the geographical shape of a geofence.
old-location: gnss\gnss_georegion.htm
tech.root: gnss
ms.assetid: 70FC3BCE-3869-4263-8870-BB97438CB5F1
ms.date: 2/15/2018
ms.keywords: "*PGNSS_GEOREGION, GNSS_GEOREGION, GNSS_GEOREGION structure [Sensor Devices], PGNSS_GEOREGION, PGNSS_GEOREGION structure pointer [Sensor Devices], gnss.gnss_georegion, gnssdriver/GNSS_GEOREGION, gnssdriver/PGNSS_GEOREGION"
ms.topic: struct
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	gnssdriver.h
api_name:
-	GNSS_GEOREGION
product:
- Windows
targetos: Windows
req.typenames: GNSS_GEOREGION, *PGNSS_GEOREGION
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


<a href="https://msdn.microsoft.com/736A1D63-A96E-4E29-ADFD-F441AC4757C6">GNSS_GEOREGIONTYP</a>E enumeration that defines the georegion type of a geofence.


### -field Circle


<a href="https://msdn.microsoft.com/library/windows/hardware/dn925179">GNSS_GEOREGION_CIRCLE</a> structure that defines a circular geofence.


### -field Unused

 




#### - Unused[512]

Padding buffer.


## -remarks



A geographical shape is used to define a geofence.  Windows 10 currently supports only circular geofences.





