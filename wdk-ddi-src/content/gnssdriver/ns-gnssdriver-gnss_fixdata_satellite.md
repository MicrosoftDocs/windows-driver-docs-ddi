---
UID: NS:gnssdriver.GNSS_FIXDATA_SATELLITE
title: GNSS_FIXDATA_SATELLITE
author: windows-driver-content
description: This structure defines satellite-related information of a fix.
old-location: gnss\gnss_fixdata_satellite.htm
old-project: gnss
ms.assetid: D1454F07-3CBA-498B-B054-6A0D5020A164
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PGNSS_FIXDATA_SATELLITE, GNSS_FIXDATA_SATELLITE, GNSS_FIXDATA_SATELLITE structure [Sensor Devices], PGNSS_FIXDATA_SATELLITE, PGNSS_FIXDATA_SATELLITE structure pointer [Sensor Devices], gnss.gnss_fixdata_satellite, gnssdriver/GNSS_FIXDATA_SATELLITE, gnssdriver/PGNSS_FIXDATA_SATELLITE"
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	GNSS_FIXDATA_SATELLITE
product: Windows
targetos: Windows
req.typenames: GNSS_FIXDATA_SATELLITE, *PGNSS_FIXDATA_SATELLITE
---

# GNSS_FIXDATA_SATELLITE structure


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

 




#### - SatelliteArray[GNSS_MAXSATELLITE]

An array of satellites with each array element representing information about a specific satellite.

