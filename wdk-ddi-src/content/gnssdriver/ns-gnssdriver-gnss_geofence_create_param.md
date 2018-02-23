---
UID: NS:gnssdriver.GNSS_GEOFENCE_CREATE_PARAM
title: GNSS_GEOFENCE_CREATE_PARAM
author: windows-driver-content
description: This structure defines the parameters for creating a geofence in the GNSS engine.
old-location: sensors\gnss_geofence_create_param.htm
old-project: sensors
ms.assetid: CA517EF6-41EE-4DB0-B628-35902BA34FFB
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: gnssdriver/GNSS_GEOFENCE_CREATE_PARAM, GNSS_GEOFENCE_CREATE_PARAM, PGNSS_GEOFENCE_CREATE_PARAM structure pointer [Sensor Devices], GNSS_GEOFENCE_CREATE_PARAM structure [Sensor Devices], PGNSS_GEOFENCE_CREATE_PARAM, *PGNSS_GEOFENCE_CREATE_PARAM, gnssdriver/PGNSS_GEOFENCE_CREATE_PARAM, sensors.gnss_geofence_create_param
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	gnssdriver.h
apiname:
-	GNSS_GEOFENCE_CREATE_PARAM
product: Windows
targetos: Windows
req.typenames: GNSS_GEOFENCE_CREATE_PARAM, *PGNSS_GEOFENCE_CREATE_PARAM
---

# GNSS_GEOFENCE_CREATE_PARAM structure


## -description


This structure defines the parameters for creating a geofence in the GNSS engine.


## -syntax


````
typedef struct {
  ULONG               Size;
  ULONG               Version;
  ULONG               AlertTypes;
  GNSS_GEOFENCE_STATE InitialState;
  GNSS_GEOREGION      Boundary;
  BYTE                Unused[512];
} GNSS_GEOFENCE_CREATE_PARAM, *PGNSS_GEOFENCE_CREATE_PARAM;
````


## -struct-fields




### -field Size

Structure size.


### -field Version

Version number.


### -field AlertTypes

This is a bitmask that indicates the various alerts for this geofence that the HLOS is interested in. The GNSS engine should not raise any geofence alerts unless specifically requested by the HLOS.

If the HLOS sets only GNSS_GEOFENCEALERTTYPE_ENTRY, the GNSS engine must track the geofence all the time, but raise alert only when the device has entered the geofence. The next alert is expected when the device moves out of the geofence and reenters.

If the HLOS sets only GNSS_GEOFENCEALERTTYPE_EXIT, the GNSS engine must track the geofence all the time, but raise alert only when the device has exit the geofence after entering it previously. The next alert is expected when the device moves inside the geofence and re-exits.

If the HLOS sets both the bitmasks, the GNSS engine must track the geofence all the time, and raise alert as the device moves in and out of the geofence .

In all cases, the GNSS engine must separately raise the global tracking status alert if it is unable to track the geofences (irrespective of their alert settings).


### -field InitialState

Indicates the initial state of the specific geofence, as seen by the HLOS.  The GNSS engine must use this state as the starting state of the geofence, as opposed always starting from the GNSS_GeofenceState_Unknown state. This allows the GNSS engine to stay in sync with the HLOS in terms of the geofence states and get around any differences in geofence entry or  exit detection logic between the GNSS engine and the HLOS.

As the GNSS engine starts tracking the newly added geofence, if it determines that the geofence is in a different state than this initial state, it should raise the appropriate alert. Conversely, if the states are identical, no alert should be raised.


### -field Boundary

The actual boundary of the geofence.


### -field Unused

 




#### - Unused[512]

Padding buffer.


## -remarks



A geographical shape is used to define a geofence.  Windows 10 currently supports only circular geofences.



