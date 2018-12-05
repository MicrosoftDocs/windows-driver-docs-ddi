---
UID: NS:gnssdriver.__unnamed_struct_25
title: GNSS_GEOFENCES_TRACKINGSTATUS_DATA
author: windows-driver-content
description: This structure is used by the GNSS engine to notify of any changes in the tracking status while tracking a set of previously created geofences.
old-location: gnss\gnss_geofences_trackingstatus_data.htm
tech.root: gnss
ms.assetid: 65E59305-B1D9-4255-926A-A72F3B4887AF
ms.date: 02/15/2018
ms.keywords: "*PGNSS_GEOFENCES_TRACKINGSTATUS_DATA, GNSS_GEOFENCES_TRACKINGSTATUS_DATA, GNSS_GEOFENCES_TRACKINGSTATUS_DATA structure [Sensor Devices], PGNSS_GEOFENCES_TRACKINGSTATUS_DATA, PGNSS_GEOFENCES_TRACKINGSTATUS_DATA structure pointer [Sensor Devices], gnss.gnss_geofences_trackingstatus_data, gnssdriver/GNSS_GEOFENCES_TRACKINGSTATUS_DATA, gnssdriver/PGNSS_GEOFENCES_TRACKINGSTATUS_DATA"
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
-	GNSS_GEOFENCES_TRACKINGSTATUS_DATA
product:
- Windows
targetos: Windows
req.typenames: GNSS_GEOFENCES_TRACKINGSTATUS_DATA, *PGNSS_GEOFENCES_TRACKINGSTATUS_DATA
---

# GNSS_GEOFENCES_TRACKINGSTATUS_DATA structure


## -description


This structure is used by the GNSS engine to notify of any changes in the tracking status while tracking a set of previously created geofences.


## -struct-fields




### -field Size

Structure size.


### -field Version

Version number.


### -field Status

A failure code indicates that the GNSS engine is unable to track the geofences (due to bad signal conditions or other transient errors).

A success code indicates that the GNSS engine was previously unable to track geofences, and is now able to track them.


### -field StatusTimeStamp

The UTC time of this status.


### -field Unused

 




#### - Unused[512]

Padding buffer.


## -remarks



The GNSS engine must not raise  events when it is not tracking any mobile-originated geofences (but tracking network-initiated Geofences), or when the geofence tracking has been reset by the GNSS_ResetGeofenceTracking command.



